# Microsoft.Crm.ObjectModel.RibbonClientMetadataUninstallHandler::RegenerateRibbonMetadataForEntities

- ea: `0x1995b0`
- end: `0x199788`
- name: `Microsoft.Crm.ObjectModel.RibbonClientMetadataUninstallHandler::RegenerateRibbonMetadataForEntities`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1995a0`

## callees

- `0x1995b0`
- `0x199790`
- `0x1b2450`
- `0x1b2ae0`
- `0x1eae30`
- `0x1eaec0`
- `0x1eb5e0`

## string_xrefs

- `0x1995e5`: `Solution Uninstall`
- `0x1996bd`: `Solution Uninstall`
- `0x199713`: `Solution Uninstall`
- `0x1995fb`: `Started updating Ribbon Metadata at solution uninstall.`
- `0x1996d3`: `Completed updating Ribbon Metadata at solution uninstall.`
- `0x199729`: `Failed updating Ribbon Metadata at solution uninstall.`

## pseudocode

```c

```

## disassembly

```asm
0x1995b0  ldsfld   string [mscorlib]System.String::Empty
0x1995b5  stloc.0
0x1995b6  ldc.i4.0
0x1995b7  stloc.1
0x1995b8  ldc.i4.0
0x1995b9  stloc.2
0x1995ba  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1995bf  stloc.3
0x1995c0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x1995c5  ldarg.2
0x1995c6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1995cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x1995d0  ldarg.2
0x1995d1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x1995d6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_UniqueName()
0x1995db  stloc.s  4
0x1995dd  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x1995e2  stloc.s  5
0x1995e4  ldarg.2
0x1995e5  ldstr    aSolutionUninst// "Solution Uninstall"
0x1995ea  ldloc.s  4
0x1995ec  ldstr    asc_24F76C// ""
0x1995f1  ldstr    asc_24F76C// ""
0x1995f6  ldstr    a01_12// "{0}: {1}"
0x1995fb  ldstr    aStartedUpdatin// "Started updating Ribbon Metadata at sol"...
0x199600  ldloc.s  4
0x199602  call     string [mscorlib]System.String::Format(string, object, object)
0x199607  ldc.i4.1
0x199608  ldc.i4.0
0x199609  conv.i8
0x19960a  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x19960f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo>::.ctor()
0x199614  stloc.s  6
0x199616  ldarg.1
0x199617  brfalse  loc_199787
0x19961c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x199621  stloc.s  7
0x199623  ldarg.1
0x199624  callvirt instance valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<var<u1>> class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x199629  stloc.s  8
0x19962b  br.s     loc_19966D
0x19962d  ldloca.s 8
0x19962f  call     instance var<u1> valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x199634  stloc.s  9
0x199636  ldarg.0
0x199637  ldloc.s  9
0x199639  ldarg.2
0x19963a  call     instance string Microsoft.Crm.ObjectModel.RibbonClientMetadataUninstallHandler::GetEntityLogicalName(valuetype [mscorlib]System.Guid formId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x19963f  stloc.s  0xA
0x199641  ldloc.s  5
0x199643  ldloc.s  0xA
0x199645  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x19964a  brtrue.s loc_19966D
0x19964c  ldloc.s  6
0x19964e  ldloc.s  0xA
0x199650  ldarg.2
0x199651  call     class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo> Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::GenerateDependentComponentsForEntityRibbon(string entityLogicalName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x199656  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x19965b  ldloc.s  5
0x19965d  ldloc.s  0xA
0x19965f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x199664  pop
0x199665  ldloc.3
0x199666  ldloc.s  0xA
0x199668  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x19966d  ldloca.s 8
0x19966f  call     instance bool valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x199674  brtrue.s loc_19962D
0x199676  leave.s  loc_199686
0x199678  ldloca.s 8
0x19967a  constrained. valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<valuetype [mscorlib]System.Guid>
0x199680  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x199685  endfinally
0x199686  ldloc.s  6
0x199688  ldstr    aNull// "null"
0x19968d  ldstr    aGlobal_0// "Global"
0x199692  ldarg.2
0x199693  call     class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo> Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::GenerateDependentComponentsForSingleRibbonContext(string entityLogicalName, string ribbonContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x199698  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x19969d  ldloc.s  6
0x19969f  ldstr    aNull// "null"
0x1996a4  ldstr    aDashboard_0// "Dashboard"
0x1996a9  ldarg.2
0x1996aa  call     class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo> Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::GenerateDependentComponentsForSingleRibbonContext(string entityLogicalName, string ribbonContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1996af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1996b4  ldloc.s  6
0x1996b6  ldarg.2
0x1996b7  call     void Microsoft.Crm.ObjectModel.RibbonMetadata.RibbonClientMetadataHelper::UpdateRibbonRuntimeDependencies(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.ObjectModel.DependentComponentInfo> componentInfoList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1996bc  ldarg.2
0x1996bd  ldstr    aSolutionUninst// "Solution Uninstall"
0x1996c2  ldloc.s  4
0x1996c4  ldstr    asc_24F76C// ""
0x1996c9  ldstr    asc_24F76C// ""
0x1996ce  ldstr    a01// "{0}:{1}"
0x1996d3  ldstr    aCompletedUpdat// "Completed updating Ribbon Metadata at s"...
0x1996d8  ldloc.s  4
0x1996da  call     string [mscorlib]System.String::Format(string, object, object)
0x1996df  ldc.i4.1
0x1996e0  ldloc.s  7
0x1996e2  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x1996e7  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x1996ec  leave    loc_199787
0x1996f1  stloc.s  0xB
0x1996f3  ldc.i4.1
0x1996f4  stloc.2
0x1996f5  ldloc.s  0xB
0x1996f7  callvirt instance string [mscorlib]System.Object::ToString()
0x1996fc  stloc.0
0x1996fd  ldloc.s  0xB
0x1996ff  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x199704  stloc.s  0xC
0x199706  ldloc.s  0xC
0x199708  brfalse.s loc_199712
0x19970a  ldloc.s  0xC
0x19970c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x199711  stloc.1
0x199712  ldarg.2
0x199713  ldstr    aSolutionUninst// "Solution Uninstall"
0x199718  ldloc.s  4
0x19971a  ldstr    asc_24F76C// ""
0x19971f  ldstr    asc_24F76C// ""
0x199724  ldstr    a01// "{0}:{1}"
0x199729  ldstr    aFailedUpdating// "Failed updating Ribbon Metadata at solu"...
0x19972e  ldloc.s  0xB
0x199730  callvirt instance string [mscorlib]System.Object::ToString()
0x199735  ldloc.s  0xB
0x199737  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x19973c  call     string [mscorlib]System.String::Concat(string, string)
0x199741  call     string [mscorlib]System.String::Format(string, object, object)
0x199746  ldc.i4.0
0x199747  ldloc.s  7
0x199749  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x19974e  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.MetadataTelemetry::RibbonMetadataGenerationOperationLog(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, string, string, string, string, bool, int64)
0x199753  rethrow
0x199755  call     class Microsoft.Crm.ObjectModel.SolutionTelemetryEvents Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x19975a  ldarg.2
0x19975b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x199760  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x199765  ldloc.s  4
0x199767  ldstr    asc_24F050// ","
0x19976c  ldloc.3
0x19976d  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x199772  call     string [mscorlib]System.String::Join(string, string[])
0x199777  ldloc.2
0x199778  ldloc.s  7
0x19977a  callvirt instance int64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::get_ElapsedMilliseconds()
0x19977f  ldloc.0
0x199780  ldloc.1
0x199781  callvirt instance void Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::RibbonClientMetadataUpdateCompleted(valuetype [mscorlib]System.Guid organizationId, string applicationVersion, string solutionName, string impactedEntities, bool hasFailed, int64 executionTime, string exceptionMessage, int32 errorCode)
0x199786  endfinally
0x199787  ret
```
