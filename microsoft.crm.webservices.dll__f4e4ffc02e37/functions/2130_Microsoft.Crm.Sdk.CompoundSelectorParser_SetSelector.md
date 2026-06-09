# Microsoft.Crm.Sdk.CompoundSelectorParser::SetSelector

- ea: `0x2130`
- end: `0x2189`
- name: `Microsoft.Crm.Sdk.CompoundSelectorParser::SetSelector`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x2410`
- `0x4600`
- `0x4930`

## pseudocode

```c

```

## disassembly

```asm
0x2130  ldarg.2
0x2131  castclass object[]
0x2136  ldc.i4.0
0x2137  ldelem.ref
0x2138  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0x213d  stloc.0
0x213e  ldarg.1
0x213f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.RequestBase::get_OrganizationId()
0x2144  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2149  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x214e  stloc.1
0x214f  ldarg.0
0x2150  ldloc.1
0x2151  ldloc.0
0x2152  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Name()
0x2157  ldc.i4.1
0x2158  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x215d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x2162  call     instance string Microsoft.Crm.Sdk.CompoundSelectorParser::GetSubEntityName(string parentEntityPlatformName)
0x2167  stloc.2
0x2168  ldarg.1
0x2169  ldloc.0
0x216a  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Name()
0x216f  ldloc.1
0x2170  ldloc.2
0x2171  ldc.i4.0
0x2172  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2177  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x217c  ldc.i4.1
0x217d  ldarg.1
0x217e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.RequestBase::get_OrganizationId()
0x2183  callvirt instance void Microsoft.Crm.Sdk.RequestBase::SetCategoryEntity(string primaryEntity, string secondaryEntity, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mappingType, valuetype [mscorlib]System.Guid organizationId)
0x2188  ret
```
