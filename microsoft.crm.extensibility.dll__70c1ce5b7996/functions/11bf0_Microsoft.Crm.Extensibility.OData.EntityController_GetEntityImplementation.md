# Microsoft.Crm.Extensibility.OData.EntityController::GetEntityImplementation

- ea: `0x11bf0`
- end: `0x11c8a`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetEntityImplementation`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x319b0`

## callees

- `0x11500`
- `0x11540`
- `0x11bf0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x28b60`
- `0x28bb0`

## string_xrefs

- `0x11c6a`: `CrmODataGetEntityCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x11bf0  ldarg.0
0x11bf1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x11bf6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x11bfb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x11c00  stloc.0
0x11c01  ldarg.0
0x11c02  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11c07  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x11c0c  stloc.1
0x11c0d  ldarg.0
0x11c0e  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11c13  ldarg.0
0x11c14  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11c19  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11c1e  stloc.2
0x11c1f  ldarg.1
0x11c20  ldarg.0
0x11c21  ldarg.1
0x11c22  ldind.ref
0x11c23  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x11c28  stind.ref
0x11c29  ldarg.0
0x11c2a  ldarg.1
0x11c2b  ldind.ref
0x11c2c  ldarg.2
0x11c2d  ldloc.1
0x11c2e  ldloc.2
0x11c2f  call     instance class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EntityController::GetEntityInternal(string entityName, string key, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x11c34  stloc.3
0x11c35  ldloc.2
0x11c36  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x11c3b  brfalse.s loc_11C65
0x11c3d  ldloc.2
0x11c3e  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x11c43  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x11c48  brfalse.s loc_11C65
0x11c4a  ldarg.0
0x11c4b  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11c50  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x11c55  ldloc.2
0x11c56  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x11c5b  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x11c60  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x11c65  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x11c6a  ldstr    aCrmodatagetent// "CrmODataGetEntityCompleted"
0x11c6f  ldarg.1
0x11c70  ldind.ref
0x11c71  ldstr    aGet// "get"
0x11c76  ldnull
0x11c77  ldloc.0
0x11c78  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x11c7d  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x11c82  ldarg.0
0x11c83  ldloc.3
0x11c84  callvirt T0x2B000073
0x11c89  ret
```
