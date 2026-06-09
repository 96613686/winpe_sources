# Microsoft.Crm.Common.Application.Platform.List::Execute

- ea: `0x4530`
- end: `0x454a`
- name: `Microsoft.Crm.Common.Application.Platform.List::Execute`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4570`

## pseudocode

```c

```

## disassembly

```asm
0x4530  ldarg.0
0x4531  ldarg.1
0x4532  ldarg.2
0x4533  ldnull
0x4534  ldc.i4.0
0x4535  ldarg.3
0x4536  ldc.i4.0
0x4537  ldarg.s  4
0x4539  ldarg.s  5
0x453b  ldarg.s  6
0x453d  ldarg.s  7
0x453f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4544  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Platform.List::InternalCreateActivities(valuetype [mscorlib]System.Guid listId, string friendlyName, string activityXml, int32 activityObjectTypeCode, valuetype [mscorlib]System.Guid templateId, bool propagate, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions ownershipOption, valuetype [mscorlib]System.Guid ownerId, int32 ownerType, bool sendEmail, valuetype [mscorlib]System.Guid queueId)
0x4549  ret
```
