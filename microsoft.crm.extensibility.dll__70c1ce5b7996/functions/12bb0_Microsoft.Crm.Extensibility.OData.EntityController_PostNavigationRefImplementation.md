# Microsoft.Crm.Extensibility.OData.EntityController::PostNavigationRefImplementation

- ea: `0x12bb0`
- end: `0x12c0d`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PostNavigationRefImplementation`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x31f30`

## callees

- `0x11770`
- `0x12bb0`
- `0x12c70`
- `0x1eea0`
- `0x1ef70`
- `0x23e80`

## string_xrefs

- `0x12beb`: `CrmODataPostNavigationRefCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12bb0  ldarg.1
0x12bb1  ldarg.0
0x12bb2  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12bb7  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12bbc  brfalse.s loc_12BD5
0x12bbe  ldarg.0
0x12bbf  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x12bc4  ldarg.1
0x12bc5  call     string [mscorlib]System.String::Format(string, object)
0x12bca  ldstr    aGet_0// "GET"
0x12bcf  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x12bd4  throw
0x12bd5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12bda  stloc.0
0x12bdb  ldarg.0
0x12bdc  ldarg.1
0x12bdd  ldarg.2
0x12bde  ldarg.3
0x12bdf  ldarg.s  4
0x12be1  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::UpdateNavigationRefInternal(string entityName, string key, string navigation, class [System]System.Uri link)
0x12be6  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12beb  ldstr    aCrmodatapostna_0// "CrmODataPostNavigationRefCompleted"
0x12bf0  ldarg.1
0x12bf1  ldstr    aPost// "post"
0x12bf6  ldstr    aNavigationrefn// "navigationRefName"
0x12bfb  ldarg.3
0x12bfc  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12c01  ldloc.0
0x12c02  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12c07  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12c0c  ret
```
