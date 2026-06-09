# Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveAllEntities

- ea: `0xe840`
- end: `0xe8b3`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveAllEntities`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x82d0`

## callees

- `0x7ed0`
- `0xdbd0`
- `0xdc00`
- `0xdc30`
- `0xe840`
- `0x5a810`

## string_xrefs

- `0xe84c`: `prvReadEntity`
- `0xe863`: `prvReadAttribute`
- `0xe87a`: `prvReadRelationship`

## pseudocode

```c

```

## disassembly

```asm
0xe840  newobj   instance void Microsoft.Crm.Sdk.Metadata.MetadataPerformanceCounter::.ctor()
0xe845  stloc.0
0xe846  ldarg.3
0xe847  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xe84c  ldstr    aPrvreadentity// "prvReadEntity"
0xe851  ldarg.3
0xe852  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe857  ldarg.3
0xe858  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe85d  ldarg.3
0xe85e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xe863  ldstr    aPrvreadattribu// "prvReadAttribute"
0xe868  ldarg.3
0xe869  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe86e  ldarg.3
0xe86f  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe874  ldarg.3
0xe875  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xe87a  ldstr    aPrvreadrelatio// "prvReadRelationship"
0xe87f  ldarg.3
0xe880  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xe885  ldarg.3
0xe886  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xe88b  ldc.i4.0
0xe88c  starg.s  2
0xe88e  ldarg.2
0xe88f  call     class Microsoft.Crm.Sdk.Metadata.IMetadataReader Microsoft.Crm.Sdk.Metadata.MetadataReaderFactory::CreateInstance(bool needsUnpublishedMetadata)
0xe894  ldarg.1
0xe895  ldarg.2
0xe896  ldarg.3
0xe897  ldarg.s  4
0xe899  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata[] Microsoft.Crm.Sdk.Metadata.IMetadataReader::RetrieveAllEntities(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityFilters metadataItems, bool retrieveAsIfPublished, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& timestamp)
0xe89e  ldloc.0
0xe89f  callvirt instance void Microsoft.Crm.Sdk.Metadata.MetadataPerformanceCounter::TrackSuccessfulRequest()
0xe8a4  stloc.1
0xe8a5  leave.s  loc_E8B1
0xe8a7  ldloc.0
0xe8a8  brfalse.s loc_E8B0
0xe8aa  ldloc.0
0xe8ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe8b0  endfinally
0xe8b1  ldloc.1
0xe8b2  ret
```
