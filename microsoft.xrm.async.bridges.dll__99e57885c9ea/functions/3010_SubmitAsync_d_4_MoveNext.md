# <SubmitAsync>d__4::MoveNext

- ea: `0x3010`
- end: `0x32b6`
- name: `<SubmitAsync>d__4::MoveNext`
- size: `678`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x180`
- `0x450`
- `0x470`
- `0x490`
- `0xb20`
- `0x1ff0`
- `0x2010`
- `0x2080`
- `0x20f0`
- `0x3010`

## pseudocode

```c

```

## disassembly

```asm
0x3010  ldarg.0
0x3011  ldfld    int32 <SubmitAsync>d__4::<>1__state
0x3016  stloc.0
0x3017  ldloc.0
0x3018  switch   loc_30A2, loc_30A2, loc_30A2
0x3029  ldarg.0
0x302a  ldfld    class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult <SubmitAsync>d__4::result
0x302f  ldstr    aResult// "result"
0x3034  call     T0x2B000011
0x3039  call     T0x2B000012
0x303e  pop
0x303f  ldarg.0
0x3040  ldfld    class Microsoft.Xrm.Async.Bridges.OperationRequest <SubmitAsync>d__4::operationRequest
0x3045  ldstr    aOperationreque// "operationRequest"
0x304a  call     T0x2B000001
0x304f  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<class Microsoft.Xrm.Async.Bridges.OperationRequest> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsValid(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<class Microsoft.Xrm.Async.Bridges.OperationRequest> arg)
0x3054  pop
0x3055  ldarg.0
0x3056  ldfld    class Microsoft.Xrm.Async.Bridges.CallbackSubmitter <SubmitAsync>d__4::<>4__this
0x305b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ITargetEndpointConfigLookup Microsoft.Xrm.Async.Bridges.CallbackSubmitter::targetEndpointConfigLookup
0x3060  ldsfld   string [mscorlib]System.String::Empty
0x3065  ldarg.0
0x3066  ldfld    class Microsoft.Xrm.Async.Bridges.OperationRequest <SubmitAsync>d__4::operationRequest
0x306b  callvirt instance class Microsoft.Xrm.Async.Bridges.AsyncOperation Microsoft.Xrm.Async.Bridges.OperationRequest::get_AsyncOperation()
0x3070  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Xrm.Async.Bridges.AsyncOperation::get_OrganizationId()
0x3075  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.TargetEndpointConfig Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ITargetEndpointConfigLookup::Find(string workload, valuetype [mscorlib]System.Guid organizationId)
0x307a  stloc.1
0x307b  ldarg.0
0x307c  ldarg.0
0x307d  ldfld    class Microsoft.Xrm.Async.Bridges.CallbackSubmitter <SubmitAsync>d__4::<>4__this
0x3082  ldfld    class Microsoft.Xrm.Async.Bridges.IHttpCallbackRequestBuilder Microsoft.Xrm.Async.Bridges.CallbackSubmitter::httpCallbackRequestBuilder
0x3087  ldarg.0
0x3088  ldfld    class Microsoft.Xrm.Async.Bridges.OperationRequest <SubmitAsync>d__4::operationRequest
0x308d  callvirt instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.OperationRequest::get_CompletionCallbackUri()
0x3092  ldarg.0
0x3093  ldfld    class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult <SubmitAsync>d__4::result
0x3098  callvirt instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Xrm.Async.Bridges.IHttpCallbackRequestBuilder::Build(class [System]System.Uri callbackUri, class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult result)
0x309d  stfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SubmitAsync>d__4::<request>5__1
0x30a2  nop
0x30a3  ldloc.0
0x30a4  switch   loc_3106, loc_3175, loc_31AB
0x30b5  ldloca.s 2
0x30b7  ldloc.1
0x30b8  callvirt instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.TargetEndpointConfig::get_AudienceUri()
0x30bd  ldc.i4.0
0x30be  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::.ctor([opt] class [System]System.Uri audienceUri, [opt] bool forceRefresh)
0x30c3  ldarg.0
0x30c4  ldfld    class Microsoft.Xrm.Async.Bridges.CallbackSubmitter <SubmitAsync>d__4::<>4__this
0x30c9  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IHttpSenderFactory Microsoft.Xrm.Async.Bridges.CallbackSubmitter::senderFactory
0x30ce  ldloc.2
0x30cf  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IHttpSenderFactory::GetSenderAsync([opt] valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions senderOptions)
0x30d4  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::GetAwaiter()
0x30d9  stloc.3
0x30da  ldloca.s 3
0x30dc  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::get_IsCompleted()
0x30e1  brtrue.s loc_3122
0x30e3  ldarg.0
0x30e4  ldc.i4.0
0x30e5  dup
0x30e6  stloc.0
0x30e7  stfld    int32 <SubmitAsync>d__4::<>1__state
0x30ec  ldarg.0
0x30ed  ldloc.3
0x30ee  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <SubmitAsync>d__4::<>u__1
0x30f3  ldarg.0
0x30f4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SubmitAsync>d__4::<>t__builder
0x30f9  ldloca.s 3
0x30fb  ldarg.0
0x30fc  call     T0x2B000078
0x3101  leave    loc_32B5
0x3106  ldarg.0
0x3107  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <SubmitAsync>d__4::<>u__1
0x310c  stloc.3
0x310d  ldarg.0
0x310e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <SubmitAsync>d__4::<>u__1
0x3113  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>
0x3119  ldarg.0
0x311a  ldc.i4.m1
0x311b  dup
0x311c  stloc.0
0x311d  stfld    int32 <SubmitAsync>d__4::<>1__state
0x3122  ldloca.s 3
0x3124  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::GetResult()
0x3129  ldloca.s 3
0x312b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>
0x3131  ldarg.0
0x3132  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SubmitAsync>d__4::<request>5__1
0x3137  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x313c  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> [System.Net.Http]System.Net.Http.HttpMessageInvoker::SendAsync(class [System.Net.Http]System.Net.Http.HttpRequestMessage, valuetype [mscorlib]System.Threading.CancellationToken)
0x3141  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x3146  stloc.s  5
0x3148  ldloca.s 5
0x314a  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x314f  brtrue.s loc_3192
0x3151  ldarg.0
0x3152  ldc.i4.1
0x3153  dup
0x3154  stloc.0
0x3155  stfld    int32 <SubmitAsync>d__4::<>1__state
0x315a  ldarg.0
0x315b  ldloc.s  5
0x315d  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SubmitAsync>d__4::<>u__2
0x3162  ldarg.0
0x3163  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SubmitAsync>d__4::<>t__builder
0x3168  ldloca.s 5
0x316a  ldarg.0
0x316b  call     T0x2B000079
0x3170  leave    loc_32B5
0x3175  ldarg.0
0x3176  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SubmitAsync>d__4::<>u__2
0x317b  stloc.s  5
0x317d  ldarg.0
0x317e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SubmitAsync>d__4::<>u__2
0x3183  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x3189  ldarg.0
0x318a  ldc.i4.m1
0x318b  dup
0x318c  stloc.0
0x318d  stfld    int32 <SubmitAsync>d__4::<>1__state
0x3192  ldloca.s 5
0x3194  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x3199  ldloca.s 5
0x319b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x31a1  stloc.s  4
0x31a3  ldarg.0
0x31a4  ldloc.s  4
0x31a6  stfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SubmitAsync>d__4::<response>5__2
0x31ab  nop
0x31ac  ldloc.0
0x31ad  ldc.i4.2
0x31ae  beq.s    loc_3204
0x31b0  ldarg.0
0x31b1  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SubmitAsync>d__4::<response>5__2
0x31b6  callvirt instance bool [System.Net.Http]System.Net.Http.HttpResponseMessage::get_IsSuccessStatusCode()
0x31bb  brtrue   loc_3245
0x31c0  ldarg.0
0x31c1  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SubmitAsync>d__4::<response>5__2
0x31c6  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Content()
0x31cb  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> [System.Net.Http]System.Net.Http.HttpContent::ReadAsStringAsync()
0x31d0  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x31d5  stloc.s  7
0x31d7  ldloca.s 7
0x31d9  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x31de  brtrue.s loc_3221
0x31e0  ldarg.0
0x31e1  ldc.i4.2
0x31e2  dup
0x31e3  stloc.0
0x31e4  stfld    int32 <SubmitAsync>d__4::<>1__state
0x31e9  ldarg.0
0x31ea  ldloc.s  7
0x31ec  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <SubmitAsync>d__4::<>u__3
0x31f1  ldarg.0
0x31f2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SubmitAsync>d__4::<>t__builder
0x31f7  ldloca.s 7
0x31f9  ldarg.0
0x31fa  call     T0x2B00007A
0x31ff  leave    loc_32B5
0x3204  ldarg.0
0x3205  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <SubmitAsync>d__4::<>u__3
0x320a  stloc.s  7
0x320c  ldarg.0
0x320d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <SubmitAsync>d__4::<>u__3
0x3212  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3218  ldarg.0
0x3219  ldc.i4.m1
0x321a  dup
0x321b  stloc.0
0x321c  stfld    int32 <SubmitAsync>d__4::<>1__state
0x3221  ldloca.s 7
0x3223  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x3228  ldloca.s 7
0x322a  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3230  stloc.s  6
0x3232  ldarg.0
0x3233  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SubmitAsync>d__4::<response>5__2
0x3238  callvirt instance valuetype [System]System.Net.HttpStatusCode [System.Net.Http]System.Net.Http.HttpResponseMessage::get_StatusCode()
0x323d  ldloc.s  6
0x323f  newobj   instance void [System.Web]System.Web.HttpException::.ctor(int32, string)
0x3244  throw
0x3245  leave.s  loc_325F
0x3247  ldloc.0
0x3248  ldc.i4.0
0x3249  bge.s    loc_325E
0x324b  ldarg.0
0x324c  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SubmitAsync>d__4::<response>5__2
0x3251  brfalse.s loc_325E
0x3253  ldarg.0
0x3254  ldfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SubmitAsync>d__4::<response>5__2
0x3259  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x325e  endfinally
0x325f  ldarg.0
0x3260  ldnull
0x3261  stfld    class [System.Net.Http]System.Net.Http.HttpResponseMessage <SubmitAsync>d__4::<response>5__2
0x3266  leave.s  loc_3280
0x3268  ldloc.0
0x3269  ldc.i4.0
0x326a  bge.s    loc_327F
0x326c  ldarg.0
0x326d  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SubmitAsync>d__4::<request>5__1
0x3272  brfalse.s loc_327F
0x3274  ldarg.0
0x3275  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SubmitAsync>d__4::<request>5__1
0x327a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x327f  endfinally
0x3280  ldarg.0
0x3281  ldnull
0x3282  stfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SubmitAsync>d__4::<request>5__1
0x3287  leave.s  loc_32A2
0x3289  stloc.s  8
0x328b  ldarg.0
0x328c  ldc.i4.s 0xFE
0x328e  stfld    int32 <SubmitAsync>d__4::<>1__state
0x3293  ldarg.0
0x3294  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SubmitAsync>d__4::<>t__builder
0x3299  ldloc.s  8
0x329b  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x32a0  leave.s  loc_32B5
0x32a2  ldarg.0
0x32a3  ldc.i4.s 0xFE
0x32a5  stfld    int32 <SubmitAsync>d__4::<>1__state
0x32aa  ldarg.0
0x32ab  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <SubmitAsync>d__4::<>t__builder
0x32b0  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x32b5  ret
```
