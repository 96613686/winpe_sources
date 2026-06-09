# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddProductToKit

- ea: `0x3090`
- end: `0x309e`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddProductToKit`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5920`
- `0x5950`

## pseudocode

```c

```

## disassembly

```asm
0x3090  ldarg.0
0x3091  ldarg.1
0x3092  ldarg.2
0x3093  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddProductToKitCommand::.ctor(valuetype [mscorlib]System.Guid kitId, valuetype [mscorlib]System.Guid productId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3098  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddProductToKitCommand::Execute()
0x309d  ret
```
