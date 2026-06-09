# Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityNavigationImplementation

- ea: `0x130f0`
- end: `0x131a8`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityNavigationImplementation`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x321d0`

## callees

- `0x130f0`
- `0x18fd0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x22bb0`
- `0x24e60`
- `0x28b60`
- `0x28bb0`
- `0x28f60`

## string_xrefs

- `0x13188`: `CrmODataGetEntityCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x130f0  ldarg.0
0x130f1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x130f6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x130fb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x13100  stloc.0
0x13101  ldarg.0
0x13102  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x13107  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1310c  stloc.1
0x1310d  ldarg.0
0x1310e  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x13113  ldarg.0
0x13114  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x13119  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1311e  stloc.2
0x1311f  ldarg.0
0x13120  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x13125  call     string Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCastNavigationEntityName(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1312a  stloc.3
0x1312b  ldarg.0
0x1312c  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x13131  ldloc.1
0x13132  ldarg.1
0x13133  ldarg.2
0x13134  ldarg.3
0x13135  ldarg.s  4
0x13137  ldloc.3
0x13138  ldarg.s  5
0x1313a  ldloc.2
0x1313b  callvirt instance class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveNavigationEntityNavigation(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityName, string entityId, string navigationPropertyName, string navigationPropertyId, string derivedAttributeName, string innerNavigation, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x13140  stloc.s  4
0x13142  ldloc.s  4
0x13144  brtrue.s loc_13153
0x13146  ldloc.1
0x13147  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1314c  ldc.i4.0
0x1314d  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x13152  ret
0x13153  ldloc.2
0x13154  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x13159  brfalse.s loc_13183
0x1315b  ldloc.2
0x1315c  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x13161  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x13166  brfalse.s loc_13183
0x13168  ldarg.0
0x13169  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1316e  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x13173  ldloc.2
0x13174  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x13179  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1317e  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x13183  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x13188  ldstr    aCrmodatagetent// "CrmODataGetEntityCompleted"
0x1318d  ldarg.1
0x1318e  ldstr    aGet// "get"
0x13193  ldnull
0x13194  ldloc.0
0x13195  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x1319a  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x1319f  ldarg.0
0x131a0  ldloc.s  4
0x131a2  callvirt T0x2B000073
0x131a7  ret
```
