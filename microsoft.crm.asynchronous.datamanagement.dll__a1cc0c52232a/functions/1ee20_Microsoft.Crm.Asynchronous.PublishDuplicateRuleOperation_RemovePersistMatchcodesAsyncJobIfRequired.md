# Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::RemovePersistMatchcodesAsyncJobIfRequired

- ea: `0x1ee20`
- end: `0x1ee33`
- name: `Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::RemovePersistMatchcodesAsyncJobIfRequired`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1ed50`

## callees

- `0x1ee20`
- `0x1ee40`
- `0x1eed0`

## pseudocode

```c

```

## disassembly

```asm
0x1ee20  ldarg.2
0x1ee21  ldarg.0
0x1ee22  call     int32 Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::GetPublishedOrPublishingRulesCount(valuetype [mscorlib]System.Guid organizationId, string entityName)
0x1ee27  ldc.i4.0
0x1ee28  bgt.s    loc_1EE32
0x1ee2a  ldarg.0
0x1ee2b  ldarg.2
0x1ee2c  ldarg.1
0x1ee2d  call     void Microsoft.Crm.Asynchronous.PublishDuplicateRuleOperation::RemovePersistMatchcodesAsyncJob(string entityName, valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Asynchronous.DuplicateRuleDataAccess data)
0x1ee32  ret
```
