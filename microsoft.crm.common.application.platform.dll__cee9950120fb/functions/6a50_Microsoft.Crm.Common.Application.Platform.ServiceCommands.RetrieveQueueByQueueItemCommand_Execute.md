# Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::Execute

- ea: `0x6a50`
- end: `0x6a65`
- name: `Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::Execute`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x6a50`

## pseudocode

```c

```

## disassembly

```asm
0x6a50  ldarg.0
0x6a51  ldfld    bool Microsoft.Crm.Common.Application.Platform.ServiceCommands.RetrieveQueueByQueueItemCommand::_queryValid
0x6a56  brfalse.s loc_6A5F
0x6a58  ldarg.0
0x6a59  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x6a5e  ret
0x6a5f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor()
0x6a64  ret
```
