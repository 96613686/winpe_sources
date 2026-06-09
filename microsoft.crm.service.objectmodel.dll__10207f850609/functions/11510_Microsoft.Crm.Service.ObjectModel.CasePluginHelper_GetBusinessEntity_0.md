# Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity_0

- ea: `0x11510`
- end: `0x1152d`
- name: `Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntity_0`
- size: `29`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x11370`
- `0x119d0`
- `0x11e20`
- `0x11e80`
- `0x12590`

## callees

- `0x11510`
- `0x11530`

## pseudocode

```c

```

## disassembly

```asm
0x11510  ldarg.0
0x11511  ldarg.1
0x11512  ldarg.2
0x11513  ldarg.3
0x11514  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.CasePluginHelper::GetBusinessEntityCollection(string entityName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> conditionalAtttributes, string[] requiredFields, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x11519  stloc.0
0x1151a  ldloc.0
0x1151b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x11520  ldc.i4.0
0x11521  bgt.s    loc_11525
0x11523  ldnull
0x11524  ret
0x11525  ldloc.0
0x11526  ldc.i4.0
0x11527  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x1152c  ret
```
