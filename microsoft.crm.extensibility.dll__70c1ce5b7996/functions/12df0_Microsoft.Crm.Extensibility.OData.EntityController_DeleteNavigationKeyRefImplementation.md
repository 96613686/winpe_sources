# Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationKeyRefImplementation

- ea: `0x12df0`
- end: `0x12e84`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationKeyRefImplementation`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x32050`

## callees

- `0x11500`
- `0x11770`
- `0x12df0`
- `0x18fd0`
- `0x1ea20`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x23e80`
- `0x24e60`
- `0x28b60`

## string_xrefs

- `0x12e5c`: `delete`
- `0x12e55`: `CrmODataDeleteNavigationKeyRefCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12df0  ldarg.0
0x12df1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12df6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x12dfb  ldarg.1
0x12dfc  ldind.ref
0x12dfd  ldarg.0
0x12dfe  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12e03  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12e08  brfalse.s loc_12E22
0x12e0a  ldarg.0
0x12e0b  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x12e10  ldarg.1
0x12e11  ldind.ref
0x12e12  call     string [mscorlib]System.String::Format(string, object)
0x12e17  ldstr    aNone// "NONE"
0x12e1c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x12e21  throw
0x12e22  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12e27  stloc.0
0x12e28  ldarg.0
0x12e29  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12e2e  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12e33  stloc.1
0x12e34  ldarg.1
0x12e35  ldarg.0
0x12e36  ldarg.1
0x12e37  ldind.ref
0x12e38  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12e3d  stind.ref
0x12e3e  ldarg.0
0x12e3f  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x12e44  ldloc.1
0x12e45  ldarg.1
0x12e46  ldind.ref
0x12e47  ldarg.2
0x12e48  ldarg.3
0x12e49  ldarg.s  4
0x12e4b  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::DeleteResourceNavigationPropertyKeyReference(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string navigationPropertyName, string propertyKey)
0x12e50  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12e55  ldstr    aCrmodatadelete_2// "CrmODataDeleteNavigationKeyRefCompleted"
0x12e5a  ldarg.1
0x12e5b  ldind.ref
0x12e5c  ldstr    aDelete_0// "delete"
0x12e61  ldstr    aNavigationname// "navigationName"
0x12e66  ldarg.3
0x12e67  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12e6c  ldloc.0
0x12e6d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12e72  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12e77  ldloc.1
0x12e78  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12e7d  ldc.i4.0
0x12e7e  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12e83  ret
```
