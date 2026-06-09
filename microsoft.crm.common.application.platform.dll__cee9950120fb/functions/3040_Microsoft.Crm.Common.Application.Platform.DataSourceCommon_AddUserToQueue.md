# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddUserToQueue

- ea: `0x3040`
- end: `0x304e`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddUserToQueue`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x70`
- `0xa0`

## pseudocode

```c

```

## disassembly

```asm
0x3040  ldarg.0
0x3041  ldarg.1
0x3042  ldarg.2
0x3043  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.AddUserToQueueCommand::.ctor(valuetype [mscorlib]System.Guid queueId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity member, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3048  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.AddUserToQueueCommand::Execute()
0x304d  ret
```
