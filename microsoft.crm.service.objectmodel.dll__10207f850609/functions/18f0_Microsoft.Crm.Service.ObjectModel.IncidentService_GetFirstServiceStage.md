# Microsoft.Crm.Service.ObjectModel.IncidentService::GetFirstServiceStage

- ea: `0x18f0`
- end: `0x192e`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::GetFirstServiceStage`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2200`

## callees

- `0x18b0`
- `0x18f0`

## string_xrefs

- `0x190b`: `servicestage`

## pseudocode

```c

```

## disassembly

```asm
0x18f0  ldarg.0
0x18f1  ldarg.1
0x18f2  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::HasServiceStage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x18f7  brfalse.s loc_192C
0x18f9  ldarg.1
0x18fa  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x18ff  ldarg.0
0x1900  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1905  ldc.i4.0
0x1906  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x190b  ldstr    aServicestage// "servicestage"
0x1910  ldc.i4.1
0x1911  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x1916  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x191b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_OptionsInDisplayOrder()
0x1920  ldc.i4.0
0x1921  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Item(!!T0)
0x1926  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x192b  ret
0x192c  ldc.i4.0
0x192d  ret
```
