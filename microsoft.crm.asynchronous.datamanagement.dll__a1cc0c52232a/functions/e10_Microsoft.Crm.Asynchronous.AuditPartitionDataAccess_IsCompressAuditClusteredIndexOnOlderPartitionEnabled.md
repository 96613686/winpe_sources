# Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::IsCompressAuditClusteredIndexOnOlderPartitionEnabled

- ea: `0xe10`
- end: `0xe1d`
- name: `Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::IsCompressAuditClusteredIndexOnOlderPartitionEnabled`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa10`

## string_xrefs

- `0xe10`: `CompressAuditClusteredIndexOnOlderPartition`

## pseudocode

```c

```

## disassembly

```asm
0xe10  ldstr    aCompressauditc_1// "CompressAuditClusteredIndexOnOlderParti"...
0xe15  ldc.i4.0
0xe16  ldarg.1
0xe17  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe1c  ret
```
