# Microsoft.Crm.Common.Application.Platform.List::AddMembersByFetchXml

- ea: `0x4370`
- end: `0x4388`
- name: `Microsoft.Crm.Common.Application.Platform.List::AddMembersByFetchXml`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3050`

## pseudocode

```c

```

## disassembly

```asm
0x4370  ldarg.1
0x4371  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4376  ldarg.2
0x4377  ldarg.0
0x4378  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x437d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x4382  call     void Microsoft.Crm.Common.Application.Platform.DataSourceCommon::AddMembersByFetchXmlList(valuetype [mscorlib]System.Guid listId, string fetchXml, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4387  ret
```
