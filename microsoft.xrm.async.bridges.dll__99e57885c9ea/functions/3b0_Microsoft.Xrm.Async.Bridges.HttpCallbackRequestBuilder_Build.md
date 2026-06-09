# Microsoft.Xrm.Async.Bridges.HttpCallbackRequestBuilder::Build

- ea: `0x3b0`
- end: `0x3fc`
- name: `Microsoft.Xrm.Async.Bridges.HttpCallbackRequestBuilder::Build`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x410`
- `0x8a0`
- `0x2e20`

## string_xrefs

- `0x3b1`: `callbackUri`

## pseudocode

```c

```

## disassembly

```asm
0x3b0  ldarg.1
0x3b1  ldstr    aCallbackuri// "callbackUri"
0x3b6  call     T0x2B00000F
0x3bb  call     T0x2B000010
0x3c0  pop
0x3c1  ldarg.2
0x3c2  ldstr    aResult// "result"
0x3c7  call     T0x2B000011
0x3cc  call     T0x2B000012
0x3d1  pop
0x3d2  ldarg.0
0x3d3  ldfld    class Microsoft.Xrm.Async.Bridges.IAsyncHandlerResultResponseMapper Microsoft.Xrm.Async.Bridges.HttpCallbackRequestBuilder::responseMapper
0x3d8  ldarg.2
0x3d9  callvirt instance valuetype [System]System.Net.HttpStatusCode Microsoft.Xrm.Async.Bridges.IAsyncHandlerResultResponseMapper::Map(class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult result)
0x3de  newobj   instance void Microsoft.Xrm.Async.Bridges.Contracts.CallbackRequest::.ctor(valuetype [System]System.Net.HttpStatusCode statusCode)
0x3e3  stloc.0
0x3e4  call     class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpMethod::get_Post()
0x3e9  ldarg.1
0x3ea  newobj   instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::.ctor(class [System.Net.Http]System.Net.Http.HttpMethod, class [System]System.Uri)
0x3ef  dup
0x3f0  ldloc.0
0x3f1  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommonJson.Http.JsonSerializedContent::.ctor(object content)
0x3f6  callvirt instance void [System.Net.Http]System.Net.Http.HttpRequestMessage::set_Content(class [System.Net.Http]System.Net.Http.HttpContent)
0x3fb  ret
```
