# Microsoft.Crm.Common.Application.Platform.List::ListCreateActivities

- ea: `0x4550`
- end: `0x4569`
- name: `Microsoft.Crm.Common.Application.Platform.List::ListCreateActivities`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4470`

## callees

- `0x4570`

## pseudocode

```c

```

## disassembly

```asm
0x4550  ldarg.0
0x4551  ldarg.1
0x4552  ldarg.2
0x4553  ldarg.3
0x4554  ldarg.s  4
0x4556  ldarg.s  5
0x4558  ldc.i4.1
0x4559  ldarg.s  6
0x455b  ldarg.s  7
0x455d  ldarg.s  8
0x455f  ldarg.s  9
0x4561  ldarg.s  0xA
0x4563  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Platform.List::InternalCreateActivities(valuetype [mscorlib]System.Guid listId, string friendlyName, string activityXml, int32 activityObjectTypeCode, valuetype [mscorlib]System.Guid templateId, bool propagate, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions ownershipOption, valuetype [mscorlib]System.Guid ownerId, int32 ownerType, bool sendEmail, valuetype [mscorlib]System.Guid queueId)
0x4568  ret
```
