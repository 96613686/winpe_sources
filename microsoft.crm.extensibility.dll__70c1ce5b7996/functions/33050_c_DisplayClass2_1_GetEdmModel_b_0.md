# <>c__DisplayClass2_1::<GetEdmModel>b__0

- ea: `0x33050`
- end: `0x3323a`
- name: `<>c__DisplayClass2_1::<GetEdmModel>b__0`
- size: `490`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1a480`
- `0x1eea0`
- `0x1ef30`
- `0x20020`
- `0x288d0`
- `0x33050`

## string_xrefs

- `0x331c9`: `CrmODataEdmModelCreateCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x33050  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetOrganizationContext()
0x33055  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_Instance()
0x3305a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache::Instance()
0x3305f  ldarg.0
0x33060  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33065  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache <>c__DisplayClass2_0::metadataCache
0x3306a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x3306f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OrgType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization::get_OrgType()
0x33074  call     class [mscorlib]System.IDisposable Microsoft.Crm.Extensibility.ODataV4.CrmODataModelLock::Enter(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache runtimeTypeCache, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataEntitiesCache xrmMetadataEntitiesCache, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OrgType orgType)
0x33079  stloc.0
0x3307a  ldarg.0
0x3307b  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33080  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache <>c__DisplayClass2_0::metadataCache
0x33085  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ServerDynamicMetadataCache
0x3308a  dup
0x3308b  brtrue.s loc_33091
0x3308d  pop
0x3308e  ldnull
0x3308f  br.s     loc_330A2
0x33091  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataContainer [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ServerDynamicMetadataCache::get___DynamicMetadataContainer()
0x33096  dup
0x33097  brtrue.s loc_3309D
0x33099  pop
0x3309a  ldnull
0x3309b  br.s     loc_330A2
0x3309d  call     instance class [mscorlib]System.IDisposable [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataContainer::AcquireReadLockXXX()
0x330a2  stloc.1
0x330a3  ldstr    aLockwait// "LockWait"
0x330a8  ldarg.0
0x330a9  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken <>c__DisplayClass2_1::executionToken
0x330ae  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x330b3  stloc.2
0x330b4  ldloca.s 2
0x330b6  call     instance string [mscorlib]System.Int64::ToString()
0x330bb  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x330c0  ldstr    aIsruntimetypei// "IsRuntimeTypeInitialized.Crm"
0x330c5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_Instance()
0x330ca  ldc.i4.0
0x330cb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::IsInitialized(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OrgType)
0x330d0  stloc.3
0x330d1  ldloca.s 3
0x330d3  call     instance string [mscorlib]System.Boolean::ToString()
0x330d8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x330dd  ldstr    aIsruntimetypei_0// "IsRuntimeTypeInitialized.Cds"
0x330e2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::get_Instance()
0x330e7  ldc.i4.1
0x330e8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.RuntimeTypeCache::IsInitialized(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OrgType)
0x330ed  stloc.3
0x330ee  ldloca.s 3
0x330f0  call     instance string [mscorlib]System.Boolean::ToString()
0x330f5  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x330fa  ldstr    aModelversion// "ModelVersion"
0x330ff  ldarg.0
0x33100  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33105  ldflda   valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion <>c__DisplayClass2_0::modelVersion
0x3310a  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion
0x33110  callvirt instance string [mscorlib]System.Object::ToString()
0x33115  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x3311a  ldstr    aModelvisibilit// "ModelVisibility"
0x3311f  ldarg.0
0x33120  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33125  ldflda   valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility <>c__DisplayClass2_0::modelVisibility
0x3312a  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility
0x33130  callvirt instance string [mscorlib]System.Object::ToString()
0x33135  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x3313a  ldarg.0
0x3313b  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33140  ldarg.0
0x33141  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33146  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache <>c__DisplayClass2_0::metadataCache
0x3314b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_EdmModel()
0x33150  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>> <>c__DisplayClass2_0::edmModelsCache
0x33155  ldarg.0
0x33156  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x3315b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>> <>c__DisplayClass2_0::edmModelsCache
0x33160  ldarg.0
0x33161  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33166  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion <>c__DisplayClass2_0::modelVersion
0x3316b  ldarg.0
0x3316c  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33171  ldflda   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel> <>c__DisplayClass2_0::versionedEdmModelCache
0x33176  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>>::TryGetValue(var<u1>, !!T0)
0x3317b  brfalse.s loc_331A5
0x3317d  ldarg.0
0x3317e  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33183  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel> <>c__DisplayClass2_0::versionedEdmModelCache
0x33188  ldarg.0
0x33189  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x3318e  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility <>c__DisplayClass2_0::modelVisibility
0x33193  ldarg.0
0x33194  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33199  ldflda   class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel <>c__DisplayClass2_0::edmModel
0x3319e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>::TryGetValue(var<u1>, !!T0)
0x331a3  brtrue.s loc_33223
0x331a5  ldstr    aMethodname// "methodName"
0x331aa  ldstr    aInitializeedmm// "InitializeEdmModels"
0x331af  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x331b4  ldarg.0
0x331b5  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x331ba  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache <>c__DisplayClass2_0::metadataCache
0x331bf  call     void Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::InitializeEdmModels(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache)
0x331c4  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x331c9  ldstr    aCrmodataedmmod// "CrmODataEdmModelCreateCompleted"
0x331ce  ldstr    aOdataedmmodel// "oDataEdmModel"
0x331d3  ldstr    aMetadata_0// "metadata"
0x331d8  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x331dd  ldarg.0
0x331de  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken <>c__DisplayClass2_1::executionToken
0x331e3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x331e8  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, class [mscorlib]System.Tuple`2<string, string> parameters, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x331ed  ldarg.0
0x331ee  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x331f3  ldarg.0
0x331f4  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x331f9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>> <>c__DisplayClass2_0::edmModelsCache
0x331fe  ldarg.0
0x331ff  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33204  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion <>c__DisplayClass2_0::modelVersion
0x33209  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>>::get_Item(void)
0x3320e  ldarg.0
0x3320f  ldfld    class <>c__DisplayClass2_0 <>c__DisplayClass2_1::CS$<>8__locals1
0x33214  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility <>c__DisplayClass2_0::modelVisibility
0x33219  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel>::get_Item(void)
0x3321e  stfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel <>c__DisplayClass2_0::edmModel
0x33223  leave.s  loc_33239
0x33225  ldloc.1
0x33226  brfalse.s loc_3322E
0x33228  ldloc.1
0x33229  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3322e  endfinally
0x3322f  ldloc.0
0x33230  brfalse.s loc_33238
0x33232  ldloc.0
0x33233  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33238  endfinally
0x33239  ret
```
