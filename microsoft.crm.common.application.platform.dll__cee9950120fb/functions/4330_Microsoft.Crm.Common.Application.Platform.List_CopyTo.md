# Microsoft.Crm.Common.Application.Platform.List::CopyTo

- ea: `0x4330`
- end: `0x434d`
- name: `Microsoft.Crm.Common.Application.Platform.List::CopyTo`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2fb0`

## pseudocode

```c

```

## disassembly

```asm
0x4330  ldarg.1
0x4331  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4336  ldarg.2
0x4337  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x433c  ldarg.0
0x433d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x4342  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4347  call     void Microsoft.Crm.Common.Application.Platform.DataSourceCommon::CopyMembersList(valuetype [mscorlib]System.Guid sourceListId, valuetype [mscorlib]System.Guid destinationListId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x434c  ret
```
