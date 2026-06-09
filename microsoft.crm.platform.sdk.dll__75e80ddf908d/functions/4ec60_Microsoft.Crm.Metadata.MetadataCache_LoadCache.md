# Microsoft.Crm.Metadata.MetadataCache::LoadCache

- ea: `0x4ec60`
- end: `0x4ef1c`
- name: `Microsoft.Crm.Metadata.MetadataCache::LoadCache`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4e9c0`

## callees

- `0xd380`
- `0x493c0`
- `0x49670`
- `0x4b220`
- `0x4b2a0`
- `0x4ebb0`
- `0x4ec60`
- `0x4ef20`
- `0x4ef70`
- `0x4f4c0`
- `0x4f4e0`
- `0x4fd60`
- `0x4fed0`
- `0x79800`
- `0x80860`
- `0x808c0`

## string_xrefs

- `0x4ec65`: `Metadata_BEGIN_Microsoft.Crm.Metadata.MetadataCache.LoadCache`
- `0x4ec91`: `ASP_BEGIN_MDCACHELOAD: AppDomain = {0}`
- `0x4ecbf`: `Loading StaticMetadataCache for organization : {0}`
- `0x4ed97`: `cacheType`
- `0x4edc5`: `isPerThreadCache`
- `0x4ee1b`: `CacheTimeStamp`
- `0x4ee2c`: `IsInAsyncServiceContext`
- `0x4ee91`: `ASP_END_MDCACHELOAD: AppDomain = {0}`
- `0x4eeb7`: `Loaded MetadataCache. MetadataCacheConfig.LoadMethod = {0} Actual LoadMethod = {1}`
- `0x4ef03`: `Metadata_END_Microsoft.Crm.Metadata.MetadataCache.LoadCache`

## pseudocode

```c

