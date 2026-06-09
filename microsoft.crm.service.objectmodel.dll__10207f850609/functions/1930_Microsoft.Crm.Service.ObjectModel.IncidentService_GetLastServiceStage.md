# Microsoft.Crm.Service.ObjectModel.IncidentService::GetLastServiceStage

- ea: `0x1930`
- end: `0x197c`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::GetLastServiceStage`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2200`

## callees

- `0x18b0`
- `0x1930`

## string_xrefs

- `0x194b`: `servicestage`

## pseudocode

```c

```

## disassembly

```asm
0x1930  ldarg.0
0x1931  ldarg.1
0x1932  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::HasServiceStage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1937  brfalse.s loc_197A
0x1939  ldarg.1
0x193a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x193f  ldarg.0
0x1940  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1945  ldc.i4.0
0x1946  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x194b  ldstr    aServicestage// "servicestage"
0x1950  ldc.i4.1
0x1951  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1956  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x195b  stloc.0
0x195c  ldloc.0
0x195d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionsInDisplayOrder()
0x1962  ldloc.0
0x1963  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x1968  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>>::get_Count()
0x196d  ldc.i4.1
0x196e  sub
0x196f  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(!!T0)
0x1974  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x1979  ret
0x197a  ldc.i4.0
0x197b  ret
```
