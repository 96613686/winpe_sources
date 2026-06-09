# Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveEntity

- ea: `0xeff0`
- end: `0xf094`
- name: `Microsoft.Crm.Sdk.Metadata.MetadataServiceProvider::RetrieveEntity`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x83c0`

## callees

- `0x7f20`
- `0xdbd0`
- `0xdc00`
- `0xdc30`
- `0xeff0`
- `0x5a810`

## string_xrefs

- `0xf022`: `prvReadEntity`
- `0xf03c`: `prvReadAttribute`
- `0xf056`: `prvReadRelationship`

## pseudocode

```c

```

## disassembly

```asm
0xeff0  newobj   instance void Microsoft.Crm.Sdk.Metadata.MetadataPerformanceCounter::.ctor()
0xeff5  stloc.0
0xeff6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xeffb  ldarg.3
0xeffc  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf001  brfalse.s loc_F01B
0xf003  ldarg.2
0xf004  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf009  brfalse.s loc_F01B
0xf00b  ldstr    aLogicalnameIsR// "LogicalName is required when entity id "...
0xf010  ldstr    aLogicalname_0// "LogicalName"
0xf015  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0xf01a  throw
0xf01b  ldarg.s  5
0xf01d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xf022  ldstr    aPrvreadentity// "prvReadEntity"
0xf027  ldarg.s  5
0xf029  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf02e  ldarg.s  5
0xf030  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf035  ldarg.s  5
0xf037  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xf03c  ldstr    aPrvreadattribu// "prvReadAttribute"
0xf041  ldarg.s  5
0xf043  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf048  ldarg.s  5
0xf04a  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf04f  ldarg.s  5
0xf051  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0xf056  ldstr    aPrvreadrelatio// "prvReadRelationship"
0xf05b  ldarg.s  5
0xf05d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf062  ldarg.s  5
0xf064  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf069  ldc.i4.0
0xf06a  starg.s  4
0xf06c  ldarg.s  4
0xf06e  call     class Microsoft.Crm.Sdk.Metadata.IMetadataReader Microsoft.Crm.Sdk.Metadata.MetadataReaderFactory::CreateInstance(bool needsUnpublishedMetadata)
0xf073  ldarg.1
0xf074  ldarg.2
0xf075  ldarg.3
0xf076  ldarg.s  4
0xf078  ldarg.s  5
0xf07a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata Microsoft.Crm.Sdk.Metadata.IMetadataReader::RetrieveEntity(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityFilters entityItems, string logicalName, valuetype [mscorlib]System.Guid metadataId, bool retrieveAsIfPublished, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xf07f  ldloc.0
0xf080  callvirt instance void Microsoft.Crm.Sdk.Metadata.MetadataPerformanceCounter::TrackSuccessfulRequest()
0xf085  stloc.1
0xf086  leave.s  loc_F092
0xf088  ldloc.0
0xf089  brfalse.s loc_F091
0xf08b  ldloc.0
0xf08c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf091  endfinally
0xf092  ldloc.1
0xf093  ret
```
