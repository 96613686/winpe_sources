# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::SelectControllerImplementation

- ea: `0x2dbe0`
- end: `0x2ddab`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::SelectControllerImplementation`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x35050`

## callees

- `0x18e90`
- `0x18ed0`
- `0x29140`
- `0x29180`
- `0x2db00`
- `0x2dbe0`
- `0x2de50`
- `0x2df50`
- `0x2e240`
- `0x2e450`

## string_xrefs

- `0x2dc11`: `MaxDataServiceVersion`
- `0x2dc23`: `MaxDataServiceVersion`

## pseudocode

```c

```

## disassembly

```asm
0x2dbe0  ldarg.1
0x2dbe1  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dbe6  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0x2dbeb  ldc.i4.0
0x2dbec  ble.s    loc_2DC0B
0x2dbee  ldarg.1
0x2dbef  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dbf4  call     T0x2B0000EA
0x2dbf9  isinst   Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataUnresolvedPathSegment
0x2dbfe  brfalse.s loc_2DC0B
0x2dc00  ldstr    aCrmodataerror// "CrmODataError"
0x2dc05  stloc.3
0x2dc06  leave    loc_2DDA9
0x2dc0b  ldarg.2
0x2dc0c  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x2dc11  ldstr    aMaxdataservice// "MaxDataServiceVersion"
0x2dc16  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Contains(string)
0x2dc1b  brfalse.s loc_2DC2E
0x2dc1d  ldarg.2
0x2dc1e  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x2dc23  ldstr    aMaxdataservice// "MaxDataServiceVersion"
0x2dc28  callvirt instance bool [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Remove(string)
0x2dc2d  pop
0x2dc2e  ldarg.2
0x2dc2f  call     class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataRequestHeader(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2dc34  stloc.0
0x2dc35  ldarg.0
0x2dc36  ldarg.2
0x2dc37  ldloca.s 1
0x2dc39  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::GetApiVersionFromRequest(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, [out] string& echoVersion)
0x2dc3e  stloc.2
0x2dc3f  ldarg.2
0x2dc40  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x2dc45  ldstr    aCrmWebapiVersi// "crm-webapi-version"
0x2dc4a  ldloc.1
0x2dc4b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x2dc50  ldloc.2
0x2dc51  ldnull
0x2dc52  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x2dc57  brfalse.s loc_2DC72
0x2dc59  ldarg.2
0x2dc5a  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2dc5f  ldarg.0
0x2dc60  ldloc.2
0x2dc61  ldarg.2
0x2dc62  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2dc67  ldloc.1
0x2dc68  call     instance class [mscorlib]System.Version Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::ValidateApiVersion(class [mscorlib]System.Version version, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, string versionStr)
0x2dc6d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_SdkClientVersion(class [mscorlib]System.Version)
0x2dc72  ldloc.0
0x2dc73  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_AreSolutionVersionsSpecified()
0x2dc78  brfalse.s loc_2DC87
0x2dc7a  ldarg.0
0x2dc7b  ldloc.0
0x2dc7c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Extensibility.OData.SolutionDependency> Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_SolutionsDetails()
0x2dc81  call     instance bool Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::ValidateSolutionVersions(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Extensibility.OData.SolutionDependency> solutionDetails)
0x2dc86  pop
0x2dc87  ldarg.1
0x2dc88  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dc8d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0x2dc92  brtrue.s loc_2DCA1
0x2dc94  ldarg.0
0x2dc95  call     instance void Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::SetUserLanguageCode()
0x2dc9a  ldnull
0x2dc9b  stloc.3
0x2dc9c  leave    loc_2DDA9
0x2dca1  ldarg.1
0x2dca2  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dca7  call     T0x2B00010C
0x2dcac  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.MetadataSegment
0x2dcb1  brfalse.s loc_2DCC7
0x2dcb3  ldarg.0
0x2dcb4  ldarg.2
0x2dcb5  call     instance void Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::ValidateMetadataRequest(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x2dcba  ldarg.0
0x2dcbb  call     instance void Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::SetUserLanguageCode()
0x2dcc0  ldnull
0x2dcc1  stloc.3
0x2dcc2  leave    loc_2DDA9
0x2dcc7  ldarg.1
0x2dcc8  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dccd  call     T0x2B0000EA
0x2dcd2  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationSegment
0x2dcd7  brtrue.s loc_2DD37
0x2dcd9  ldarg.1
0x2dcda  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dcdf  call     T0x2B0000EA
0x2dce4  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment
0x2dce9  brtrue.s loc_2DD37
0x2dceb  ldarg.1
0x2dcec  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dcf1  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0x2dcf6  ldc.i4.2
0x2dcf7  blt.s    loc_2DD55
0x2dcf9  ldarg.1
0x2dcfa  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dcff  ldarg.1
0x2dd00  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dd05  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0x2dd0a  ldc.i4.2
0x2dd0b  sub
0x2dd0c  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0x2dd11  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmFunction
0x2dd16  brtrue.s loc_2DD37
0x2dd18  ldarg.1
0x2dd19  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dd1e  ldarg.1
0x2dd1f  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dd24  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0x2dd29  ldc.i4.2
0x2dd2a  sub
0x2dd2b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Item(!!T0)
0x2dd30  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmFunctionImport
0x2dd35  brfalse.s loc_2DD55
0x2dd37  ldarg.2
0x2dd38  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x2dd3d  ldstr    aOdataShouldrec// "OData.ShouldRecalculateSelectExpandNode"
0x2dd42  ldc.i4.1
0x2dd43  box      [mscorlib]System.Boolean
0x2dd48  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2dd4d  ldstr    aAction// "Action"
0x2dd52  stloc.3
0x2dd53  leave.s  loc_2DDA9
0x2dd55  ldarg.1
0x2dd56  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dd5b  call     T0x2B00010C
0x2dd60  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.EntitySetSegment
0x2dd65  brfalse.s loc_2DD6F
0x2dd67  ldstr    aEntity_0// "Entity"
0x2dd6c  stloc.3
0x2dd6d  leave.s  loc_2DDA9
0x2dd6f  ldarg.1
0x2dd70  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x2dd75  call     T0x2B00010C
0x2dd7a  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.SingletonSegment
0x2dd7f  brfalse.s loc_2DD89
0x2dd81  ldstr    aSingleton// "Singleton"
0x2dd86  stloc.3
0x2dd87  leave.s  loc_2DDA9
0x2dd89  leave.s  loc_2DDA7
0x2dd8b  stloc.s  4
0x2dd8d  ldarg.2
0x2dd8e  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Properties()
0x2dd93  ldstr    aRoutingexcepti// "RoutingException"
0x2dd98  ldloc.s  4
0x2dd9a  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x2dd9f  ldstr    aCrmodataerror// "CrmODataError"
0x2dda4  stloc.3
0x2dda5  leave.s  loc_2DDA9
0x2dda7  ldnull
0x2dda8  ret
0x2dda9  ldloc.3
0x2ddaa  ret
```
