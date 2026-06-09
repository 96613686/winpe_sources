# Microsoft.Crm.Extensibility.OData.EntityController::DeletePropertyImplementation

- ea: `0x12570`
- end: `0x12602`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::DeletePropertyImplementation`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x31cf0`

## callees

- `0x11500`
- `0x11770`
- `0x12570`
- `0x18fd0`
- `0x1e9a0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x23e80`
- `0x24e60`
- `0x28b60`

## string_xrefs

- `0x125da`: `delete`
- `0x125d3`: `CrmODataDeletePropertyCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12570  ldarg.0
0x12571  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12576  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x1257b  ldarg.1
0x1257c  ldind.ref
0x1257d  ldarg.0
0x1257e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12583  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12588  brfalse.s loc_125A2
0x1258a  ldarg.0
0x1258b  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x12590  ldarg.1
0x12591  ldind.ref
0x12592  call     string [mscorlib]System.String::Format(string, object)
0x12597  ldstr    aGet_0// "GET"
0x1259c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x125a1  throw
0x125a2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x125a7  stloc.0
0x125a8  ldarg.0
0x125a9  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x125ae  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x125b3  stloc.1
0x125b4  ldarg.1
0x125b5  ldarg.0
0x125b6  ldarg.1
0x125b7  ldind.ref
0x125b8  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x125bd  stind.ref
0x125be  ldarg.0
0x125bf  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x125c4  ldloc.1
0x125c5  ldarg.1
0x125c6  ldind.ref
0x125c7  ldarg.2
0x125c8  ldarg.3
0x125c9  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::DeleteResourceProperty(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string propertyName)
0x125ce  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x125d3  ldstr    aCrmodatadelete_0// "CrmODataDeletePropertyCompleted"
0x125d8  ldarg.1
0x125d9  ldind.ref
0x125da  ldstr    aDelete_0// "delete"
0x125df  ldstr    aPropertyname// "propertyName"
0x125e4  ldarg.3
0x125e5  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x125ea  ldloc.0
0x125eb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x125f0  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x125f5  ldloc.1
0x125f6  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x125fb  ldc.i4.0
0x125fc  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12601  ret
```
