# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ConvertProductToKit

- ea: `0x2f90`
- end: `0x2f9d`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::ConvertProductToKit`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5a10`
- `0x5a40`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.0
0x2f91  ldarg.1
0x2f92  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertProductToKitCommand::.ctor(valuetype [mscorlib]System.Guid productId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2f97  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.ConvertProductToKitCommand::Execute()
0x2f9c  ret
```
