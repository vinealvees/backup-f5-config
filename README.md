backup-f5-config
=========

This role synchronizes the configuration of the two devices (two in the production environment and two in the staging environment) and backs up the settings of each one.

Requirements
------------

Role tested in Ansible 2.9.2, Python 2.7, BIG-IP 12.1.3.5 and BIG-IP 13.1.0.1

Role Variables
--------------

defaults/main.yml:
```
- balancerUser: user
- balancerPass: password
- balancerProdPrimario: bigip_device_primary_production
- balancerProdSecundario: bigip_device_secondary_production
- balancerHomoPrimario: bigip_device_primary_staging
- balancerHomoSecundario: bigip_device_secondary_staging
- balancerHomoDeviceGroup: sync_group_bigip_staging
- balancerProdDeviceGroup: sync_group_bigip_production
- balancerBackupFilenameHomoLapa: "filename_backup_bigip_secondary_staging.ucs"
- balancerBackupFilePathHomoLapa: "file_path_backup_bigip_secondary_staging_destination.ucs"
- balancerBackupFilenameHomoVivo: "filename_backup_bigip_primary_staging.ucs"
- balancerBackupFilePathHomoVivo: "file_path_backup_bigip_primary_staging_destination.ucs"
- balancerBackupFilenameProdLapa: "filename_backup_bigip_secondary_production.ucs"
- balancerBackupFilePathProdLapa: "file_path_backup_bigip_secondary_production_destination.ucs"
- balancerBackupFilenameProdVivo: "filename_backup_bigip_primary_production.ucs"
- balancerBackupFilePathProdVivo: "file_path_backup_bigip_primary_production_destination.ucs"
```

Example Playbook
----------------

```
- name: Synchronizing and Creating Backup Configurations
  hosts: localhost
  gather_facts: true
  connection: local
  roles:
    - backup-f5-config
```

License
-------

BSD

Author Information
------------------

Github: [vinealvees](#https://github.com/vinealvees/)