# Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationRefImplementation

- ea: `0x12a60`
- end: `0x12ba8`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationRefImplementation`
- size: `328`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x31ed0`

## callees

- `0xfe80`
- `0x11500`
- `0x11680`
- `0x12a60`
- `0x17650`
- `0x17660`
- `0x18fd0`
- `0x1eea0`
- `0x1ef70`
- `0x1f5d0`
- `0x20290`
- `0x203a0`
- `0x20450`
- `0x20d50`
- `0x23e80`
- `0x24e60`
- `0x28b60`
- `0x28bb0`

## string_xrefs

- `0x12b04`: `CrmODataGetNavigationRefCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12a60  ldarg.0
0x12a61  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12a66  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x12a6b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12a70  stloc.0
0x12a71  ldarg.0
0x12a72  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12a77  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x12a7c  stloc.1
0x12a7d  ldarg.0
0x12a7e  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12a83  ldarg.0
0x12a84  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12a89  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12a8e  stloc.2
0x12a8f  ldarg.1
0x12a90  ldarg.0
0x12a91  ldarg.1
0x12a92  ldind.ref
0x12a93  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12a98  stind.ref
0x12a99  ldarg.0
0x12a9a  ldarg.1
0x12a9b  ldind.ref
0x12a9c  ldarg.2
0x12a9d  ldarg.3
0x12a9e  ldloc.1
0x12a9f  ldloc.2
0x12aa0  call     instance class Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection Microsoft.Crm.Extensibility.OData.EntityController::GetNavigationRefInternal(string entityName, string key, string navigation, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x12aa5  stloc.3
0x12aa6  ldloc.3
0x12aa7  ldloc.1
0x12aa8  ldarg.0
0x12aa9  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12aae  call     class [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLinks Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetEdmEntityReferenceCollection(class [System.Web.OData]System.Web.OData.EdmEntityObjectCollection edmEntityObjectCollection, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12ab3  stloc.s  4
0x12ab5  ldloc.3
0x12ab6  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_HasMoreRecords()
0x12abb  brfalse.s loc_12AFF
0x12abd  ldarg.0
0x12abe  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12ac3  ldarg.3
0x12ac4  ldloc.3
0x12ac5  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_PagingCookie()
0x12aca  ldarg.0
0x12acb  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12ad0  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::IsTopCountNotExceeded(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, string edmNavigationProperty, string pagingCookie, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12ad5  brfalse.s loc_12AFF
0x12ad7  ldloc.s  4
0x12ad9  ldarg.0
0x12ada  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12adf  ldloc.3
0x12ae0  callvirt instance string Microsoft.Crm.Extensibility.OData.CrmEdmEntityObjectCollection::get_PagingCookie()
0x12ae5  call     string Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetNextBatchingCookie(string batchingCookie)
0x12aea  ldarg.3
0x12aeb  ldloca.s 5
0x12aed  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x12af3  ldloc.s  5
0x12af5  call     class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateNextPageLink(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, string pagingCookie, string navigationPropertyName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> primaryAttributeValue)
0x12afa  callvirt instance void [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLinks::set_NextPageLink(class [System]System.Uri)
0x12aff  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12b04  ldstr    aCrmodatagetnav_0// "CrmODataGetNavigationRefCompleted"
0x12b09  ldarg.1
0x12b0a  ldind.ref
0x12b0b  ldstr    aGet// "get"
0x12b10  ldstr    aNavigationrefn// "navigationRefName"
0x12b15  ldarg.3
0x12b16  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x12b1b  ldloc.0
0x12b1c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12b21  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x12b26  ldloc.s  4
0x12b28  brfalse.s loc_12B38
0x12b2a  ldloc.s  4
0x12b2c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLink> [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLinks::get_Links()
0x12b31  call     T0x2B00007E
0x12b36  brtrue.s loc_12B6F
0x12b38  ldarg.1
0x12b39  ldind.ref
0x12b3a  ldarg.3
0x12b3b  ldarg.0
0x12b3c  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12b41  ldarg.1
0x12b42  ldind.ref
0x12b43  ldarg.0
0x12b44  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12b49  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12b4e  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::IsManyToOneRelationship(string edmEntityName, string navigationPropertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isMetadataEntity)
0x12b53  brtrue.s loc_12B59
0x12b55  ldloc.s  4
0x12b57  brtrue.s loc_12B66
0x12b59  ldloc.1
0x12b5a  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12b5f  ldc.i4.0
0x12b60  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x12b65  ret
0x12b66  ldarg.0
0x12b67  ldloc.s  4
0x12b69  callvirt T0x2B00007F
0x12b6e  ret
0x12b6f  ldarg.1
0x12b70  ldind.ref
0x12b71  ldarg.3
0x12b72  ldarg.0
0x12b73  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12b78  ldarg.1
0x12b79  ldind.ref
0x12b7a  ldarg.0
0x12b7b  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x12b80  call     bool Microsoft.Crm.Extensibility.OData.CrmODataMetadataUtilities::IsMetadataEntity(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x12b85  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::IsManyToOneRelationship(string edmEntityName, string navigationPropertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel, [opt] bool isMetadataEntity)
0x12b8a  brfalse.s loc_12B9F
0x12b8c  ldarg.0
0x12b8d  ldloc.s  4
0x12b8f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLink> [Microsoft.OData.Core]Microsoft.OData.ODataEntityReferenceLinks::get_Links()
0x12b94  call     T0x2B000080
0x12b99  callvirt T0x2B000081
0x12b9e  ret
0x12b9f  ldarg.0
0x12ba0  ldloc.s  4
0x12ba2  callvirt T0x2B00007F
0x12ba7  ret
```
