# <ExecuteOperationAsync>d__4::MoveNext

- ea: `0x4c0`
- end: `0x5f9`
- name: `<ExecuteOperationAsync>d__4::MoveNext`
- size: `313`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4c0`

## string_xrefs

- `0x506`: `x-ms-crm-hyrax-completion-callback-uri`

## pseudocode

```c

```

## disassembly

```asm
0x4c0  ldarg.0
0x4c1  ldfld    int32 <ExecuteOperationAsync>d__4::<>1__state
0x4c6  stloc.0
0x4c7  ldloc.0
0x4c8  brfalse  loc_56F
0x4cd  ldarg.0
0x4ce  ldfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x4d3  callvirt instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x4d8  callvirt instance bool [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary::get_IsValid()
0x4dd  brtrue.s loc_4FB
0x4df  ldarg.0
0x4e0  ldfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x4e5  ldarg.0
0x4e6  ldfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x4eb  callvirt instance class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary [System.Web.Http]System.Web.Http.ApiController::get_ModelState()
0x4f0  callvirt instance class [System.Web.Http]System.Web.Http.Results.InvalidModelStateResult [System.Web.Http]System.Web.Http.ApiController::BadRequest(class [System.Web.Http]System.Web.Http.ModelBinding.ModelStateDictionary)
0x4f5  stloc.1
0x4f6  leave    loc_5E4
0x4fb  ldarg.0
0x4fc  ldfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x501  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage [System.Web.Http]System.Web.Http.ApiController::get_Request()
0x506  ldstr    aXMsCrmHyraxCom// "x-ms-crm-hyrax-completion-callback-uri"
0x50b  call     T0x2B000012
0x510  stloc.2
0x511  newobj   instance void [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::.ctor()
0x516  dup
0x517  ldarg.0
0x518  ldfld    class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation <ExecuteOperationAsync>d__4::operation
0x51d  callvirt instance void [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::set_AsyncOperation(class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation)
0x522  dup
0x523  ldloc.2
0x524  callvirt instance void [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest::set_CompletionCallbackUri(class [System]System.Uri)
0x529  stloc.3
0x52a  ldarg.0
0x52b  ldfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x530  ldfld    class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerHost Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::asyncHandlerHost
0x535  ldloc.3
0x536  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerHost::ExecuteAsync(class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.OperationRequest)
0x53b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult>::GetAwaiter()
0x540  stloc.s  7
0x542  ldloca.s 7
0x544  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult>::get_IsCompleted()
0x549  brtrue.s loc_58C
0x54b  ldarg.0
0x54c  ldc.i4.0
0x54d  dup
0x54e  stloc.0
0x54f  stfld    int32 <ExecuteOperationAsync>d__4::<>1__state
0x554  ldarg.0
0x555  ldloc.s  7
0x557  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> <ExecuteOperationAsync>d__4::<>u__1
0x55c  ldarg.0
0x55d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <ExecuteOperationAsync>d__4::<>t__builder
0x562  ldloca.s 7
0x564  ldarg.0
0x565  call     T0x2B000013
0x56a  leave    loc_5F8
0x56f  ldarg.0
0x570  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> <ExecuteOperationAsync>d__4::<>u__1
0x575  stloc.s  7
0x577  ldarg.0
0x578  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> <ExecuteOperationAsync>d__4::<>u__1
0x57d  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult>
0x583  ldarg.0
0x584  ldc.i4.m1
0x585  dup
0x586  stloc.0
0x587  stfld    int32 <ExecuteOperationAsync>d__4::<>1__state
0x58c  ldloca.s 7
0x58e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult>::GetResult()
0x593  stloc.s  8
0x595  ldloca.s 7
0x597  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult>
0x59d  ldloc.s  8
0x59f  stloc.s  6
0x5a1  ldloc.s  6
0x5a3  stloc.s  4
0x5a5  ldarg.0
0x5a6  ldfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x5ab  ldfld    class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.IAsyncHandlerResultResponseMapper Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::responseMapper
0x5b0  ldloc.s  4
0x5b2  callvirt instance valuetype [System]System.Net.HttpStatusCode [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.IAsyncHandlerResultResponseMapper::Map(class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult)
0x5b7  stloc.s  5
0x5b9  ldarg.0
0x5ba  ldfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x5bf  ldloc.s  5
0x5c1  ldloc.s  4
0x5c3  callvirt T0x2B000014
0x5c8  stloc.1
0x5c9  leave.s  loc_5E4
0x5cb  stloc.s  9
0x5cd  ldarg.0
0x5ce  ldc.i4.s 0xFE
0x5d0  stfld    int32 <ExecuteOperationAsync>d__4::<>1__state
0x5d5  ldarg.0
0x5d6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <ExecuteOperationAsync>d__4::<>t__builder
0x5db  ldloc.s  9
0x5dd  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetException(class [mscorlib]System.Exception)
0x5e2  leave.s  loc_5F8
0x5e4  ldarg.0
0x5e5  ldc.i4.s 0xFE
0x5e7  stfld    int32 <ExecuteOperationAsync>d__4::<>1__state
0x5ec  ldarg.0
0x5ed  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <ExecuteOperationAsync>d__4::<>t__builder
0x5f2  ldloc.1
0x5f3  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::SetResult(var<u1>)
0x5f8  ret
```
