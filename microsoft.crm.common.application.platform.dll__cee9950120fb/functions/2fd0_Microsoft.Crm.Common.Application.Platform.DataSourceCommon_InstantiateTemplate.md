# Microsoft.Crm.Common.Application.Platform.DataSourceCommon::InstantiateTemplate

- ea: `0x2fd0`
- end: `0x2fdf`
- name: `Microsoft.Crm.Common.Application.Platform.DataSourceCommon::InstantiateTemplate`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2420`

## callees

- `0x5c10`
- `0x5c50`

## pseudocode

```c

```

## disassembly

```asm
0x2fd0  ldarg.0
0x2fd1  ldarg.1
0x2fd2  ldarg.2
0x2fd3  ldarg.3
0x2fd4  newobj   instance void Microsoft.Crm.Common.Application.Platform.ServiceCommands.InstantiateTemplateCommand::.ctor(valuetype [mscorlib]System.Guid templateId, valuetype [mscorlib]System.Guid objectId, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType objectType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2fd9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Common.Application.Platform.ServiceCommands.InstantiateTemplateCommand::Execute()
0x2fde  ret
```
