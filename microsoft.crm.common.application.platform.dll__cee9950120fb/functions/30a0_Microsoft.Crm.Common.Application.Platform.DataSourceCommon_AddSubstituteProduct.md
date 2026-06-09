# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddSubstituteProduct

- ea: `0x30a0`
- end: `0x30ae`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddSubstituteProduct`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5970`
- `0x59a0`

## pseudocode

```c

```

## disassembly

```asm
0x30a0  ldarg.0
0x30a1  ldarg.1
0x30a2  ldarg.2
0x30a3  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddSubstituteProductCommand::.ctor(valuetype [mscorlib]System.Guid productId, valuetype [mscorlib]System.Guid substituteId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x30a8  call     instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.AddSubstituteProductCommand::Execute()
0x30ad  ret
```
