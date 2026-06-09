# Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityPropertyImplementation

- ea: `0x12fe0`
- end: `0x130e7`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationEntityPropertyImplementation`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x32170`

## callees

- `0xf740`
- `0x12fe0`
- `0x18fd0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x22a50`
- `0x24e60`
- `0x28b60`
- `0x28bb0`
- `0x28f60`
- `0x28f80`

## string_xrefs

- `0x13090`: `CrmODataGetPropertyCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12fe0  ldarg.0
0x12fe1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12fe6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x12feb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12ff0  stloc.0
0x12ff1  ldarg.0
0x12ff2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12ff7  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12ffc  stloc.1
0x12ffd  ldarg.0
0x12ffe  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x13003  ldarg.0
0x13004  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x13009  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1300e  stloc.2
0x1300f  ldarg.0
0x13010  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x13015  call     string Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCastNavigationEntityName(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1301a  stloc.3
0x1301b  ldarg.1
0x1301c  ldarg.0
0x1301d  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x13022  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x13027  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::IsMetadataEntity()
0x1302c  brtrue.s loc_13044
0x1302e  ldc.i4   0x195
0x13033  ldstr    aThisMethodIsSu// "This method is supported only for metad"...
0x13038  ldc.i4.0
0x13039  newarr   [mscorlib]System.Object
0x1303e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x13043  throw
0x13044  ldloc.2
0x13045  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1304a  brfalse.s loc_13074
0x1304c  ldloc.2
0x1304d  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x13052  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x13057  brfalse.s loc_13074
0x13059  ldarg.0
0x1305a  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1305f  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x13064  ldloc.2
0x13065  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1306a  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1306f  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x13074  ldarg.0
0x13075  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x1307a  ldloc.1
0x1307b  ldarg.1
0x1307c  ldarg.2
0x1307d  ldarg.3
0x1307e  ldarg.s  4
0x13080  ldloc.3
0x13081  ldloc.2
0x13082  ldarg.s  5
0x13084  callvirt instance object Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEntityMetadataNavigationProperty(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityName, string entityId, string navigation, string navigationPropertyId, string derivedAttributeName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions, string navigationProperty)
0x13089  stloc.s  4
0x1308b  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x13090  ldstr    aCrmodatagetpro// "CrmODataGetPropertyCompleted"
0x13095  ldarg.1
0x13096  ldstr    aGet// "get"
0x1309b  ldstr    aPropertyname// "propertyName"
0x130a0  ldarg.s  5
0x130a2  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x130a7  ldloc.0
0x130a8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x130ad  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x130b2  ldloc.s  4
0x130b4  brtrue.s loc_130C3
0x130b6  ldloc.1
0x130b7  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x130bc  ldc.i4.0
0x130bd  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x130c2  ret
0x130c3  ldarg.0
0x130c4  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x130c9  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetValueSegment(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x130ce  brfalse.s loc_130DE
0x130d0  ldarg.0
0x130d1  ldloc.s  4
0x130d3  callvirt instance string [mscorlib]System.Object::ToString()
0x130d8  callvirt T0x2B000078
0x130dd  ret
0x130de  ldarg.0
0x130df  ldloc.s  4
0x130e1  callvirt T0x2B00006B
0x130e6  ret
```
