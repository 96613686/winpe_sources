# Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::AuditDeleteOperation

- ea: `0x14240`
- end: `0x14259`
- name: `Microsoft.Crm.CrmLive.Provisioning.DeleteOrganizationBackupExecutor::AuditDeleteOperation`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14110`

## string_xrefs

- `0x14246`: `DeleteOrganizationBackup`
- `0x1424b`: `Delete`

## pseudocode

```c

```

## disassembly

```asm
0x14240  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x14245  ldarg.0
0x14246  ldstr    aDeleteorganiza_0// "DeleteOrganizationBackup"
0x1424b  ldstr    aDelete// "Delete"
0x14250  ldarg.1
0x14251  ldarg.2
0x14252  ldarg.0
0x14253  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x14258  ret
```
