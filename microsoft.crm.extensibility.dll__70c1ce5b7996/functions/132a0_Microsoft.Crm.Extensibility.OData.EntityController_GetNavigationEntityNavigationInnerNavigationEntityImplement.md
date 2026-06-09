# Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityNavigationInnerNavigationEntityImplementation

- ea: `0x132a0`
- end: `0x1334a`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityNavigationInnerNavigationEntityImplementation`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x322a0`

## callees

- `0x132a0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x22d40`
- `0x28b60`
- `0x28bb0`
- `0x28f60`

## string_xrefs

- `0x1332a`: `CrmODataGetEntityCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x132a0  ldarg.0
0x132a1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x132a6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x132ab  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x132b0  stloc.0
0x132b1  ldarg.0
0x132b2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x132b7  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x132bc  stloc.1
0x132bd  ldarg.0
0x132be  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x132c3  ldarg.0
0x132c4  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x132c9  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x132ce  stloc.2
0x132cf  ldarg.0
0x132d0  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x132d5  call     string Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCastNavigationEntityName(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x132da  stloc.3
0x132db  ldarg.0
0x132dc  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x132e1  ldloc.1
0x132e2  ldarg.1
0x132e3  ldarg.2
0x132e4  ldarg.3
0x132e5  ldarg.s  4
0x132e7  ldloc.3
0x132e8  ldarg.s  5
0x132ea  ldarg.s  6
0x132ec  ldarg.s  7
0x132ee  callvirt instance object Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveNavigationEntityNavigationInnerNavigation(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityName, string entityId, string navigationPropertyName, string navigationPropertyId, string derivedAttributeName, string innerNavigation, string innerNavigationNavigation, [opt] string innerNavigationNavigationKey)
0x132f3  stloc.s  4
0x132f5  ldloc.2
0x132f6  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x132fb  brfalse.s loc_13325
0x132fd  ldloc.2
0x132fe  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x13303  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x13308  brfalse.s loc_13325
0x1330a  ldarg.0
0x1330b  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x13310  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x13315  ldloc.2
0x13316  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1331b  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x13320  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x13325  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x1332a  ldstr    aCrmodatagetent// "CrmODataGetEntityCompleted"
0x1332f  ldarg.1
0x13330  ldstr    aGet// "get"
0x13335  ldnull
0x13336  ldloc.0
0x13337  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x1333c  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x13341  ldarg.0
0x13342  ldloc.s  4
0x13344  callvirt T0x2B00006B
0x13349  ret
```
