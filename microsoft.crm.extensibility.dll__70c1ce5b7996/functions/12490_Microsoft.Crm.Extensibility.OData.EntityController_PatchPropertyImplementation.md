# Microsoft.Crm.Extensibility.OData.EntityController::PatchPropertyImplementation

- ea: `0x12490`
- end: `0x1256a`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PatchPropertyImplementation`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x31c90`

## callees

- `0xf740`
- `0x10020`
- `0x11500`
- `0x11770`
- `0x11a80`
- `0x12490`
- `0x1e5b0`
- `0x1eea0`
- `0x1ef70`
- `0x1f890`
- `0x20d50`
- `0x23e80`
- `0x28b60`

## string_xrefs

- `0x1252b`: `CrmODataPatchPropertyCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12490  ldarg.0
0x12491  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12496  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x1249b  ldarg.1
0x1249c  ldind.ref
0x1249d  ldarg.0
0x1249e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x124a3  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x124a8  brfalse.s loc_124C2
0x124aa  ldarg.0
0x124ab  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x124b0  ldarg.1
0x124b1  ldind.ref
0x124b2  call     string [mscorlib]System.String::Format(string, object)
0x124b7  ldstr    aGet_0// "GET"
0x124bc  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x124c1  throw
0x124c2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x124c7  stloc.0
0x124c8  ldarg.0
0x124c9  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x124ce  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x124d3  stloc.1
0x124d4  ldarg.1
0x124d5  ldarg.0
0x124d6  ldarg.1
0x124d7  ldind.ref
0x124d8  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x124dd  stind.ref
0x124de  ldarg.1
0x124df  ldind.ref
0x124e0  ldarg.0
0x124e1  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x124e6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x124eb  ldarg.3
0x124ec  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x124f1  ldarg.1
0x124f2  ldind.ref
0x124f3  ldarg.3
0x124f4  ldarg.0
0x124f5  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x124fa  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::CheckIfPropertyTypeIsComplex(string edmEntityName, string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x124ff  brfalse.s loc_1250C
0x12501  ldc.i4   0x195
0x12506  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x1250b  throw
0x1250c  ldarg.s  4
0x1250e  call     object Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetTranslatedPropertyValue(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty, object propertyValue)
0x12513  stloc.2
0x12514  ldarg.0
0x12515  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x1251a  ldloc.1
0x1251b  ldarg.1
0x1251c  ldind.ref
0x1251d  ldarg.2
0x1251e  ldarg.3
0x1251f  ldloc.2
0x12520  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateResourceProperty(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string propertyName, object edmPropertyValue)
0x12525  stloc.3
0x12526  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x1252b  ldstr    aCrmodatapatchp// "CrmODataPatchPropertyCompleted"
0x12530  ldarg.1
0x12531  ldind.ref
0x12532  ldstr    aPatch// "patch"
0x12537  ldstr    aPropertyname// "propertyName"
0x1253c  ldarg.3
0x1253d  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12542  ldloc.0
0x12543  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12548  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x1254d  ldarg.0
0x1254e  ldarg.1
0x1254f  ldind.ref
0x12550  ldloc.3
0x12551  box      [mscorlib]System.Guid
0x12556  ldarg.1
0x12557  ldind.ref
0x12558  ldarg.0
0x12559  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x1255e  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12563  ldloc.1
0x12564  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::HandlePatchAndPutActionExecuteTransactionResponse(string entityName, object key, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x12569  ret
```
