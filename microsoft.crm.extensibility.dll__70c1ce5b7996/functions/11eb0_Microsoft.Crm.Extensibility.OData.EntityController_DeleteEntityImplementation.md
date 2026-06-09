# Microsoft.Crm.Extensibility.OData.EntityController::DeleteEntityImplementation

- ea: `0x11eb0`
- end: `0x11f0b`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::DeleteEntityImplementation`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x31ac0`

## callees

- `0x11500`
- `0x116f0`
- `0x18fd0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x24e60`
- `0x28b60`

## string_xrefs

- `0x11ee6`: `CrmODataDeleteEntityCompleted`
- `0x11eed`: `delete`

## pseudocode

```c

```

## disassembly

```asm
0x11eb0  ldarg.0
0x11eb1  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x11eb6  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x11ebb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x11ec0  stloc.0
0x11ec1  ldarg.0
0x11ec2  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11ec7  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x11ecc  stloc.1
0x11ecd  ldarg.1
0x11ece  ldarg.0
0x11ecf  ldarg.1
0x11ed0  ldind.ref
0x11ed1  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x11ed6  stind.ref
0x11ed7  ldarg.0
0x11ed8  ldloc.1
0x11ed9  ldarg.1
0x11eda  ldind.ref
0x11edb  ldarg.2
0x11edc  call     instance void Microsoft.Crm.Extensibility.OData.EntityController::DeleteEntityInternal(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityIdValue)
0x11ee1  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x11ee6  ldstr    aCrmodatadelete// "CrmODataDeleteEntityCompleted"
0x11eeb  ldarg.1
0x11eec  ldind.ref
0x11eed  ldstr    aDelete_0// "delete"
0x11ef2  ldnull
0x11ef3  ldloc.0
0x11ef4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x11ef9  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x11efe  ldloc.1
0x11eff  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x11f04  ldc.i4.0
0x11f05  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x11f0a  ret
```
