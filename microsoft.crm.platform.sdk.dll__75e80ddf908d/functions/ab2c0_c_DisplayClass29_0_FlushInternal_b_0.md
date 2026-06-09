# <>c__DisplayClass29_0::<FlushInternal>b__0

- ea: `0xab2c0`
- end: `0xab44b`
- name: `<>c__DisplayClass29_0::<FlushInternal>b__0`
- size: `395`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0xd380`
- `0x49670`
- `0x4ab60`
- `0x4b220`
- `0x4b230`
- `0x4b500`
- `0x4b540`
- `0x4b570`
- `0x4b580`
- `0x4b5e0`
- `0x4e710`
- `0x4efd0`
- `0xab2c0`

## string_xrefs

- `0xab2d4`: `NumberOfOrganizationsInCache`
- `0xab32b`: `MetadataCache.FlushOrg:{0}`
- `0xab3c2`: `Error in updating MD cache during flush, clearing it so next access rebuilds it`
- `0xab3fe`: `MetadataCache.FlushAllOrgs`

## pseudocode

```c

```

## disassembly

```asm
0xab2c0  ldc.i4.1
0xab2c1  stloc.0
0xab2c2  ldsfld   string [mscorlib]System.String::Empty
0xab2c7  stloc.1
0xab2c8  ldsfld   string [mscorlib]System.String::Empty
0xab2cd  stloc.2
0xab2ce  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0xab2d3  stloc.3
0xab2d4  ldstr    aNumberoforgani// "NumberOfOrganizationsInCache"
0xab2d9  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0xab2de  callvirt instance int32 Microsoft.Crm.Metadata.MetadataCacheStorage::get_NumberOfOrganizationsInCache()
0xab2e3  stloc.s  4
0xab2e5  ldloca.s 4
0xab2e7  call     instance string [mscorlib]System.Int32::ToString()
0xab2ec  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xab2f1  ldstr    aNumberofdynami// "NumberOfDynamicMetadataContainersInMemo"...
0xab2f6  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0xab2fb  callvirt instance int32 Microsoft.Crm.Metadata.MetadataCacheStorage::get_NumberOfDynamicMetadataContainersInMemory()
0xab300  stloc.s  4
0xab302  ldloca.s 4
0xab304  call     instance string [mscorlib]System.Int32::ToString()
0xab309  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xab30e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xab313  ldarg.0
0xab314  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab319  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xab31e  brfalse  loc_AB3F6
0xab323  ldarg.0
0xab324  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab329  ldc.i4.s 0x19
0xab32b  ldstr    aMetadatacacheF_0// "MetadataCache.FlushOrg:{0}"
0xab330  ldc.i4.1
0xab331  newarr   [mscorlib]System.Object
0xab336  dup
0xab337  ldc.i4.0
0xab338  ldarg.0
0xab339  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab33e  box      [mscorlib]System.Guid
0xab343  stelem.ref
0xab344  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xab349  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0xab34e  ldarg.0
0xab34f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab354  callvirt instance class Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry Microsoft.Crm.Metadata.MetadataCacheStorage::TryLookupEntry(valuetype [mscorlib]System.Guid organizationId)
0xab359  stloc.s  5
0xab35b  ldloc.s  5
0xab35d  brfalse  loc_AB418
0xab362  ldloc.s  5
0xab364  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.MetadataCacheDictionaryEntry::cache
0xab369  isinst   Microsoft.Crm.Metadata.ServerDynamicMetadataCache
0xab36e  stloc.s  6
0xab370  ldloc.s  6
0xab372  brfalse.s loc_AB37C
0xab374  ldloc.s  6
0xab376  callvirt instance string Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0xab37b  stloc.1
0xab37c  ldarg.0
0xab37d  ldfld    bool <>c__DisplayClass29_0::forceRemoveCache
0xab382  brtrue.s loc_AB3E4
0xab384  call     bool Microsoft.Crm.Platform.MetadataCacheUtil::IsRefreshableMetadataCacheEnabled()
0xab389  brfalse.s loc_AB3E4
0xab38b  ldloc.s  6
0xab38d  brfalse.s loc_AB3E4
0xab38f  ldloc.s  6
0xab391  callvirt instance class Microsoft.Crm.Metadata.IMetadataCacheDataProvider Microsoft.Crm.Metadata.ServerDynamicMetadataCache::get_Provider()
0xab396  isinst   Microsoft.Crm.Metadata.DynamicMetadataCacheDataProvider
0xab39b  brfalse.s loc_AB3E4
0xab39d  ldarg.0
0xab39e  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab3a3  ldarg.0
0xab3a4  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext <>c__DisplayClass29_0::context
0xab3a9  call     void Microsoft.Crm.Metadata.MetadataCache::UpdateCache(valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0xab3ae  ldc.i4.0
0xab3af  stloc.0
0xab3b0  ldloc.s  6
0xab3b2  callvirt instance string Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0xab3b7  stloc.2
0xab3b8  leave.s  loc_AB418
0xab3ba  ldarg.0
0xab3bb  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab3c0  ldc.i4.s 0x19
0xab3c2  ldstr    aErrorInUpdatin// "Error in updating MD cache during flush"...
0xab3c7  ldc.i4.0
0xab3c8  newarr   [mscorlib]System.Object
0xab3cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xab3d2  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0xab3d7  ldarg.0
0xab3d8  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab3dd  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheStorage::FlushNoNotification(valuetype [mscorlib]System.Guid organizationId)
0xab3e2  leave.s  loc_AB418
0xab3e4  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0xab3e9  ldarg.0
0xab3ea  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab3ef  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheStorage::FlushNoNotification(valuetype [mscorlib]System.Guid organizationId)
0xab3f4  br.s     loc_AB418
0xab3f6  ldnull
0xab3f7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xab3fc  ldc.i4.s 0x19
0xab3fe  ldstr    aMetadatacacheF_1// "MetadataCache.FlushAllOrgs"
0xab403  ldc.i4.0
0xab404  newarr   [mscorlib]System.Object
0xab409  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xab40e  ldsfld   class Microsoft.Crm.Metadata.MetadataCacheStorage Microsoft.Crm.Metadata.MetadataCacheStorage::StaticInstance
0xab413  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheStorage::FlushForAllOrganizationsNoNotification()
0xab418  ldloc.3
0xab419  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0xab41e  pop
0xab41f  call     class Microsoft.Crm.Metadata.MetadataCacheEventSource Microsoft.Crm.Metadata.MetadataCacheEventSource::get_Instance()
0xab424  ldarg.0
0xab425  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass29_0::organizationId
0xab42a  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0xab42f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserId()
0xab434  ldloc.0
0xab435  ldc.i4.1
0xab436  ldc.i4.0
0xab437  ldloc.1
0xab438  ldloc.2
0xab439  ldloc.3
0xab43a  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0xab43f  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheEventSource::MetadataCacheFlushCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string userId, bool isCacheRemoved, bool wasLoadedFromStandardCache, bool wasLoadedInStagedContext, string originalTimeStamp, string updatedTimeStamp, int64 executionTimeInMilliseconds)
0xab444  call     void Microsoft.Crm.Metadata.MetadataCache::TrackNumberOfOrganizationsInCache()
0xab449  ldloc.0
0xab44a  ret
```
