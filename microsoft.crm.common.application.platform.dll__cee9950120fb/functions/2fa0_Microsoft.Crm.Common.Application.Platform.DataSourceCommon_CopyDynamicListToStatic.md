# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CopyDynamicListToStatic

- ea: `0x2fa0`
- end: `0x2fad`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CopyDynamicListToStatic`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x5a60`
- `0x5a90`

## pseudocode

```c

```

## disassembly

```asm
0x2fa0  ldarg.0
0x2fa1  ldarg.1
0x2fa2  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyDynamicListCommand::.ctor(valuetype [mscorlib]System.Guid dynamiclistId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2fa7  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Application.Platform.ServiceCommands.CopyDynamicListCommand::Execute()
0x2fac  ret
```
