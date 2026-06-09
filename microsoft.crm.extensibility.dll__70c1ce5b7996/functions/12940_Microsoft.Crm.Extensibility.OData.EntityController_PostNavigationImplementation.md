# Microsoft.Crm.Extensibility.OData.EntityController::PostNavigationImplementation

- ea: `0x12940`
- end: `0x12a51`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PostNavigationImplementation`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x31e70`

## callees

- `0x11500`
- `0x11730`
- `0x12940`
- `0x18fd0`
- `0x190a0`
- `0x19ac0`
- `0x19c40`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x22930`
- `0x24e60`
- `0x28b60`
- `0x28bb0`
- `0x28f60`

## string_xrefs

- `0x1297a`: `CrmODataPostNavigationCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12940  ldarg.0
0x12941  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12946  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x1294b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12950  stloc.0
0x12951  ldarg.0
0x12952  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12957  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1295c  stloc.1
0x1295d  ldarg.1
0x1295e  ldarg.0
0x1295f  ldarg.1
0x12960  ldind.ref
0x12961  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12966  stind.ref
0x12967  ldarg.0
0x12968  ldloc.1
0x12969  ldarg.1
0x1296a  ldind.ref
0x1296b  ldarg.2
0x1296c  ldarg.3
0x1296d  ldarg.s  4
0x1296f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.EntityController::PostNavigationInternal(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityIdValue, string navigationPropertyName, class [System.Web.OData]System.Web.OData.EdmEntityObject navigationEntityObject)
0x12974  stloc.2
0x12975  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x1297a  ldstr    aCrmodatapostna// "CrmODataPostNavigationCompleted"
0x1297f  ldarg.1
0x12980  ldind.ref
0x12981  ldstr    aPost// "post"
0x12986  ldstr    aNavigationname// "navigationName"
0x1298b  ldarg.3
0x1298c  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12991  ldloc.0
0x12992  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12997  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x1299c  ldarg.0
0x1299d  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x129a2  ldarg.0
0x129a3  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x129a8  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x129ad  stloc.3
0x129ae  ldarg.0
0x129af  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x129b4  call     string Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCastNavigationEntityName(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x129b9  stloc.s  4
0x129bb  ldloc.1
0x129bc  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x129c1  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferReturnSpecified()
0x129c6  brfalse.s loc_12A44
0x129c8  ldloc.1
0x129c9  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x129ce  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferReturn()
0x129d3  ldstr    aRepresentation// "representation"
0x129d8  callvirt instance bool [mscorlib]System.String::Equals(string)
0x129dd  brfalse.s loc_12A44
0x129df  ldarg.0
0x129e0  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x129e5  ldloc.1
0x129e6  ldarg.1
0x129e7  ldind.ref
0x129e8  ldarg.2
0x129e9  ldarg.3
0x129ea  ldloca.s 2
0x129ec  constrained. [mscorlib]System.Guid
0x129f2  callvirt instance string [mscorlib]System.Object::ToString()
0x129f7  ldloc.s  4
0x129f9  ldloc.3
0x129fa  callvirt instance class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::RetrieveEntityMetadataNavigation(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string entityName, string entityId, string navigationPropertyName, string navigationPropertyId, string derivedAttributeName, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x129ff  stloc.s  5
0x12a01  ldloc.3
0x12a02  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12a07  brfalse.s loc_12A31
0x12a09  ldloc.3
0x12a0a  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12a0f  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x12a14  brfalse.s loc_12A31
0x12a16  ldarg.0
0x12a17  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12a1c  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x12a21  ldloc.3
0x12a22  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x12a27  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x12a2c  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x12a31  ldloc.1
0x12a32  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12a37  ldloc.s  5
0x12a39  ldc.i4   0xC9
0x12a3e  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetReturnRepresentationODataResponse(object eobj, valuetype [System]System.Net.HttpStatusCode statusCode)
0x12a43  ret
0x12a44  ldloc.1
0x12a45  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12a4a  ldc.i4.0
0x12a4b  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12a50  ret
```
