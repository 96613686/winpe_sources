# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::UpdateRibbonClientMetadata

- ea: `0x79780`
- end: `0x79c53`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::UpdateRibbonClientMetadata`
- size: `1235`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x97940`

## callees

- `0x66b60`
- `0x79780`
- `0x79c60`
- `0x79cc0`
- `0x79d30`
- `0x79e00`
- `0x79ed0`

## string_xrefs

- `0x797bf`: `UpdateRibbonClientMetadata: Started generating Ribbon Client Metadata`
- `0x797cd`: `UpdateRibbonClientMetadata: Started generating Ribbon Client Metadata`
- `0x79818`: `UpdateRibbonClientMetadata: Did not find any entities to update during solution install`
- `0x79867`: `UpdateRibbonClientMetadata: Ribbon Client Metadata generation is disabled during solution install`
- `0x798ad`: `UpdateRibbonClientMetadata: Ribbon Client Metadata generation did not run as Organization state is disabled.`
- `0x79906`: `UpdateRibbonClientMetadata: Flushed all Ribbon Caches before generating metadata. Time taken in millisecs:{0}`
- `0x79a19`: `UpdateRibbonClientMetadata: Started Processing EntityTemplate`
- `0x79a7a`: `UpdateRibbonClientMetadata: Generating Ribbon Client Metadata for entity - '{0}' during EntityTemplate processing`
- `0x79aef`: `UpdateRibbonClientMetadata: Completed Processing EntityTemplate. Time taken in milliseconds: {0}`
- `0x79b6c`: `UpdateRibbonClientMetadata: Failed generating Ribbon Client Metadata.Caught Exception : {0}.Inner Exception : {1}`
- `0x79bb9`: `Microsoft.Crm.Tools.ImportExportPublish.UpdateRibbonClientMetadata`
- `0x79c30`: `Microsoft.Crm.Tools.ImportExportPublish.UpdateRibbonClientMetadata`
- `0x79c1b`: `UpdateRibbonClientMetadata: Completed generating Ribbon Client Metadata`

## pseudocode

```c

```

## disassembly

