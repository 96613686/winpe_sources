# Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::DecorateQuery

- ea: `0x6ef0`
- end: `0x6f1b`
- name: `Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::DecorateQuery`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7280`

## callees

- `0x6f20`
- `0x6ff0`

## pseudocode

```c

```

## disassembly

```asm
0x6ef0  ldarg.0
0x6ef1  ldarg.1
0x6ef2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x6ef7  ldarg.0
0x6ef8  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_context
0x6efd  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6f02  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x6f07  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::_entityMetadata
0x6f0c  ldarg.0
0x6f0d  ldarg.1
0x6f0e  call     instance void Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddDateFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query)
0x6f13  ldarg.0
0x6f14  ldarg.1
0x6f15  call     instance void Microsoft.Crm.Common.Application.Platform.QueryDecorators.ActivityQueryDecorator::AddStateFilter(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query)
0x6f1a  ret
```
