# Microsoft.Crm.Common.Application.Platform.List::QualifyListByFetchXml

- ea: `0x4350`
- end: `0x4369`
- name: `Microsoft.Crm.Common.Application.Platform.List::QualifyListByFetchXml`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2fc0`

## pseudocode

```c

```

## disassembly

```asm
0x4350  ldarg.1
0x4351  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4356  ldarg.2
0x4357  ldarg.3
0x4358  ldarg.0
0x4359  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x435e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4363  call     void Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RemoveMembersByFetchXmlList(valuetype [mscorlib]System.Guid listId, string fetchXml, bool keepReturned, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4368  ret
```
