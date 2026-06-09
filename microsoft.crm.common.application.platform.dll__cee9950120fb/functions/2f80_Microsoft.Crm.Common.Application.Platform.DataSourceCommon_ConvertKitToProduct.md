# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ConvertKitToProduct

- ea: `0x2f80`
- end: `0x2f8d`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ConvertKitToProduct`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x59c0`
- `0x59f0`

## pseudocode

```c

```

## disassembly

```asm
0x2f80  ldarg.0
0x2f81  ldarg.1
0x2f82  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertKitToProductCommand::.ctor(valuetype [mscorlib]System.Guid kitId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2f87  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertKitToProductCommand::Execute()
0x2f8c  ret
```
