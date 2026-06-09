# Microsoft.Crm.Metadata.EntityService::CreateInternalHelper

- ea: `0x306d0`
- end: `0x30a7a`
- name: `Microsoft.Crm.Metadata.EntityService::CreateInternalHelper`
- size: `938`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x76660`

## callees

- `0x2cad0`
- `0x2cb00`
- `0x2cb70`
- `0x2cd30`
- `0x2d290`
- `0x2d530`
- `0x306d0`
- `0x31070`
- `0x32b80`
- `0x358c0`
- `0x5a810`
- `0x76690`

## string_xrefs

- `0x3080c`: `prvReadEntity`
- `0x307e6`: `prvCreateEntity`
- `0x309d0`: `EntityService.Create for ObjectTypeCode: {0} caught exception: {1}`
- `0x30a0e`: `EntityService.Create failed for ObjectTypeCode: {0} caught exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x306d0  newobj   instance void <>c__DisplayClass22_0::.ctor()
0x306d5  stloc.0
0x306d6  ldloc.0
0x306d7  ldarg.1
0x306d8  stfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x306dd  ldloc.0
0x306de  ldarg.3
0x306df  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x306e4  ldloc.0
0x306e5  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x306ea  ldstr    aEntityinfo// "entityInfo"
0x306ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x306f4  ldloc.0
0x306f5  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x306fa  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x306ff  ldstr    aEntityinfoEnti// "entityInfo.EntityDescription"
0x30704  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x30709  ldarg.2
0x3070a  ldstr    aMetadatahelper// "metadataHelper"
0x3070f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x30714  ldloc.0
0x30715  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x3071a  ldstr    aContext// "context"
0x3071f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x30724  ldloc.0
0x30725  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x3072a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3072f  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_ContextStorage()
0x30734  ldsfld   string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.MetadataCacheUtil::AddStagedMetadataInCache
0x30739  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x3073e  brtrue.s loc_30760
0x30740  ldloc.0
0x30741  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30746  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x3074b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_ContextStorage()
0x30750  ldsfld   string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.MetadataCacheUtil::AddStagedMetadataInCache
0x30755  ldc.i4.1
0x30756  box      [mscorlib]System.Boolean
0x3075b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x30760  ldloc.0
0x30761  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30766  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3076b  pop
0x3076c  ldloc.0
0x3076d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30772  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x30777  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_IsInStagedContext()
0x3077c  brtrue.s loc_3078A
0x3077e  ldloc.0
0x3077f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30784  ldc.i4.1
0x30785  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_FlushMetadataCache(bool)
0x3078a  ldarg.0
0x3078b  ldloc.0
0x3078c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30791  call     instance void Microsoft.Crm.Metadata.EntityService::PreloadSecurityCaches(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x30796  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x3079b  ldloc.0
0x3079c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x307a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x307a6  ldloc.0
0x307a7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x307ac  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x307b1  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.OrganizationFeature::CreateCustomEntity
0x307b6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::IsFeatureDisabled(valuetype [mscorlib]System.Guid)
0x307bb  brfalse.s loc_307DB
0x307bd  ldloc.0
0x307be  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x307c3  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x307c8  brtrue.s loc_307DB
0x307ca  ldc.i4   0x8004B042
0x307cf  ldc.i4.0
0x307d0  newarr   [mscorlib]System.Object
0x307d5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x307da  throw
0x307db  ldloc.0
0x307dc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x307e1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x307e6  ldstr    aPrvcreateentit_0// "prvCreateEntity"
0x307eb  ldloc.0
0x307ec  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x307f1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x307f6  ldloc.0
0x307f7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x307fc  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x30801  ldloc.0
0x30802  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30807  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x3080c  ldstr    aPrvreadentity// "prvReadEntity"
0x30811  ldloc.0
0x30812  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30817  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3081c  ldloc.0
0x3081d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30822  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x30827  ldloc.0
0x30828  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x3082d  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::StartTransactionIfRequired()
0x30832  stloc.1
0x30833  ldc.i4.0
0x30834  stloc.2
0x30835  ldstr    asc_804C0// ""
0x3083a  stloc.3
0x3083b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x30840  stloc.s  4
0x30842  ldloc.0
0x30843  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30848  ldc.i4.1
0x30849  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoAddRootsContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AddRootsOption)
0x3084e  stloc.s  5
0x30850  ldarg.0
0x30851  ldloc.0
0x30852  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x30857  ldarg.2
0x30858  ldloc.0
0x30859  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x3085e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.EntityService::CreateInternal(class Microsoft.Crm.Metadata.EntityCreateInfo entityInfo, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x30863  stloc.s  6
0x30865  ldloc.0
0x30866  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x3086b  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsBPFEntity()
0x30870  brtrue.s loc_30889
0x30872  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::.ctor()
0x30877  ldc.i4.0
0x30878  ldloc.0
0x30879  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x3087e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x30883  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.EntityService::UpdateCustomEntityFeatureStateIfNecessary(bool, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x30888  pop
0x30889  ldloc.0
0x3088a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x3088f  ldc.i4.4
0x30890  ldloc.s  6
0x30892  ldc.i4.1
0x30893  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::AddDependencyOperation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.DependencyOperationType, valuetype [mscorlib]System.Guid, int32)
0x30898  ldloc.0
0x30899  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x3089e  callvirt instance valuetype Microsoft.Crm.Metadata.SuppressMetadataOperationTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_SuppressMetadataOperationType()
0x308a3  ldc.i4.4
0x308a4  and
0x308a5  brtrue.s loc_308B2
0x308a7  ldloc.0
0x308a8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x308ad  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::FlushOrganization(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x308b2  ldnull
0x308b3  stloc.s  7
0x308b5  ldloc.0
0x308b6  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x308bb  callvirt instance string Microsoft.Crm.Metadata.EntityCreateInfo::get_Name()
0x308c0  ldloc.0
0x308c1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x308c6  ldloc.0
0x308c7  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x308cc  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x308d1  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ApplicationMetadataInvalidationTrigger::TriggerEntityMetadataCreateInvalidation(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x308d6  ldloc.0
0x308d7  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x308dc  callvirt instance bool Microsoft.Crm.Metadata.EntityCreateInfo::get_IsActivity()
0x308e1  brfalse.s loc_308EF
0x308e3  ldarg.0
0x308e4  ldloc.0
0x308e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x308ea  call     instance void Microsoft.Crm.Metadata.EntityService::SetBootstrapToRunIfCustomActivityIsCreated(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x308ef  ldloc.0
0x308f0  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x308f5  callvirt instance valuetype Microsoft.Crm.Metadata.SuppressMetadataOperationTypes Microsoft.Crm.Metadata.EntityCreateInfo::get_SuppressMetadataOperationType()
0x308fa  ldc.i4.s 0x40
0x308fc  and
0x308fd  brtrue.s loc_30952
0x308ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x30904  stloc.s  7
0x30906  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.EntityService::Logger
0x3090b  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Metadata.EntityServiceRibbonGenerationActivityType>::get_Instance()
0x30910  ldloc.0
0x30911  ldftn    instance void <>c__DisplayClass22_0::<CreateInternalHelper>b__0()
0x30917  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3091c  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x30921  ldloc.0
0x30922  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30927  ldloc.0
0x30928  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x3092d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x30932  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x30937  stloc.s  8
0x30939  ldloca.s 8
0x3093b  constrained. [mscorlib]System.Guid
0x30941  callvirt instance string [mscorlib]System.Object::ToString()
0x30946  ldloc.s  7
0x30948  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x3094d  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGeneration(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, int64)
0x30952  ldloc.1
0x30953  brfalse.s loc_309A8
0x30955  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x3095a  stloc.s  7
0x3095c  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.EntityService::Logger
0x30961  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Metadata.EntityServiceProcessDependenciesActivityType>::get_Instance()
0x30966  ldloc.0
0x30967  ldftn    instance void <>c__DisplayClass22_0::<CreateInternalHelper>b__1()
0x3096d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x30972  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x30977  ldloc.0
0x30978  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x3097d  ldloc.0
0x3097e  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x30983  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x30988  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x3098d  stloc.s  8
0x3098f  ldloca.s 8
0x30991  constrained. [mscorlib]System.Guid
0x30997  callvirt instance string [mscorlib]System.Object::ToString()
0x3099c  ldloc.s  7
0x3099e  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x309a3  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::DependencyProcessing(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, int64)
0x309a8  ldc.i4.1
0x309a9  stloc.2
0x309aa  ldloc.s  6
0x309ac  stloc.s  8
0x309ae  leave    loc_30A77
0x309b3  ldloc.s  5
0x309b5  brfalse.s loc_309BE
0x309b7  ldloc.s  5
0x309b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x309be  endfinally
0x309bf  stloc.s  9
0x309c1  ldloc.s  9
0x309c3  ldloc.0
0x309c4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x309c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x309ce  ldc.i4.s 0x19
0x309d0  ldstr    aEntityserviceC// "EntityService.Create for ObjectTypeCode"...
0x309d5  ldc.i4.2
0x309d6  newarr   [mscorlib]System.Object
0x309db  dup
0x309dc  ldc.i4.0
0x309dd  ldloc.0
0x309de  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x309e3  callvirt instance int32 Microsoft.Crm.Metadata.EntityCreateInfo::get_ObjectTypeCode()
0x309e8  box      [mscorlib]System.Int32
0x309ed  stelem.ref
0x309ee  dup
0x309ef  ldc.i4.1
0x309f0  ldloc.s  9
0x309f2  stelem.ref
0x309f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x309f8  ldloc.1
0x309f9  brfalse.s loc_30A06
0x309fb  ldloc.0
0x309fc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30a01  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::RollbackTransaction()
0x30a06  ldloc.s  9
0x30a08  callvirt instance string [mscorlib]System.Object::ToString()
0x30a0d  stloc.3
0x30a0e  ldstr    aEntityserviceC_0// "EntityService.Create failed for ObjectT"...
0x30a13  ldloc.0
0x30a14  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x30a19  callvirt instance int32 Microsoft.Crm.Metadata.EntityCreateInfo::get_ObjectTypeCode()
0x30a1e  box      [mscorlib]System.Int32
0x30a23  ldloc.s  9
0x30a25  call     string [mscorlib]System.String::Format(string, object, object)
0x30a2a  ldloc.s  9
0x30a2c  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x30a31  throw
0x30a32  ldloc.0
0x30a33  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass22_0::context
0x30a38  ldloc.0
0x30a39  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x30a3e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescriptionPropertyBag Microsoft.Crm.Metadata.EntityCreateInfo::get_EntityDescription()
0x30a43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityDescription::get_EntityId()
0x30a48  stloc.s  0xA
0x30a4a  ldloca.s 0xA
0x30a4c  constrained. [mscorlib]System.Guid
0x30a52  callvirt instance string [mscorlib]System.Object::ToString()
0x30a57  ldloc.0
0x30a58  ldfld    class Microsoft.Crm.Metadata.EntityCreateInfo <>c__DisplayClass22_0::entityInfo
0x30a5d  callvirt instance int32 Microsoft.Crm.Metadata.EntityCreateInfo::get_ObjectTypeCode()
0x30a62  ldloc.s  4
0x30a64  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x30a69  ldloc.2
0x30a6a  ldloc.3
0x30a6b  ldarg.2
0x30a6c  callvirt instance bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_IsInternalSolutionContext()
0x30a71  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::MetadataServiceEntityCreate(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, int32, int64, bool, string, bool)
0x30a76  endfinally
0x30a77  ldloc.s  8
0x30a79  ret
```
