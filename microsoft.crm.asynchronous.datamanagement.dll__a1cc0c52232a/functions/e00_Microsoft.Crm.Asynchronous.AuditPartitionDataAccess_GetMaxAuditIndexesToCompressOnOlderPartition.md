# Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetMaxAuditIndexesToCompressOnOlderPartition

- ea: `0xe00`
- end: `0xe0d`
- name: `Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetMaxAuditIndexesToCompressOnOlderPartition`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa10`

## string_xrefs

- `0xe00`: `MaxAuditIndexesToCompressOnOlderPartition`

## pseudocode

```c

```

## disassembly

```asm
0xe00  ldstr    aMaxauditindexe_1// "MaxAuditIndexesToCompressOnOlderPartiti"...
0xe05  ldc.i4.3
0xe06  ldarg.1
0xe07  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe0c  ret
```
