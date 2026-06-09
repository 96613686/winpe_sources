# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRoute

- ea: `0x2fe0`
- end: `0x2ff3`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRoute`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x6170`
- `0x6260`

## pseudocode

```c

```

## disassembly

```asm
0x2fe0  ldarg.0
0x2fe1  ldarg.1
0x2fe2  ldarg.2
0x2fe3  ldarg.3
0x2fe4  ldarg.s  4
0x2fe6  ldarg.s  5
0x2fe8  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QueueItemRouteCommand::.ctor(valuetype [mscorlib]System.Guid entityId, valuetype [mscorlib]System.Guid destinationQueueId, valuetype [mscorlib]System.Guid workerId, int32 workerType, bool keepExisting, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2fed  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.QueueItemRouteCommand::Execute()
0x2ff2  ret
```
