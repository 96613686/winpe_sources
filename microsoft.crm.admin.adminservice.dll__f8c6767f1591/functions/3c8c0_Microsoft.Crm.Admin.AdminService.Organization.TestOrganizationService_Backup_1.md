# Microsoft.Crm.Admin.AdminService.Organization.TestOrganizationService::Backup_1

- ea: `0x3c8c0`
- end: `0x3c8e7`
- name: `Microsoft.Crm.Admin.AdminService.Organization.TestOrganizationService::Backup_1`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x151e0`
- `0x15200`
- `0x15220`
- `0x15240`

## string_xrefs

- `0x3c8c6`: `BackupPath`
- `0x3c8d1`: `Logpath`
- `0x3c8dc`: `ManifestPath`

## pseudocode

```c

```

## disassembly

```asm
0x3c8c0  newobj   instance void Microsoft.Crm.Admin.Api.OrganizationBackupData::.ctor()
0x3c8c5  dup
0x3c8c6  ldstr    aBackuppath// "BackupPath"
0x3c8cb  callvirt instance void Microsoft.Crm.Admin.Api.OrganizationBackupData::set_BackupPathOnShare(string value)
0x3c8d0  dup
0x3c8d1  ldstr    aLogpath// "Logpath"
0x3c8d6  callvirt instance void Microsoft.Crm.Admin.Api.OrganizationBackupData::set_LogPathOnShare(string value)
0x3c8db  dup
0x3c8dc  ldstr    aManifestpath// "ManifestPath"
0x3c8e1  callvirt instance void Microsoft.Crm.Admin.Api.OrganizationBackupData::set_ManifestPathOnShare(string value)
0x3c8e6  ret
```
