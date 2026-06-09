# Microsoft.Crm.Extensibility.OData.EntityController::PutNavigationEntityImplementation

- ea: `0x127d0`
- end: `0x1289b`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::PutNavigationEntityImplementation`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x31db0`

## callees

- `0xf740`
- `0x11500`
- `0x11a80`
- `0x1eea0`
- `0x1ef70`
- `0x20d50`
- `0x22480`
- `0x23e80`
- `0x28b60`
- `0x323e0`

## string_xrefs

- `0x12823`: `CrmODataPutNavigationKeyCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x127d0  newobj   instance void <>c__DisplayClass59_0::.ctor()
0x127d5  stloc.0
0x127d6  ldloc.0
0x127d7  ldarg.3
0x127d8  stfld    string <>c__DisplayClass59_0::navigation
0x127dd  ldarg.0
0x127de  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x127e3  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x127e8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x127ed  stloc.1
0x127ee  ldarg.0
0x127ef  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x127f4  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x127f9  stloc.2
0x127fa  ldarg.1
0x127fb  ldarg.0
0x127fc  ldarg.1
0x127fd  ldind.ref
0x127fe  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12803  stind.ref
0x12804  ldarg.0
0x12805  ldfld    class Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider Microsoft.Crm.Extensibility.OData.EntityController::crmODataMetadataServiceDataProvider
0x1280a  ldloc.2
0x1280b  ldarg.1
0x1280c  ldind.ref
0x1280d  ldarg.2
0x1280e  ldloc.0
0x1280f  ldfld    string <>c__DisplayClass59_0::navigation
0x12814  ldarg.s  4
0x12816  ldarg.s  5
0x12818  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.CrmODataMetadataServiceDataProvider::UpdateEdmNavigationEntity(class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, string edmEntityName, string entityIdValue, string navigationPropertyName, string navigationKey, class [System.Web.OData]System.Web.OData.EdmEntityObject navigationEntityObject)
0x1281d  stloc.3
0x1281e  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12823  ldstr    aCrmodataputnav// "CrmODataPutNavigationKeyCompleted"
0x12828  ldarg.1
0x12829  ldind.ref
0x1282a  ldstr    aPut// "put"
0x1282f  ldstr    aNavigationname// "navigationName"
0x12834  ldloc.0
0x12835  ldfld    string <>c__DisplayClass59_0::navigation
0x1283a  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x1283f  ldloc.1
0x12840  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12845  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x1284a  ldarg.1
0x1284b  ldind.ref
0x1284c  ldarg.0
0x1284d  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12852  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12857  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty> [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::DeclaredNavigationProperties(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType)
0x1285c  ldloc.0
0x1285d  ldftn    instance bool <>c__DisplayClass59_0::<PutNavigationEntityImplementation>b__0(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty x)
0x12863  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty, bool>::.ctor(object, native int)
0x12868  call     T0x2B00007C
0x1286d  call     T0x2B00007D
0x12872  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEntityType [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::ToEntityType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNavigationProperty)
0x12877  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x1287c  stloc.s  4
0x1287e  ldarg.0
0x1287f  ldloc.s  4
0x12881  ldloc.3
0x12882  box      [mscorlib]System.Guid
0x12887  ldarg.1
0x12888  ldind.ref
0x12889  ldarg.0
0x1288a  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x1288f  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12894  ldloc.2
0x12895  call     instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.EntityController::HandlePatchAndPutActionExecuteTransactionResponse(string entityName, object key, bool isMetadataEntity, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context)
0x1289a  ret
```
