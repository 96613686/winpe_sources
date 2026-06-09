# Microsoft.Crm.Extensibility.OData.EntityController::GetEntitySetImplementation

- ea: `0x11f10`
- end: `0x12149`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetEntitySetImplementation`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x31b10`

## callees

- `0x11520`
- `0x11570`
- `0x11f10`
- `0x17630`
- `0x19ba0`
- `0x1d5e0`
- `0x1d660`
- `0x1d750`
- `0x1eea0`
- `0x1ef70`
- `0x1f6b0`
- `0x20d50`
- `0x21290`
- `0x212e0`
- `0x21330`
- `0x24780`
- `0x24e60`
- `0x28b60`
- `0x28bb0`
- `0x28c90`
- `0x28e40`
- `0x28fa0`
- `0x28fe0`

## string_xrefs

- `0x120f2`: `CrmODataGetEntitySetCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x11f10  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x11f15  stloc.0
0x11f16  ldnull
0x11f17  stloc.1
0x11f18  ldnull
0x11f19  stloc.2
0x11f1a  ldnull
0x11f1b  stloc.3
0x11f1c  ldnull
0x11f1d  stloc.s  4
0x11f1f  ldnull
0x11f20  stloc.s  5
0x11f22  ldnull
0x11f23  stloc.s  6
0x11f25  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x11f2a  pop
0x11f2b  ldarg.0
0x11f2c  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x11f31  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x11f36  ldarg.0
0x11f37  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11f3c  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x11f41  stloc.1
0x11f42  ldarg.0
0x11f43  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11f48  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::QueryParameterDictionary(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x11f4d  stloc.s  6
0x11f4f  ldloc.s  6
0x11f51  ldloc.1
0x11f52  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateQueryParameters(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x11f57  ldarg.0
0x11f58  ldarg.1
0x11f59  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityLogicalNameIfAvailable(string entityName)
0x11f5e  stloc.s  5
0x11f60  ldarg.0
0x11f61  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11f66  ldarg.0
0x11f67  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11f6c  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::IsCustomQueryOptionPresent(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11f71  brfalse.s loc_11FB4
0x11f73  ldstr    aRequestoption// "RequestOption"
0x11f78  ldstr    aCustomqueryopt// "CustomQueryOption"
0x11f7d  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x11f82  ldarg.0
0x11f83  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11f88  ldarg.0
0x11f89  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11f8e  call     class Microsoft.Crm.Extensibility.OData.CustomQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCustomQueryOptionForQueryView(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11f93  stloc.s  7
0x11f95  ldarg.0
0x11f96  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x11f9b  ldloc.1
0x11f9c  ldarg.1
0x11f9d  ldloc.s  5
0x11f9f  ldloc.s  7
0x11fa1  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityCollection(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityCollectionName, string castedEntityName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x11fa6  stloc.3
0x11fa7  ldloc.s  7
0x11fa9  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption Microsoft.Crm.Extensibility.OData.CustomQueryOptions::get_SelectExpandQueryOption()
0x11fae  stloc.2
0x11faf  br       loc_120C1
0x11fb4  ldloc.s  6
0x11fb6  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsChangeTrackingQuery(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters)
0x11fbb  brfalse.s loc_11FFF
0x11fbd  ldstr    aRequestoption// "RequestOption"
0x11fc2  ldstr    aChangetracking// "ChangeTrackingQuery"
0x11fc7  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x11fcc  ldarg.0
0x11fcd  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11fd2  ldarg.0
0x11fd3  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11fd8  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11fdd  stloc.s  8
0x11fdf  ldarg.0
0x11fe0  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x11fe5  ldloc.1
0x11fe6  ldarg.1
0x11fe7  ldloc.s  8
0x11fe9  ldloc.s  6
0x11feb  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmEdmChangedObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityChanges(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityCollectionName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters)
0x11ff0  stloc.s  4
0x11ff2  ldloc.s  8
0x11ff4  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x11ff9  stloc.2
0x11ffa  br       loc_120C1
0x11fff  ldloc.1
0x12000  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12005  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferTrackChangesHeaderSpecified()
0x1200a  brtrue.s loc_12015
0x1200c  ldloc.s  6
0x1200e  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsTrackingEnabled(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters)
0x12013  brfalse.s loc_12065
0x12015  ldloc.1
0x12016  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1201b  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferTrackChangesHeaderSpecified()
0x12020  ldloc.s  6
0x12022  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SkipIfInvalidHeaderState(bool changeTrackingHeader, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters)
0x12027  brtrue.s loc_12065
0x12029  ldstr    aRequestoption// "RequestOption"
0x1202e  ldstr    aPrefertrackcha// "PreferTrackChangesHeader"
0x12033  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x12038  ldarg.0
0x12039  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1203e  ldarg.0
0x1203f  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12044  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12049  stloc.s  9
0x1204b  ldarg.0
0x1204c  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x12051  ldloc.1
0x12052  ldarg.1
0x12053  ldloc.s  9
0x12055  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::RetrieveEdmEntityInitialLoad(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityCollectionName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x1205a  stloc.3
0x1205b  ldloc.s  9
0x1205d  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12062  stloc.2
0x12063  br.s     loc_120C1
0x12065  ldarg.0
0x12066  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1206b  ldarg.0
0x1206c  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12071  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12076  stloc.s  0xA
0x12078  ldarg.0
0x12079  ldarg.1
0x1207a  ldloc.s  5
0x1207c  ldloc.1
0x1207d  ldloc.3
0x1207e  ldloc.s  0xA
0x12080  call     instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EntityController::GetEntitySetInternal(string entitySetName, string castedEntityName, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection crmEdmEntityObjectCollection, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x12085  stloc.3
0x12086  ldloc.s  0xA
0x12088  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1208d  stloc.2
0x1208e  ldloc.s  0xA
0x12090  callvirt instance class [System.Web.OData]System.Web.OData.Query.CountQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Count()
0x12095  brfalse.s loc_120C1
0x12097  ldloc.s  0xA
0x12099  callvirt instance class [System.Web.OData]System.Web.OData.Query.CountQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Count()
0x1209e  callvirt instance bool [System.Web.OData]System.Web.OData.Query.CountQueryOption::get_Value()
0x120a3  brfalse.s loc_120C1
0x120a5  ldarg.0
0x120a6  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x120ab  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x120b0  ldloc.3
0x120b1  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_TotalRecordCount()
0x120b6  conv.i8
0x120b7  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x120bc  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_TotalCount(valuetype [mscorlib]System.Nullable`1<int64>)
0x120c1  ldloc.2
0x120c2  brfalse.s loc_120E2
0x120c4  ldloc.2
0x120c5  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x120ca  brfalse.s loc_120E2
0x120cc  ldarg.0
0x120cd  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x120d2  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x120d7  ldloc.2
0x120d8  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x120dd  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x120e2  ldarg.0
0x120e3  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x120e8  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCountSegment(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x120ed  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x120f2  ldstr    aCrmodatagetent_0// "CrmODataGetEntitySetCompleted"
0x120f7  ldarg.1
0x120f8  ldstr    aGet// "get"
0x120fd  ldnull
0x120fe  ldloc.0
0x120ff  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12104  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12109  brfalse.s loc_1212F
0x1210b  ldloc.s  6
0x1210d  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsChangeTrackingQuery(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters)
0x12112  brfalse.s loc_12122
0x12114  ldarg.0
0x12115  ldloc.s  4
0x12117  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Web.OData]System.Web.OData.IEdmChangedObject>::get_Count()
0x1211c  callvirt T0x2B000074
0x12121  ret
0x12122  ldarg.0
0x12123  ldloc.3
0x12124  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_TotalRecordCount()
0x12129  callvirt T0x2B000074
0x1212e  ret
0x1212f  ldloc.s  6
0x12131  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsChangeTrackingQuery(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParameters)
0x12136  brfalse.s loc_12141
0x12138  ldarg.0
0x12139  ldloc.s  4
0x1213b  callvirt T0x2B000075
0x12140  ret
0x12141  ldarg.0
0x12142  ldloc.3
0x12143  callvirt T0x2B000076
0x12148  ret
```
