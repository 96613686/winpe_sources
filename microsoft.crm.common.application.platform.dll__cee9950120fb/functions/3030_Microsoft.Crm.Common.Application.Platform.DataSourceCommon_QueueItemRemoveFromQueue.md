# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRemoveFromQueue

- ea: `0x3030`
- end: `0x303d`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRemoveFromQueue`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x160`
- `0x190`

## pseudocode

```c

```

## disassembly

```asm
0x3030  ldarg.0
0x3031  ldarg.1
0x3032  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRemoveFromQueueCommand::.ctor(valuetype [mscorlib]System.Guid queueItemId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3037  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRemoveFromQueueCommand::Execute()
0x303c  ret
```
