# Microsoft.Crm.Extensibility.OData.EntityController::PutEntityImplementation

- ea: `0x11e10`
- end: `0x11ea9`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PutEntityImplementation`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x31a60`

## callees

- `0x11500`
- `0x11770`
- `0x11a80`
- `0x11e10`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x21ad0`
- `0x23e80`
- `0x28b60`

## string_xrefs

- `0x11e37`: `GET,PATCH,DELETE`
- `0x11e74`: `CrmODataPutEntityCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x11e10  ldarg.0
0x11e11  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x11e16  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x11e1b  ldarg.1
0x11e1c  ldind.ref
0x11e1d  ldarg.0
0x11e1e  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11e23  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11e28  brtrue.s loc_11E42
0x11e2a  ldarg.0
0x11e2b  ldstr    aOperationNotSu// "Operation not supported on {0}"
0x11e30  ldarg.1
0x11e31  ldind.ref
0x11e32  call     string [mscorlib]System.String::Format(string, object)
0x11e37  ldstr    aGetPatchDelete// "GET,PATCH,DELETE"
0x11e3c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x11e41  throw
0x11e42  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x11e47  stloc.0
0x11e48  ldarg.0
0x11e49  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x11e4e  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x11e53  stloc.1
0x11e54  ldarg.1
0x11e55  ldarg.0
0x11e56  ldarg.1
0x11e57  ldind.ref
0x11e58  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x11e5d  stind.ref
0x11e5e  ldarg.0
0x11e5f  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x11e64  ldloc.1
0x11e65  ldarg.1
0x11e66  ldind.ref
0x11e67  ldarg.2
0x11e68  ldarg.3
0x11e69  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::UpdateEdmEntity(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityIdValue, class [System.Web.OData]System.Web.OData.EdmEntityObject entityObject)
0x11e6e  stloc.2
0x11e6f  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x11e74  ldstr    aCrmodataputent// "CrmODataPutEntityCompleted"
0x11e79  ldarg.1
0x11e7a  ldind.ref
0x11e7b  ldstr    aPut// "put"
0x11e80  ldnull
0x11e81  ldloc.0
0x11e82  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x11e87  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x11e8c  ldarg.0
0x11e8d  ldarg.1
0x11e8e  ldind.ref
0x11e8f  ldloc.2
0x11e90  box      [mscorlib]System.Guid
0x11e95  ldarg.1
0x11e96  ldind.ref
0x11e97  ldarg.0
0x11e98  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x11e9d  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x11ea2  ldloc.1
0x11ea3  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::HandlePatchAndPutActionExecuteTransactionResponse(string entityName, object key, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x11ea8  ret
```
