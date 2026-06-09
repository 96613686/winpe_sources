# Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityImplementation

- ea: `0x12f30`
- end: `0x12fd5`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityImplementation`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x32110`

## callees

- `0x12f30`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x22930`
- `0x28b60`
- `0x28bb0`
- `0x28f60`

## string_xrefs

- `0x12fb5`: `CrmODataGetEntityCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12f30  ldarg.0
0x12f31  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12f36  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x12f3b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12f40  stloc.0
0x12f41  ldarg.0
0x12f42  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12f47  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12f4c  stloc.1
0x12f4d  ldarg.0
0x12f4e  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12f53  ldarg.0
0x12f54  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12f59  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12f5e  stloc.2
0x12f5f  ldarg.0
0x12f60  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12f65  call     string Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCastNavigationEntityName(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12f6a  stloc.3
0x12f6b  ldarg.0
0x12f6c  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x12f71  ldloc.1
0x12f72  ldarg.1
0x12f73  ldarg.2
0x12f74  ldarg.3
0x12f75  ldarg.s  4
0x12f77  ldloc.3
0x12f78  ldloc.2
0x12f79  callvirt instance class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEntityMetadataNavigation(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityName, string entityId, string navigationPropertyName, string navigationPropertyId, string derivedAttributeName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x12f7e  stloc.s  4
0x12f80  ldloc.2
0x12f81  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12f86  brfalse.s loc_12FB0
0x12f88  ldloc.2
0x12f89  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12f8e  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x12f93  brfalse.s loc_12FB0
0x12f95  ldarg.0
0x12f96  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12f9b  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x12fa0  ldloc.2
0x12fa1  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12fa6  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x12fab  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x12fb0  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12fb5  ldstr    aCrmodatagetent// "CrmODataGetEntityCompleted"
0x12fba  ldarg.1
0x12fbb  ldstr    aGet// "get"
0x12fc0  ldnull
0x12fc1  ldloc.0
0x12fc2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12fc7  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12fcc  ldarg.0
0x12fcd  ldloc.s  4
0x12fcf  callvirt T0x2B000073
0x12fd4  ret
```
