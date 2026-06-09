# Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetSkipAuditPartitionsToCompress

- ea: `0xdf0`
- end: `0xdfd`
- name: `Microsoft.Crm.Asynchronous.AuditPartitionDataAccess::GetSkipAuditPartitionsToCompress`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa10`

## string_xrefs

- `0xdf0`: `SkipAuditPartitionsToCompress`

## pseudocode

```c

```

## disassembly

```asm
0xdf0  ldstr    aSkipauditparti_1// "SkipAuditPartitionsToCompress"
0xdf5  ldc.i4.2
0xdf6  ldarg.1
0xdf7  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSettingWithOrgOverride(string, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xdfc  ret
```
