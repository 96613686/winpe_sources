# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemPickAndRemove

- ea: `0x3010`
- end: `0x301f`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemPickAndRemove`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xc0`
- `0xf0`

## pseudocode

```c

```

## disassembly

```asm
0x3010  ldarg.0
0x3011  ldarg.1
0x3012  ldarg.2
0x3013  ldarg.3
0x3014  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemPickCommand::.ctor(valuetype [mscorlib]System.Guid queueItemId, valuetype [mscorlib]System.Guid workerId, bool removeQueueItem, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3019  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemPickCommand::Execute()
0x301e  ret
```
