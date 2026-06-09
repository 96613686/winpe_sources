# Microsoft.Crm.Extensibility.OData.EntityController::PutNavigationRefImplementation

- ea: `0x12c10`
- end: `0x12c6d`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PutNavigationRefImplementation`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x31f90`

## callees

- `0x11770`
- `0x12c10`
- `0x12c70`
- `0x1eea0`
- `0x1ef70`
- `0x23e80`

## string_xrefs

- `0x12c4b`: `CrmODataPutNavigationRefCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12c10  ldarg.1
0x12c11  ldarg.0
0x12c12  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12c17  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12c1c  brfalse.s loc_12C35
0x12c1e  ldarg.0
0x12c1f  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x12c24  ldarg.1
0x12c25  call     string [mscorlib]System.String::Format(string, object)
0x12c2a  ldstr    aGet_0// "GET"
0x12c2f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x12c34  throw
0x12c35  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12c3a  stloc.0
0x12c3b  ldarg.0
0x12c3c  ldarg.1
0x12c3d  ldarg.2
0x12c3e  ldarg.3
0x12c3f  ldarg.s  4
0x12c41  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::UpdateNavigationRefInternal(string entityName, string key, string navigation, class [System]System.Uri link)
0x12c46  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12c4b  ldstr    aCrmodataputnav_1// "CrmODataPutNavigationRefCompleted"
0x12c50  ldarg.1
0x12c51  ldstr    aPut// "put"
0x12c56  ldstr    aNavigationname// "navigationName"
0x12c5b  ldarg.3
0x12c5c  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12c61  ldloc.0
0x12c62  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12c67  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12c6c  ret
```
