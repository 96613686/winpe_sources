# Microsoft.Crm.Extensibility.OData.EntityController::PostEntitySetImplementation

- ea: `0x12150`
- end: `0x1227f`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PostEntitySetImplementation`
- size: `303`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x31b80`

## callees

- `0xfbf0`
- `0x114e0`
- `0x11540`
- `0x116c0`
- `0x12150`
- `0x18fd0`
- `0x190a0`
- `0x19ac0`
- `0x19c40`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x24e60`
- `0x28b60`
- `0x28bb0`

## string_xrefs

- `0x12195`: `CrmODataPostEntitySetCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12150  ldarg.0
0x12151  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12156  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x1215b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12160  stloc.0
0x12161  ldarg.0
0x12162  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12167  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1216c  stloc.1
0x1216d  ldarg.1
0x1216e  ldarg.0
0x1216f  ldarg.1
0x12170  ldind.ref
0x12171  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntitySetNameIfAvailable(string entitySetName)
0x12176  stind.ref
0x12177  ldarg.1
0x12178  ldind.ref
0x12179  ldarg.0
0x1217a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x1217f  call     string Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityNameFromCollectionName(string entityCollectionName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12184  stloc.2
0x12185  ldarg.0
0x12186  ldloc.1
0x12187  ldloc.2
0x12188  ldarg.2
0x12189  ldc.i4.0
0x1218a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.EntityController::PostEntitySetInternal(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject, [opt] bool isUpsert)
0x1218f  stloc.3
0x12190  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12195  ldstr    aCrmodataposten// "CrmODataPostEntitySetCompleted"
0x1219a  ldarg.1
0x1219b  ldind.ref
0x1219c  ldstr    aPost// "post"
0x121a1  ldnull
0x121a2  ldloc.0
0x121a3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x121a8  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x121ad  ldloc.1
0x121ae  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x121b3  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferReturnSpecified()
0x121b8  brfalse  loc_12272
0x121bd  ldloc.1
0x121be  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x121c3  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferReturn()
0x121c8  ldstr    aRepresentation// "representation"
0x121cd  callvirt instance bool [mscorlib]System.String::Equals(string)
0x121d2  brfalse  loc_12272
0x121d7  ldarg.0
0x121d8  ldloc.2
0x121d9  ldloca.s 3
0x121db  constrained. [mscorlib]System.Guid
0x121e1  callvirt instance string [mscorlib]System.Object::ToString()
0x121e6  ldloc.1
0x121e7  ldarg.0
0x121e8  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x121ed  ldarg.0
0x121ee  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x121f3  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x121f8  call     instance class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EntityController::GetEntityInternal(string entityName, string key, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x121fd  stloc.s  4
0x121ff  ldarg.0
0x12200  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12205  ldarg.0
0x12206  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x1220b  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12210  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12215  brfalse.s loc_1225F
0x12217  ldarg.0
0x12218  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1221d  ldarg.0
0x1221e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12223  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12228  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x1222d  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x12232  brfalse.s loc_1225F
0x12234  ldarg.0
0x12235  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1223a  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x1223f  ldarg.0
0x12240  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12245  ldarg.0
0x12246  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x1224b  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12250  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12255  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x1225a  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x1225f  ldloc.1
0x12260  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12265  ldloc.s  4
0x12267  ldc.i4   0xC9
0x1226c  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetReturnRepresentationODataResponse(object eobj, valuetype [System]System.Net.HttpStatusCode statusCode)
0x12271  ret
0x12272  ldloc.1
0x12273  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12278  ldc.i4.0
0x12279  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x1227e  ret
```
