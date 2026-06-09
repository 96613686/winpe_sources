# Microsoft.Crm.Extensibility.OData.EntityController::PutNavigationImplementation

- ea: `0x128a0`
- end: `0x12934`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PutNavigationImplementation`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x31e10`

## callees

- `0x11500`
- `0x11770`
- `0x128a0`
- `0x18fd0`
- `0x1e790`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x23e80`
- `0x24e60`
- `0x28b60`

## string_xrefs

- `0x12905`: `CrmODataPutNavigationCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x128a0  ldarg.0
0x128a1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x128a6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x128ab  ldarg.1
0x128ac  ldind.ref
0x128ad  ldarg.0
0x128ae  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x128b3  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x128b8  brfalse.s loc_128D2
0x128ba  ldarg.0
0x128bb  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x128c0  ldarg.1
0x128c1  ldind.ref
0x128c2  call     string [mscorlib]System.String::Format(string, object)
0x128c7  ldstr    aGetPost// "GET,POST"
0x128cc  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x128d1  throw
0x128d2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x128d7  stloc.0
0x128d8  ldarg.0
0x128d9  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x128de  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x128e3  stloc.1
0x128e4  ldarg.1
0x128e5  ldarg.0
0x128e6  ldarg.1
0x128e7  ldind.ref
0x128e8  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x128ed  stind.ref
0x128ee  ldarg.0
0x128ef  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x128f4  ldloc.1
0x128f5  ldarg.1
0x128f6  ldind.ref
0x128f7  ldarg.2
0x128f8  ldarg.3
0x128f9  ldarg.s  4
0x128fb  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::UpdateNavigationPropertyCollection(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string navigationPropertyName, class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection navigationEntityCollection)
0x12900  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12905  ldstr    aCrmodataputnav_0// "CrmODataPutNavigationCompleted"
0x1290a  ldarg.1
0x1290b  ldind.ref
0x1290c  ldstr    aPut// "put"
0x12911  ldstr    aNavigationname// "navigationName"
0x12916  ldarg.3
0x12917  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x1291c  ldloc.0
0x1291d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12922  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12927  ldloc.1
0x12928  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x1292d  ldc.i4.0
0x1292e  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12933  ret
```
