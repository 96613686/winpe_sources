# Microsoft.Crm.Extensibility.OData.EntityController::PatchEntityImplementation

- ea: `0x11c90`
- end: `0x11e0f`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PatchEntityImplementation`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x31a00`

## callees

- `0x11500`
- `0x11540`
- `0x11770`
- `0x11a80`
- `0x11c90`
- `0x18fd0`
- `0x190a0`
- `0x19ac0`
- `0x19c40`
- `0x1e480`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x20de0`
- `0x23e80`
- `0x24e60`
- `0x24e70`
- `0x28b60`
- `0x28bb0`

## string_xrefs

- `0x11cb7`: `GET,PUT,DELETE`
- `0x11d05`: `CrmODataPatchEntityCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x11c90  ldarg.0
0x11c91  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x11c96  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x11c9b  ldarg.1
0x11c9c  ldind.ref
0x11c9d  ldarg.0
0x11c9e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11ca3  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11ca8  brfalse.s loc_11CC2
0x11caa  ldarg.0
0x11cab  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x11cb0  ldarg.1
0x11cb1  ldind.ref
0x11cb2  call     string [mscorlib]System.String::Format(string, object)
0x11cb7  ldstr    aGetPutDelete// "GET,PUT,DELETE"
0x11cbc  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x11cc1  throw
0x11cc2  ldarg.3
0x11cc3  ldarg.0
0x11cc4  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11cc9  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x11cce  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidatePatchInputProperties(class [System.Web.OData]System.Web.OData.EdmEntityObject entityDelta, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext crmODataExecutionContext)
0x11cd3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x11cd8  stloc.0
0x11cd9  ldarg.0
0x11cda  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11cdf  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x11ce4  stloc.1
0x11ce5  ldarg.1
0x11ce6  ldarg.0
0x11ce7  ldarg.1
0x11ce8  ldind.ref
0x11ce9  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x11cee  stind.ref
0x11cef  ldarg.0
0x11cf0  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x11cf5  ldloc.1
0x11cf6  ldarg.1
0x11cf7  ldind.ref
0x11cf8  ldarg.2
0x11cf9  ldarg.3
0x11cfa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateEdmEntity(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject)
0x11cff  stloc.2
0x11d00  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x11d05  ldstr    aCrmodatapatche// "CrmODataPatchEntityCompleted"
0x11d0a  ldarg.1
0x11d0b  ldind.ref
0x11d0c  ldstr    aPatch// "patch"
0x11d11  ldnull
0x11d12  ldloc.0
0x11d13  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x11d18  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x11d1d  ldloc.1
0x11d1e  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_IsRecordCreatedFromUpsertOperation()
0x11d23  brfalse  loc_11DF2
0x11d28  ldloc.1
0x11d29  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x11d2e  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferReturnSpecified()
0x11d33  brfalse  loc_11DE5
0x11d38  ldloc.1
0x11d39  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x11d3e  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_PreferReturn()
0x11d43  ldstr    aRepresentation// "representation"
0x11d48  callvirt instance bool [mscorlib]System.String::Equals(string)
0x11d4d  brfalse  loc_11DE5
0x11d52  ldarg.0
0x11d53  ldarg.1
0x11d54  ldind.ref
0x11d55  ldarg.2
0x11d56  callvirt instance string [mscorlib]System.Object::ToString()
0x11d5b  ldloc.1
0x11d5c  ldarg.0
0x11d5d  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11d62  ldarg.0
0x11d63  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11d68  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11d6d  call     instance class [System.Web.OData]System.Web.OData.EdmEntityObject Microsoft.Crm.Extensibility.OData.EntityController::GetEntityInternal(string entityName, string key, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x11d72  stloc.3
0x11d73  ldarg.0
0x11d74  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11d79  ldarg.0
0x11d7a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11d7f  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11d84  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x11d89  brfalse.s loc_11DD3
0x11d8b  ldarg.0
0x11d8c  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11d91  ldarg.0
0x11d92  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11d97  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11d9c  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x11da1  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x11da6  brfalse.s loc_11DD3
0x11da8  ldarg.0
0x11da9  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11dae  call     class [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageExtensions::ODataProperties(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x11db3  ldarg.0
0x11db4  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11db9  ldarg.0
0x11dba  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11dbf  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11dc4  callvirt instance class [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption [System.Web.OData]System.Web.OData.Query.ODataQueryOptions::get_SelectExpand()
0x11dc9  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause [System.Web.OData]System.Web.OData.Query.SelectExpandQueryOption::get_SelectExpandClause()
0x11dce  callvirt instance void [System.Web.OData]System.Web.OData.Extensions.HttpRequestMessageProperties::set_SelectExpandClause(class [Microsoft.OData.Core]Microsoft.OData.UriParser.SelectExpandClause)
0x11dd3  ldloc.1
0x11dd4  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x11dd9  ldloc.3
0x11dda  ldc.i4   0xC9
0x11ddf  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetReturnRepresentationODataResponse(object eobj, valuetype [System]System.Net.HttpStatusCode statusCode)
0x11de4  ret
0x11de5  ldloc.1
0x11de6  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x11deb  ldc.i4.0
0x11dec  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x11df1  ret
0x11df2  ldarg.0
0x11df3  ldarg.1
0x11df4  ldind.ref
0x11df5  ldloc.2
0x11df6  box      [mscorlib]System.Guid
0x11dfb  ldarg.1
0x11dfc  ldind.ref
0x11dfd  ldarg.0
0x11dfe  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11e03  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11e08  ldloc.1
0x11e09  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::HandlePatchAndPutActionExecuteTransactionResponse(string entityName, object key, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x11e0e  ret
```
