# Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationEntityImplementation

- ea: `0x12e90`
- end: `0x12f24`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationEntityImplementation`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x320b0`

## callees

- `0x11500`
- `0x11770`
- `0x12e90`
- `0x18fd0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x225f0`
- `0x23e80`
- `0x24e60`
- `0x28b60`

## string_xrefs

- `0x12efc`: `delete`
- `0x12ef5`: `CrmODataDeleteNavigationRefCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12e90  ldarg.0
0x12e91  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12e96  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x12e9b  ldarg.1
0x12e9c  ldind.ref
0x12e9d  ldarg.0
0x12e9e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12ea3  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12ea8  brtrue.s loc_12EC2
0x12eaa  ldarg.0
0x12eab  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x12eb0  ldarg.1
0x12eb1  ldind.ref
0x12eb2  call     string [mscorlib]System.String::Format(string, object)
0x12eb7  ldstr    aNone// "NONE"
0x12ebc  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x12ec1  throw
0x12ec2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12ec7  stloc.0
0x12ec8  ldarg.0
0x12ec9  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12ece  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12ed3  stloc.1
0x12ed4  ldarg.1
0x12ed5  ldarg.0
0x12ed6  ldarg.1
0x12ed7  ldind.ref
0x12ed8  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12edd  stind.ref
0x12ede  ldarg.0
0x12edf  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x12ee4  ldloc.1
0x12ee5  ldarg.1
0x12ee6  ldind.ref
0x12ee7  ldarg.2
0x12ee8  ldarg.3
0x12ee9  ldarg.s  4
0x12eeb  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::DeleteNavigationResource(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityIdValue, string navigationPropertyName, string navigationKey)
0x12ef0  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12ef5  ldstr    aCrmodatadelete_1// "CrmODataDeleteNavigationRefCompleted"
0x12efa  ldarg.1
0x12efb  ldind.ref
0x12efc  ldstr    aDelete_0// "delete"
0x12f01  ldstr    aNavigationname// "navigationName"
0x12f06  ldarg.3
0x12f07  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12f0c  ldloc.0
0x12f0d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12f12  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12f17  ldloc.1
0x12f18  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12f1d  ldc.i4.0
0x12f1e  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12f23  ret
```
