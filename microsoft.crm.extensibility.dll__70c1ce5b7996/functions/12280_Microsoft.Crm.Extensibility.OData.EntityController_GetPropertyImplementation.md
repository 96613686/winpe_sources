# Microsoft.Crm.Extensibility.OData.EntityController::GetPropertyImplementation

- ea: `0x12280`
- end: `0x123cb`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::GetPropertyImplementation`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x31bd0`

## callees

- `0x10020`
- `0x11500`
- `0x11600`
- `0x12280`
- `0x18fd0`
- `0x19240`
- `0x1eea0`
- `0x1ef70`
- `0x1fa70`
- `0x20d50`
- `0x24e60`
- `0x28b60`
- `0x28bb0`
- `0x28f80`
- `0x29180`

## string_xrefs

- `0x122fb`: ` $value on ComplexProperty is not supported.`
- `0x12358`: `CrmODataGetPropertyCompleted`

## pseudocode

```c

```

## disassembly

```asm
0x12280  ldarg.0
0x12281  call     instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x12286  call     void Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidateInputParameters(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary controllerModelState)
0x1228b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::.ctor()
0x12290  stloc.0
0x12291  ldarg.0
0x12292  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x12297  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x1229c  stloc.1
0x1229d  ldarg.0
0x1229e  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x122a3  ldarg.0
0x122a4  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x122a9  call     class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetQueryOptions(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x122ae  stloc.2
0x122af  ldarg.0
0x122b0  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x122b5  call     bool Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetValueSegment(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x122ba  stloc.3
0x122bb  ldloc.3
0x122bc  brfalse.s loc_1230C
0x122be  ldarg.0
0x122bf  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x122c4  call     class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataRequestHeader(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x122c9  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataMaxVersionSpecified()
0x122ce  brtrue.s loc_122E6
0x122d0  ldc.i4   0x193
0x122d5  ldstr    aOdataMaxversio// " OData-MaxVersion header must be specif"...
0x122da  ldc.i4.0
0x122db  newarr   [mscorlib]System.Object
0x122e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x122e5  throw
0x122e6  ldarg.1
0x122e7  ldind.ref
0x122e8  ldarg.3
0x122e9  ldarg.0
0x122ea  ldfld    class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel Microsoft.Crm.Extensibility.OData.EntityController::_edmModel
0x122ef  call     bool Microsoft.Crm.Extensibility.OData.EdmUtilities::CheckIfPropertyTypeIsComplex(string edmEntityName, string propertyName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x122f4  brfalse.s loc_1230C
0x122f6  ldc.i4   0x195
0x122fb  ldstr    aValueOnComplex// " $value on ComplexProperty is not suppo"...
0x12300  ldc.i4.0
0x12301  newarr   [mscorlib]System.Object
0x12306  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1230b  throw
0x1230c  ldarg.1
0x1230d  ldarg.0
0x1230e  ldarg.1
0x1230f  ldind.ref
0x12310  call     instance string Microsoft.Crm.Extensibility.OData.EntityController::GetCastedEntityNameIfAvailable(string entityName)
0x12315  stind.ref
0x12316  ldarg.0
0x12317  ldarg.1
0x12318  ldind.ref
0x12319  ldarg.2
0x1231a  ldarg.3
0x1231b  ldloc.1
0x1231c  ldloc.2
0x1231d  call     instance object Microsoft.Crm.Extensibility.OData.EntityController::GetPropertyInternal(string entityName, string key, string propertyName, class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext context, class [System.Web.OData]System.Web.OData.Query.ODataQueryOptions queryOptions)
0x12322  stloc.s  4
0x12324  ldloc.s  4
0x12326  brfalse.s loc_12353
0x12328  ldloc.s  4
0x1232a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1232f  ldtoken  [mscorlib]System.DateTimeOffset
0x12334  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12339  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1233e  brfalse.s loc_12353
0x12340  ldloc.s  4
0x12342  callvirt instance string [mscorlib]System.Object::ToString()
0x12347  call     valuetype [mscorlib]System.DateTimeOffset Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ConvertToDateTimeOffset(object propertyValue)
0x1234c  box      [mscorlib]System.DateTimeOffset
0x12351  stloc.s  4
0x12353  call     class Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::get_Instance()
0x12358  ldstr    aCrmodatagetpro// "CrmODataGetPropertyCompleted"
0x1235d  ldarg.1
0x1235e  ldind.ref
0x1235f  ldstr    aGet// "get"
0x12364  ldstr    aPropertyname// "propertyName"
0x12369  ldarg.3
0x1236a  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x1236f  ldloc.0
0x12370  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken::Stop()
0x12375  callvirt instance void Microsoft.Crm.Extensibility.OData.CrmODataTelemetryEvents::LogEvent(string eventName, string entityOrEntitySetName, string verb, class [mscorlib]System.Tuple`2<string, string> extraParam, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.EventSources.TelemetryExecutionToken executionToken)
0x1237a  ldloc.s  4
0x1237c  brtrue.s loc_1238B
0x1237e  ldloc.1
0x1237f  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x12384  ldc.i4.0
0x12385  callvirt instance class [System.Web.Http]System.Web.Http.IHttpActionResult Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse([opt] bool isResponseFromAction)
0x1238a  ret
0x1238b  ldloc.3
0x1238c  brfalse.s loc_123C2
0x1238e  ldloc.s  4
0x12390  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x12395  ldtoken  unsigned int8[]
0x1239a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1239f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x123a4  brfalse.s loc_123B4
0x123a6  ldarg.0
0x123a7  ldloc.s  4
0x123a9  castclass unsigned int8[]
0x123ae  callvirt T0x2B000077
0x123b3  ret
0x123b4  ldarg.0
0x123b5  ldloc.s  4
0x123b7  callvirt instance string [mscorlib]System.Object::ToString()
0x123bc  callvirt T0x2B000078
0x123c1  ret
0x123c2  ldarg.0
0x123c3  ldloc.s  4
0x123c5  callvirt T0x2B00006B
0x123ca  ret
```
