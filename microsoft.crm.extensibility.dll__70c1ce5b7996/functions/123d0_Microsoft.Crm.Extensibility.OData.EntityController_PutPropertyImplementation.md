# Microsoft.Crm.Extensibility.OData.EntityController::PutPropertyImplementation

- ea: `0x123d0`
- end: `0x1248f`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PutPropertyImplementation`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x31c30`

## callees

- `0xf740`
- `0x11500`
- `0x11770`
- `0x11a80`
- `0x123d0`
- `0x1e5b0`
- `0x1eea0`
- `0x1ef70`
- `0x1f890`
- `0x20d50`
- `0x23e80`
- `0x28b60`

## string_xrefs

- `0x12450`: `CrmODataPutPropertyCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x123d0  ldarg.0
0x123d1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x123d6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x123db  ldarg.1
0x123dc  ldind.ref
0x123dd  ldarg.0
0x123de  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x123e3  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x123e8  brfalse.s loc_12402
0x123ea  ldarg.0
0x123eb  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x123f0  ldarg.1
0x123f1  ldind.ref
0x123f2  call     string [mscorlib]System.String::Format(string, object)
0x123f7  ldstr    aGet_0// "GET"
0x123fc  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x12401  throw
0x12402  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12407  stloc.0
0x12408  ldarg.0
0x12409  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x1240e  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12413  stloc.1
0x12414  ldarg.1
0x12415  ldarg.0
0x12416  ldarg.1
0x12417  ldind.ref
0x12418  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x1241d  stind.ref
0x1241e  ldarg.1
0x1241f  ldind.ref
0x12420  ldarg.0
0x12421  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12426  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x1242b  ldarg.3
0x1242c  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x12431  ldarg.s  4
0x12433  call     object Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetTranslatedPropertyValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue)
0x12438  stloc.2
0x12439  ldarg.0
0x1243a  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x1243f  ldloc.1
0x12440  ldarg.1
0x12441  ldind.ref
0x12442  ldarg.2
0x12443  ldarg.3
0x12444  ldloc.2
0x12445  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateResourceProperty(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string propertyName, object edmPropertyValue)
0x1244a  stloc.3
0x1244b  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12450  ldstr    aCrmodataputpro// "CrmODataPutPropertyCompleted"
0x12455  ldarg.1
0x12456  ldind.ref
0x12457  ldstr    aPut// "put"
0x1245c  ldstr    aPropertyname// "propertyName"
0x12461  ldarg.3
0x12462  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12467  ldloc.0
0x12468  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x1246d  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12472  ldarg.0
0x12473  ldarg.1
0x12474  ldind.ref
0x12475  ldloc.3
0x12476  box      [mscorlib]System.Guid
0x1247b  ldarg.1
0x1247c  ldind.ref
0x1247d  ldarg.0
0x1247e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12483  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12488  ldloc.1
0x12489  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::HandlePatchAndPutActionExecuteTransactionResponse(string entityName, object key, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1248e  ret
```
