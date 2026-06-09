# Microsoft.Crm.Extensibility.OData.EntityController::HandleUnmappedRequest

- ea: `0x11490`
- end: `0x114d7`
- name: `Microsoft.Crm.Extensibility.OData.EntityController::HandleUnmappedRequest`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x11490`
- `0x11770`
- `0x28b60`
- `0x2da00`

## string_xrefs

- `0x114ab`: `Unmapped Request found, PathTemplate:{0}, HttpVerb:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x11490  ldarg.1
0x11491  brtrue.s loc_1149E
0x11493  ldc.i4   0x190
0x11498  newobj   instance void [System.Web.Http]System.Web.Http.HttpResponseException::.ctor(valuetype [System]System.Net.HttpStatusCode)
0x1149d  throw
0x1149e  ldarg.0
0x1149f  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x114a4  call     class Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext Microsoft.Crm.Extensibility.ODataV4.Edm.EdmExtensions::GetCrmODataExecutionContext(class [System.Net.Http]System.Net.Http.HttpRequestMessage request)
0x114a9  pop
0x114aa  ldarg.0
0x114ab  ldstr    aUnmappedReques// "Unmapped Request found, PathTemplate:{0"...
0x114b0  ldarg.1
0x114b1  callvirt instance string [System.Web.OData]System.Web.OData.Routing.ODataPath::get_PathTemplate()
0x114b6  ldarg.0
0x114b7  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x114bc  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x114c1  call     string [mscorlib]System.String::Format(string, object, object)
0x114c6  ldarg.1
0x114c7  callvirt instance string [System.Web.OData]System.Web.OData.Routing.ODataPath::get_PathTemplate()
0x114cc  call     string Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::GetAllowedMethodForODataPath(string pathTemplate)
0x114d1  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException Microsoft.Crm.Extensibility.OData.EntityController::CreateExceptionDataMethodNotAllowed(string exceptionMessage, string allowedMethods)
0x114d6  throw
```