```

## disassembly

```asm
0x4ec60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ec65  ldstr    aMetadataBeginM_0// "Metadata_BEGIN_Microsoft.Crm.Metadata.M"...
0x4ec6a  ldc.i4.0
0x4ec6b  newarr   [mscorlib]System.Object
0x4ec70  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ec75  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x4ec7a  ldarg.0
0x4ec7b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4ec80  stloc.0
0x4ec81  ldnull
0x4ec82  stloc.1
0x4ec83  ldloc.0
0x4ec84  ldloca.s 1
0x4ec86  call     bool Microsoft.Crm.Metadata.MetadataCache::GetConfigInfoForOrganization(valuetype [mscorlib]System.Guid organizationId, [out] class Microsoft.Crm.Metadata.MetadataCacheConfigInfo& configInfo)
0x4ec8b  stloc.2
0x4ec8c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ec91  ldstr    aAspBeginMdcach// "ASP_BEGIN_MDCACHELOAD: AppDomain = {0}"
0x4ec96  ldc.i4.1
0x4ec97  newarr   [mscorlib]System.Object
0x4ec9c  dup
0x4ec9d  ldc.i4.0
0x4ec9e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4eca3  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x4eca8  stelem.ref
0x4eca9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ecae  ldc.i4.0
0x4ecaf  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.PerfLogLevel)
0x4ecb4  ldarg.1
0x4ecb5  ldloc.1
0x4ecb6  call     valuetype Microsoft.Crm.Metadata.LoadMethod Microsoft.Crm.Metadata.MetadataCache::GetLoadMethod(bool fileOnlyIfExists, class Microsoft.Crm.Metadata.MetadataCacheConfigInfo configInfo)
0x4ecbb  stloc.3
0x4ecbc  ldloc.0
0x4ecbd  ldc.i4.s 0x19
0x4ecbf  ldstr    aLoadingStaticm// "Loading StaticMetadataCache for organiz"...
0x4ecc4  ldc.i4.1
0x4ecc5  newarr   [mscorlib]System.Object
0x4ecca  dup
0x4eccb  ldc.i4.0
0x4eccc  ldloc.0
0x4eccd  box      [mscorlib]System.Guid
0x4ecd2  stelem.ref
0x4ecd3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ecd8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x4ecdd  stloc.s  6
0x4ecdf  ldc.i4.3
0x4ece0  ldloc.1
0x4ece1  callvirt instance valuetype Microsoft.Crm.Metadata.MetadataCacheLoadOption Microsoft.Crm.Metadata.MetadataCacheConfigInfo::get_LoadOption()
0x4ece6  bne.un.s loc_4ED01
0x4ece8  ldc.i4.0
0x4ece9  stloc.s  5
0x4eceb  ldloc.3
0x4ecec  ldloc.s  5
0x4ecee  ldloc.1
0x4ecef  call     valuetype Microsoft.Crm.Metadata.LoadMasks Microsoft.Crm.Metadata.MetadataCache::GetLoadMasks(class Microsoft.Crm.Metadata.MetadataCacheConfigInfo configInfo)
0x4ecf4  ldarg.0
0x4ecf5  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache(valuetype Microsoft.Crm.Metadata.LoadMethod method, valuetype Microsoft.Crm.Metadata.CacheType type, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ecfa  stloc.s  4
0x4ecfc  br       loc_4ED8F
0x4ed01  ldc.i4.2
0x4ed02  ldloc.1
0x4ed03  callvirt instance valuetype Microsoft.Crm.Metadata.MetadataCacheLoadOption Microsoft.Crm.Metadata.MetadataCacheConfigInfo::get_LoadOption()
0x4ed08  beq.s    loc_4ED7B
0x4ed0a  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4ed0f  brfalse.s loc_4ED21
0x4ed11  ldc.i4.4
0x4ed12  stloc.s  5
0x4ed14  ldloc.3
0x4ed15  ldloc.s  5
0x4ed17  ldarg.0
0x4ed18  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache(valuetype Microsoft.Crm.Metadata.LoadMethod method, valuetype Microsoft.Crm.Metadata.CacheType type, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ed1d  stloc.s  4
0x4ed1f  br.s     loc_4ED8F
0x4ed21  ldloc.3
0x4ed22  ldc.i4.6
0x4ed23  bne.un.s loc_4ED35
0x4ed25  ldc.i4.1
0x4ed26  stloc.s  5
0x4ed28  ldloc.3
0x4ed29  ldloc.s  5
0x4ed2b  ldarg.0
0x4ed2c  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache(valuetype Microsoft.Crm.Metadata.LoadMethod method, valuetype Microsoft.Crm.Metadata.CacheType type, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ed31  stloc.s  4
0x4ed33  br.s     loc_4ED8F
0x4ed35  ldarg.2
0x4ed36  brfalse.s loc_4ED4C
0x4ed38  call     bool Microsoft.Crm.Caching.CacheConfiguration::get_IsMutableStagedPerThreadMetadataCacheEnabled()
0x4ed3d  brfalse.s loc_4ED4C
0x4ed3f  ldarg.0
0x4ed40  call     bool [Microsoft.Crm]Microsoft.Crm.CrmCacheUtility::IsInStagingContextAndStagedCacheEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ed45  brfalse.s loc_4ED4C
0x4ed47  ldc.i4.6
0x4ed48  stloc.s  5
0x4ed4a  br.s     loc_4ED6E
0x4ed4c  call     bool Microsoft.Crm.Platform.MetadataCacheUtil::IsRefreshableMetadataCacheEnabled()
0x4ed51  brfalse.s loc_4ED58
0x4ed53  ldc.i4.5
0x4ed54  stloc.s  5
0x4ed56  br.s     loc_4ED6E
0x4ed58  call     class Microsoft.Crm.Caching.ISharedCacheStateProvider Microsoft.Crm.Caching.SharedCacheStateFactory::CacheStateProviderInstance()
0x4ed5d  ldarg.0
0x4ed5e  callvirt instance bool Microsoft.Crm.Caching.ISharedCacheStateProvider::IsSharingEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ed63  brfalse.s loc_4ED68
0x4ed65  ldloc.2
0x4ed66  brfalse.s loc_4ED6B
0x4ed68  ldc.i4.1
0x4ed69  br.s     loc_4ED6C
0x4ed6b  ldc.i4.2
0x4ed6c  stloc.s  5
0x4ed6e  ldloc.3
0x4ed6f  ldloc.s  5
0x4ed71  ldarg.0
0x4ed72  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache(valuetype Microsoft.Crm.Metadata.LoadMethod method, valuetype Microsoft.Crm.Metadata.CacheType type, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ed77  stloc.s  4
0x4ed79  br.s     loc_4ED8F
0x4ed7b  ldc.i4.0
0x4ed7c  stloc.s  5
0x4ed7e  ldloc.3
0x4ed7f  ldloc.s  5
0x4ed81  ldloc.1
0x4ed82  call     valuetype Microsoft.Crm.Metadata.LoadMasks Microsoft.Crm.Metadata.MetadataCache::GetLoadMasks(class Microsoft.Crm.Metadata.MetadataCacheConfigInfo configInfo)
0x4ed87  ldarg.0
0x4ed88  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadMetadataCache(valuetype Microsoft.Crm.Metadata.LoadMethod method, valuetype Microsoft.Crm.Metadata.CacheType type, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ed8d  stloc.s  4
0x4ed8f  ldloc.s  6
0x4ed91  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x4ed96  pop
0x4ed97  ldstr    aCachetype// "cacheType"
0x4ed9c  ldloca.s 5
0x4ed9e  constrained. Microsoft.Crm.Metadata.CacheType
0x4eda4  callvirt instance string [mscorlib]System.Object::ToString()
0x4eda9  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4edae  ldstr    aOrganizationid// "organizationId"
0x4edb3  ldloca.s 0
0x4edb5  constrained. [mscorlib]System.Guid
0x4edbb  callvirt instance string [mscorlib]System.Object::ToString()
0x4edc0  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4edc5  ldstr    aIsperthreadcac// "isPerThreadCache"
0x4edca  ldarga.s 2
0x4edcc  call     instance string [mscorlib]System.Boolean::ToString()
0x4edd1  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4edd6  ldstr    aUserid// "UserId"
0x4eddb  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserId()
0x4ede0  callvirt instance string [mscorlib]System.Object::ToString()
0x4ede5  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4edea  ldstr    aLoadmethod// "loadMethod"
0x4edef  ldloca.s 3
0x4edf1  constrained. Microsoft.Crm.Metadata.LoadMethod
0x4edf7  callvirt instance string [mscorlib]System.Object::ToString()
0x4edfc  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4ee01  ldstr    aIsloadedinstag// "IsLoadedInStagedContext"
0x4ee06  ldloc.s  4
0x4ee08  callvirt instance bool Microsoft.Crm.Metadata.DynamicMetadataCache::IsLoadedInStagedContext()
0x4ee0d  stloc.s  7
0x4ee0f  ldloca.s 7
0x4ee11  call     instance string [mscorlib]System.Boolean::ToString()
0x4ee16  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4ee1b  ldstr    aCachetimestamp// "CacheTimeStamp"
0x4ee20  ldloc.s  4
0x4ee22  callvirt instance string Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x4ee27  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4ee2c  ldstr    aIsinasyncservi// "IsInAsyncServiceContext"
0x4ee31  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInAsyncServiceContext()
0x4ee36  stloc.s  7
0x4ee38  ldloca.s 7
0x4ee3a  call     instance string [mscorlib]System.Boolean::ToString()
0x4ee3f  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x4ee44  call     class Microsoft.Crm.Metadata.MetadataCacheEventSource Microsoft.Crm.Metadata.MetadataCacheEventSource::get_Instance()
0x4ee49  ldloc.0
0x4ee4a  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x4ee4f  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_UserId()
0x4ee54  ldloca.s 3
0x4ee56  constrained. Microsoft.Crm.Metadata.LoadMethod
0x4ee5c  callvirt instance string [mscorlib]System.Object::ToString()
0x4ee61  ldloca.s 5
0x4ee63  constrained. Microsoft.Crm.Metadata.CacheType
0x4ee69  callvirt instance string [mscorlib]System.Object::ToString()
0x4ee6e  ldarg.2
0x4ee6f  ldc.i4.0
0x4ee70  ceq
0x4ee72  ldloc.s  4
0x4ee74  callvirt instance bool Microsoft.Crm.Metadata.DynamicMetadataCache::IsLoadedInStagedContext()
0x4ee79  ldloc.s  4
0x4ee7b  callvirt instance string Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0x4ee80  ldloc.s  6
0x4ee82  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x4ee87  callvirt instance void Microsoft.Crm.Metadata.MetadataCacheEventSource::MetadataCacheLoadCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string userId, string loadMethod, string cacheType, bool loadedFromStandardCache, bool isLoadedInStagedContext, string timeStamp, int64 executionTimeInMilliseconds)
0x4ee8c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ee91  ldstr    aAspEndMdcachel// "ASP_END_MDCACHELOAD: AppDomain = {0}"
0x4ee96  ldc.i4.1
0x4ee97  newarr   [mscorlib]System.Object
0x4ee9c  dup
0x4ee9d  ldc.i4.0
0x4ee9e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x4eea3  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x4eea8  stelem.ref
0x4eea9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4eeae  ldc.i4.0
0x4eeaf  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.PerfLogLevel)
0x4eeb4  ldloc.0
0x4eeb5  ldc.i4.s 0x19
0x4eeb7  ldstr    aLoadedMetadata// "Loaded MetadataCache. MetadataCacheConf"...
0x4eebc  ldc.i4.2
0x4eebd  newarr   [mscorlib]System.Object
0x4eec2  dup
0x4eec3  ldc.i4.0
0x4eec4  ldloc.1
0x4eec5  callvirt instance valuetype Microsoft.Crm.Metadata.LoadMethod Microsoft.Crm.Metadata.MetadataCacheConfigInfo::get_LoadMethod()
0x4eeca  box      Microsoft.Crm.Metadata.LoadMethod
0x4eecf  stelem.ref
0x4eed0  dup
0x4eed1  ldc.i4.1
0x4eed2  ldloc.3
0x4eed3  box      Microsoft.Crm.Metadata.LoadMethod
0x4eed8  stelem.ref
0x4eed9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4eede  ldloc.s  4
0x4eee0  stloc.s  8
0x4eee2  leave.s  loc_4EF19
0x4eee4  stloc.s  9
0x4eee6  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInAsyncServiceContext()
0x4eeeb  brfalse.s loc_4EEFC
0x4eeed  ldloc.s  9
0x4eeef  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4eef4  ldloc.s  9
0x4eef6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x4eefb  throw
0x4eefc  rethrow
0x4eefe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ef03  ldstr    aMetadataEndMic_0// "Metadata_END_Microsoft.Crm.Metadata.Met"...
0x4ef08  ldc.i4.0
0x4ef09  newarr   [mscorlib]System.Object
0x4ef0e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4ef13  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x4ef18  endfinally
0x4ef19  ldloc.s  8
0x4ef1b  ret
```
