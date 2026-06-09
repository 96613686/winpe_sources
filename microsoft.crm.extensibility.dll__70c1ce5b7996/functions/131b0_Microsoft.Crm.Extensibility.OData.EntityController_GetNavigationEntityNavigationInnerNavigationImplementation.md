# Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityNavigationInnerNavigationImplementation

- ea: `0x131b0`
- end: `0x13299`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityNavigationInnerNavigationImplementation`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x32230`

## callees

- `0x131b0`
- `0x17630`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x22d40`
- `0x28b60`
- `0x28bb0`
- `0x28f60`

## string_xrefs

- `0x13279`: `CrmODataGetEntityCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x131b0  ldarg.0
0x131b1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x131b6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x131bb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x131c0  stloc.0
0x131c1  ldarg.0
0x131c2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x131c7  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x131cc  stloc.1
0x131cd  ldarg.0
0x131ce  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x131d3  ldarg.0
0x131d4  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x131d9  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x131de  stloc.2
0x131df  ldarg.0
0x131e0  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x131e5  call     string Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCastNavigationEntityName(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x131ea  stloc.3
0x131eb  ldarg.0
0x131ec  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x131f1  ldloc.1
0x131f2  ldarg.1
0x131f3  ldarg.2
0x131f4  ldarg.3
0x131f5  ldarg.s  4
0x131f7  ldloc.3
0x131f8  ldarg.s  5
0x131fa  ldarg.s  6
0x131fc  ldnull
0x131fd  callvirt instance object Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveNavigationEntityNavigationInnerNavigation(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityName, string entityId, string navigationPropertyName, string navigationPropertyId, string derivedAttributeName, string innerNavigation, string innerNavigationNavigation, [opt] string innerNavigationNavigationKey)
0x13202  stloc.s  4
0x13204  ldloc.2
0x13205  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1320a  brfalse.s loc_13234
0x1320c  ldloc.2
0x1320d  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x13212  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x13217  brfalse.s loc_13234
0x13219  ldarg.0
0x1321a  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1321f  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x13224  ldloc.2
0x13225  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1322a  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1322f  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x13234  ldloc.2
0x13235  callvirt instance class [System.Web.OData]System.Web.OData.Query.CountQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Count()
0x1323a  brfalse.s loc_13274
0x1323c  ldloc.2
0x1323d  callvirt instance class [System.Web.OData]System.Web.OData.Query.CountQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_Count()
0x13242  callvirt instance bool [System.Web.OData]System.Web.OData.Query.CountQueryOption::get_Value()
0x13247  brfalse.s loc_13274
0x13249  ldloc.s  4
0x1324b  isinst   Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection
0x13250  brfalse.s loc_13274
0x13252  ldarg.0
0x13253  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x13258  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x1325d  ldloc.s  4
0x1325f  castclass Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection
0x13264  callvirt instance int32 Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_TotalRecordCount()
0x13269  conv.i8
0x1326a  newobj   instance void valuetype [mscorlib]System.Nullable`1<int64>::.ctor(var<u1>)
0x1326f  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_TotalCount(valuetype [mscorlib]System.Nullable`1<int64>)
0x13274  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x13279  ldstr    aCrmodatagetent// "CrmODataGetEntityCompleted"
0x1327e  ldarg.1
0x1327f  ldstr    aGet// "get"
0x13284  ldnull
0x13285  ldloc.0
0x13286  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x1328b  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x13290  ldarg.0
0x13291  ldloc.s  4
0x13293  callvirt T0x2B00006B
0x13298  ret
```
