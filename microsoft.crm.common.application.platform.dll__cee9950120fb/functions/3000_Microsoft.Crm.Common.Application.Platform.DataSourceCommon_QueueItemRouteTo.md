# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRouteTo

- ea: `0x3000`
- end: `0x300e`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::QueueItemRouteTo`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1b0`
- `0x1e0`

## pseudocode

```c

```

## disassembly

```asm
0x3000  ldarg.0
0x3001  ldarg.1
0x3002  ldarg.2
0x3003  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRouteToCommand::.ctor(valuetype [mscorlib]System.Guid queueItemId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference routeToEntityReference, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3008  call     instance void Microsoft.Crm.Application.Platform.ServiceCommands.QueueItemRouteToCommand::Execute()
0x300d  ret
```