```asm
0x79780  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x79785  stloc.0
0x79786  ldc.i4.1
0x79787  stloc.1
0x79788  ldsfld   string [mscorlib]System.String::Empty
0x7978d  stloc.2
0x7978e  ldsfld   string [mscorlib]System.String::Empty
0x79793  stloc.3
0x79794  ldarg.2
0x79795  ldstr    aSolutionimport// "SolutionImport: {0}"
0x7979a  ldarg.0
0x7979b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x797a0  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x797a5  call     string [mscorlib]System.String::Format(string, object)
0x797aa  ldarg.0
0x797ab  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x797b0  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x797b5  ldstr    asc_9A18C// ""
0x797ba  ldstr    asc_9A18C// ""
0x797bf  ldstr    aUpdateribboncl// "UpdateRibbonClientMetadata: Started gen"...
0x797c4  ldc.i4.1
0x797c5  ldc.i4.0
0x797c6  conv.i8
0x797c7  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x797cc  ldarg.0
0x797cd  ldstr    aUpdateribboncl// "UpdateRibbonClientMetadata: Started gen"...
0x797d2  ldc.i4.0
0x797d3  ldnull
0x797d4  ldarg.2
0x797d5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::LogRibbonClientMDTelemeteryEvent(string entityName, bool hasFailed, class [mscorlib]System.Exception ex, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x797da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x797df  stloc.s  4
0x797e1  ldarg.1
0x797e2  brfalse.s loc_797ED
0x797e4  ldarg.1
0x797e5  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Count()
0x797ea  ldc.i4.1
0x797eb  bge.s    loc_7982A
0x797ed  ldarg.2
0x797ee  ldstr    aSolutionimport// "SolutionImport: {0}"
0x797f3  ldarg.0
0x797f4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x797f9  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x797fe  call     string [mscorlib]System.String::Format(string, object)
0x79803  ldarg.0
0x79804  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79809  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x7980e  ldstr    asc_9A18C// ""
0x79813  ldstr    asc_9A18C// ""
0x79818  ldstr    aUpdateribboncl_0// "UpdateRibbonClientMetadata: Did not fin"...
0x7981d  ldc.i4.1
0x7981e  ldc.i4.0
0x7981f  conv.i8
0x79820  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x79825  leave    loc_79C52
0x7982a  ldarg.2
0x7982b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x79830  ldstr    aDisableribbonm// "DisableRibbonMetadataGeneration"
0x79835  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x7983a  brfalse.s loc_79879
0x7983c  ldarg.2
0x7983d  ldstr    aSolutionimport// "SolutionImport: {0}"
0x79842  ldarg.0
0x79843  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79848  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x7984d  call     string [mscorlib]System.String::Format(string, object)
0x79852  ldarg.0
0x79853  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79858  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x7985d  ldstr    asc_9A18C// ""
0x79862  ldstr    asc_9A18C// ""
0x79867  ldstr    aUpdateribboncl_1// "UpdateRibbonClientMetadata: Ribbon Clie"...
0x7986c  ldc.i4.1
0x7986d  ldc.i4.0
0x7986e  conv.i8
0x7986f  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x79874  leave    loc_79C52
0x79879  ldarg.0
0x7987a  ldarg.2
0x7987b  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsOrganizationEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x79880  brtrue.s loc_798BF
0x79882  ldarg.2
0x79883  ldstr    aSolutionimport// "SolutionImport: {0}"
0x79888  ldarg.0
0x79889  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7988e  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x79893  call     string [mscorlib]System.String::Format(string, object)
0x79898  ldarg.0
0x79899  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x7989e  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x798a3  ldstr    asc_9A18C// ""
0x798a8  ldstr    asc_9A18C// ""
0x798ad  ldstr    aUpdateribboncl_2// "UpdateRibbonClientMetadata: Ribbon Clie"...
0x798b2  ldc.i4.1
0x798b3  ldc.i4.0
0x798b4  conv.i8
0x798b5  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x798ba  leave    loc_79C52
0x798bf  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x798c4  stloc.s  5
0x798c6  ldloc.s  5
0x798c8  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x798cd  ldarg.2
0x798ce  ldc.i4.1
0x798cf  call     void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.RibbonClientMetadataHelper::DoSafeCacheFlushBeforeRibbonMDGeneration(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x798d4  ldloc.s  5
0x798d6  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x798db  ldarg.2
0x798dc  ldstr    aSolutionimport// "SolutionImport: {0}"
0x798e1  ldarg.0
0x798e2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x798e7  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x798ec  call     string [mscorlib]System.String::Format(string, object)
0x798f1  ldarg.0
0x798f2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x798f7  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x798fc  ldstr    asc_9A18C// ""
0x79901  ldstr    asc_9A18C// ""
0x79906  ldstr    aUpdateribboncl_3// "UpdateRibbonClientMetadata: Flushed all"...
0x7990b  ldloc.s  5
0x7990d  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x79912  box      [mscorlib]System.Int64
0x79917  call     string [mscorlib]System.String::Format(string, object)
0x7991c  ldc.i4.1
0x7991d  ldc.i4.0
0x7991e  conv.i8
0x7991f  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x79924  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo>::.ctor()
0x79929  stloc.s  6
0x7992b  ldstr    asc_9A94A// ","
0x79930  ldarg.1
0x79931  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Keys()
0x79936  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x7993b  stloc.3
0x7993c  ldarg.1
0x7993d  ldstr    aNull// "null"
0x79942  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::ContainsKey(var<u1>)
0x79947  brfalse.s loc_79983
0x79949  ldloc.s  6
0x7994b  ldstr    aNull// "null"
0x79950  ldstr    aGlobal// "Global"
0x79955  ldarg.2
0x79956  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.RibbonClientMetadataHelper::GenerateDependentComponentsForSingleRibbonContext(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7995b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x79960  ldloc.s  6
0x79962  ldstr    aNull// "null"
0x79967  ldstr    aDashboard// "Dashboard"
0x7996c  ldarg.2
0x7996d  call     class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.RibbonClientMetadataHelper::GenerateDependentComponentsForSingleRibbonContext(string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x79972  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x79977  ldarg.1
0x79978  ldstr    aNull// "null"
0x7997d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Remove(var<u1>)
0x79982  pop
0x79983  ldarg.0
0x79984  ldarg.1
0x79985  call     instance class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetEntityTemplates(class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> entitiesWithRibbon)
0x7998a  stloc.s  7
0x7998c  ldarg.1
0x7998d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Keys()
0x79992  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, bool>::GetEnumerator()
0x79997  stloc.s  8
0x79999  br.s     loc_799B3
0x7999b  ldloca.s 8
0x7999d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>::get_Current()
0x799a2  stloc.s  9
0x799a4  ldloc.s  6
0x799a6  ldloc.s  9
0x799a8  ldarg.2
0x799a9  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.RibbonClientMetadataHelper::GenerateDependentComponentsForEntityRibbon(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x799ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x799b3  ldloca.s 8
0x799b5  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>::MoveNext()
0x799ba  brtrue.s loc_7999B
0x799bc  leave.s  loc_799CC
0x799be  ldloca.s 8
0x799c0  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, bool>
0x799c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x799cb  endfinally
0x799cc  ldloc.s  7
0x799ce  brfalse  loc_79B12
0x799d3  ldloc.s  7
0x799d5  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<string>::get_Count()
0x799da  ldc.i4.0
0x799db  ble      loc_79B12
0x799e0  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x799e5  stloc.s  0xA
0x799e7  ldloc.s  0xA
0x799e9  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x799ee  ldarg.2
0x799ef  ldstr    aSolutionimport// "SolutionImport: {0}"
0x799f4  ldarg.0
0x799f5  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x799fa  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x799ff  call     string [mscorlib]System.String::Format(string, object)
0x79a04  ldarg.0
0x79a05  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79a0a  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x79a0f  ldstr    asc_9A18C// ""
0x79a14  ldstr    asc_9A18C// ""
0x79a19  ldstr    aUpdateribboncl_4// "UpdateRibbonClientMetadata: Started Pro"...
0x79a1e  ldc.i4.1
0x79a1f  ldc.i4.0
0x79a20  conv.i8
0x79a21  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x79a26  ldarg.0
0x79a27  ldloc.s  7
0x79a29  call     instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetRibbonContexts(class [System.Core]System.Collections.Generic.HashSet`1<string> entityTemplates)
0x79a2e  stloc.s  0xB
0x79a30  ldarg.2
0x79a31  call     class [mscorlib]System.Collections.Generic.List`1<string> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.RibbonClientMetadataHelper::GetUCIEnableEntities(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x79a36  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x79a3b  stloc.s  0xC
0x79a3d  br.s     loc_79AA4
0x79a3f  ldloca.s 0xC
0x79a41  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x79a46  stloc.s  0xD
0x79a48  ldarg.1
0x79a49  ldloc.s  0xD
0x79a4b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::ContainsKey(var<u1>)
0x79a50  brtrue.s loc_79AA4
0x79a52  ldarg.2
0x79a53  ldstr    aSolutionimport// "SolutionImport: {0}"
0x79a58  ldarg.0
0x79a59  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79a5e  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x79a63  call     string [mscorlib]System.String::Format(string, object)
0x79a68  ldarg.0
0x79a69  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79a6e  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x79a73  ldloc.s  0xD
0x79a75  ldstr    asc_9A18C// ""
0x79a7a  ldstr    aUpdateribboncl_5// "UpdateRibbonClientMetadata: Generating "...
0x79a7f  ldloc.s  0xD
0x79a81  call     string [mscorlib]System.String::Format(string, object)
0x79a86  ldc.i4.1
0x79a87  ldc.i4.0
0x79a88  conv.i8
0x79a89  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x79a8e  ldloc.s  6
0x79a90  ldloc.s  0xD
0x79a92  ldloc.s  0xB
0x79a94  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x79a99  ldarg.2
0x79a9a  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo> [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.RibbonClientMetadataHelper::GenerateDependentComponentsForEntityRibbon(string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x79a9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x79aa4  ldloca.s 0xC
0x79aa6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x79aab  brtrue.s loc_79A3F
0x79aad  leave.s  loc_79ABD
0x79aaf  ldloca.s 0xC
0x79ab1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x79ab7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x79abc  endfinally
0x79abd  ldloc.s  0xA
0x79abf  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x79ac4  ldarg.2
0x79ac5  ldstr    aSolutionimport// "SolutionImport: {0}"
0x79aca  ldarg.0
0x79acb  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79ad0  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x79ad5  call     string [mscorlib]System.String::Format(string, object)
0x79ada  ldarg.0
0x79adb  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79ae0  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
0x79ae5  ldstr    asc_9A18C// ""
0x79aea  ldstr    asc_9A18C// ""
0x79aef  ldstr    aUpdateribboncl_6// "UpdateRibbonClientMetadata: Completed P"...
0x79af4  ldloc.s  0xA
0x79af6  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x79afb  box      [mscorlib]System.Int64
0x79b00  call     string [mscorlib]System.String::Format(string, object)
0x79b05  ldc.i4.1
0x79b06  ldloc.s  0xA
0x79b08  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x79b0d  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x79b12  nop
0x79b13  ldloc.s  6
0x79b15  ldarg.2
0x79b16  call     void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.RibbonClientMetadataHelper::UpdateRibbonRuntimeDependencies(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependentComponentInfo>, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x79b1b  leave    loc_79BDC
0x79b20  stloc.s  0xE
0x79b22  ldc.i4.0
0x79b23  stloc.1
0x79b24  ldloc.s  0xE
0x79b26  callvirt instance string [mscorlib]System.Exception::get_Message()
0x79b2b  stloc.2
0x79b2c  ldarg.0
0x79b2d  ldarg.1
0x79b2e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::get_Keys()
0x79b33  call     T0x2B000004
0x79b38  ldc.i4.1
0x79b39  ldloc.s  0xE
0x79b3b  ldarg.2
0x79b3c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::LogRibbonClientMDTelemeteryEvent(class [mscorlib]System.Collections.Generic.List`1<string> entities, bool hasFailed, class [mscorlib]System.Exception ex, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x79b41  ldarg.2
0x79b42  ldstr    aSolutionimport// "SolutionImport: {0}"
0x79b47  ldarg.0
0x79b48  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::parent
0x79b4d  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportXml::get_SolutionName()
  ... truncated ...
```
