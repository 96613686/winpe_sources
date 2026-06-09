# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemReleaseToQueue

- ea: `0x3020`
- end: `0x302d`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemReleaseToQueue`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x110`
- `0x140`

## pseudocode

```c

```

## disassembly

```asm
0x3020  ldarg.0
0x3021  ldarg.1
0x3022  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemReleaseToQueueCommand::.ctor(valuetype [mscorlib]System.Guid queueItemId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3027  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemReleaseToQueueCommand::Execute()
0x302c  ret
```
