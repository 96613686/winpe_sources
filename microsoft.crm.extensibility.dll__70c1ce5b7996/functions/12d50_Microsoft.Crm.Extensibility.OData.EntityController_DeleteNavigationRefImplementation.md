# Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationRefImplementation

- ea: `0x12d50`
- end: `0x12de2`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::DeleteNavigationRefImplementation`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x31ff0`

## callees

- `0x11500`
- `0x11770`
- `0x12d50`
- `0x18fd0`
- `0x1e9b0`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x23e80`
- `0x24e60`
- `0x28b60`

## string_xrefs

- `0x12dba`: `delete`
- `0x12db3`: `CrmODataDeleteNavigationRefCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12d50  ldarg.0
0x12d51  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12d56  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x12d5b  ldarg.1
0x12d5c  ldind.ref
0x12d5d  ldarg.0
0x12d5e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12d63  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12d68  brfalse.s loc_12D82
0x12d6a  ldarg.0
0x12d6b  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x12d70  ldarg.1
0x12d71  ldind.ref
0x12d72  call     string [mscorlib]System.String::Format(string, object)
0x12d77  ldstr    aGet_0// "GET"
0x12d7c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x12d81  throw
0x12d82  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12d87  stloc.0
0x12d88  ldarg.0
0x12d89  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12d8e  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12d93  stloc.1
0x12d94  ldarg.1
0x12d95  ldarg.0
0x12d96  ldarg.1
0x12d97  ldind.ref
0x12d98  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12d9d  stind.ref
0x12d9e  ldarg.0
0x12d9f  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataServiceDataProvider
0x12da4  ldloc.1
0x12da5  ldarg.1
0x12da6  ldind.ref
0x12da7  ldarg.2
0x12da8  ldarg.3
0x12da9  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataServiceDataProvider::DeleteResourceNavigationPropertyReference(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityKeyValue, string navigationPropertyName)
0x12dae  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12db3  ldstr    aCrmodatadelete_1// "CrmODataDeleteNavigationRefCompleted"
0x12db8  ldarg.1
0x12db9  ldind.ref
0x12dba  ldstr    aDelete_0// "delete"
0x12dbf  ldstr    aNavigationname// "navigationName"
0x12dc4  ldarg.3
0x12dc5  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12dca  ldloc.0
0x12dcb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12dd0  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12dd5  ldloc.1
0x12dd6  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12ddb  ldc.i4.0
0x12ddc  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12de1  ret
```
