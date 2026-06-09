# Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveEntityFromCache

- ea: `0xf0a0`
- end: `0xf1e7`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveEntityFromCache`
- size: `327`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x3b60`
- `0xf0a0`
- `0x5a810`

## string_xrefs

- `0xf0e2`: `prvReadEntity`
- `0xf0fc`: `prvReadAttribute`

## pseudocode

```c

```

## disassembly

```asm
0xf0a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf0a5  ldarg.3
0xf0a6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf0ab  brfalse.s loc_F0C5
0xf0ad  ldarg.2
0xf0ae  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf0b3  brfalse.s loc_F0C5
0xf0b5  ldstr    aLogicalnameIsR// "LogicalName is required when entity id "...
0xf0ba  ldstr    aLogicalname_0// "LogicalName"
0xf0bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0xf0c4  throw
0xf0c5  ldc.i4.s 0xC
0xf0c7  ldarg.1
0xf0c8  and
0xf0c9  brfalse.s loc_F0DB
0xf0cb  ldstr    aOnlyEntityAndA// "Only entity and attribute filters are s"...
0xf0d0  ldstr    aEntityitems// "EntityItems"
0xf0d5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0xf0da  throw
0xf0db  ldarg.s  4
0xf0dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xf0e2  ldstr    aPrvreadentity// "prvReadEntity"
0xf0e7  ldarg.s  4
0xf0e9  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf0ee  ldarg.s  4
0xf0f0  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf0f5  ldarg.s  4
0xf0f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xf0fc  ldstr    aPrvreadattribu// "prvReadAttribute"
0xf101  ldarg.s  4
0xf103  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf108  ldarg.s  4
0xf10a  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf10f  ldarg.2
0xf110  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf115  brtrue.s loc_F128
0xf117  ldarg.s  4
0xf119  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf11e  ldarg.2
0xf11f  ldc.i4.1
0xf120  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xf125  stloc.0
0xf126  br.s     loc_F136
0xf128  ldarg.s  4
0xf12a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf12f  ldarg.3
0xf130  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0xf135  stloc.0
0xf136  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::.ctor()
0xf13b  stloc.1
0xf13c  ldloc.1
0xf13d  ldloc.0
0xf13e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xf143  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_LogicalName(string)
0xf148  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::.ctor()
0xf14d  stloc.2
0xf14e  ldloc.0
0xf14f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xf154  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0xf159  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xf15e  stloc.3
0xf15f  br.s     loc_F1BB
0xf161  ldloc.3
0xf162  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xf167  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0xf16c  stloc.s  4
0xf16e  ldloc.s  4
0xf170  ldarg.s  4
0xf172  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata Microsoft.Crm.Sdk.Metadata.AttributeMetadataFactory::CreateXrmMetadataFromPlatformMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata platformAttributeMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf177  stloc.s  5
0xf179  ldloc.s  5
0xf17b  brfalse.s loc_F1BB
0xf17d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf182  ldloc.s  4
0xf184  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0xf189  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf18e  brfalse.s loc_F1B3
0xf190  ldloc.s  5
0xf192  ldloc.0
0xf193  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0xf198  ldloc.s  4
0xf19a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeOf()
0xf19f  box      [mscorlib]System.Guid
0xf1a4  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xf1a9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xf1ae  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::set_AttributeOf(string)
0xf1b3  ldloc.2
0xf1b4  ldloc.s  5
0xf1b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::Add(var<u1>)
0xf1bb  ldloc.3
0xf1bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xf1c1  brtrue.s loc_F161
0xf1c3  leave.s  loc_F1D9
0xf1c5  ldloc.3
0xf1c6  isinst   [mscorlib]System.IDisposable
0xf1cb  stloc.s  6
0xf1cd  ldloc.s  6
0xf1cf  brfalse.s loc_F1D8
0xf1d1  ldloc.s  6
0xf1d3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf1d8  endfinally
0xf1d9  ldloc.1
0xf1da  ldloc.2
0xf1db  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::ToArray()
0xf1e0  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::set_Attributes(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[])
0xf1e5  ldloc.1
0xf1e6  ret
```
