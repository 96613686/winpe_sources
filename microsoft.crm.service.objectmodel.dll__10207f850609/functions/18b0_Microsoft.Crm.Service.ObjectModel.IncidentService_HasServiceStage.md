# Microsoft.Crm.Service.ObjectModel.IncidentService::HasServiceStage

- ea: `0x18b0`
- end: `0x18e7`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::HasServiceStage`
- size: `55`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11d0`
- `0x18f0`
- `0x1930`
- `0x2200`

## callees

- `0x18b0`

## string_xrefs

- `0x18c2`: `servicestage`

## pseudocode

```c

```

## disassembly

```asm
0x18b0  ldarg.1
0x18b1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18b6  ldarg.0
0x18b7  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x18bc  ldc.i4.0
0x18bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x18c2  ldstr    aServicestage// "servicestage"
0x18c7  ldc.i4.1
0x18c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x18cd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x18d2  stloc.0
0x18d3  ldloc.0
0x18d4  brfalse.s loc_18E5
0x18d6  ldloc.0
0x18d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x18dc  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>>::get_Count()
0x18e1  ldc.i4.0
0x18e2  cgt.un
0x18e4  ret
0x18e5  ldc.i4.0
0x18e6  ret
```
