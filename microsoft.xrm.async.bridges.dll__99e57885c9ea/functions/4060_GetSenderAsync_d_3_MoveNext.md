# <GetSenderAsync>d__3::MoveNext

- ea: `0x4060`
- end: `0x4178`
- name: `<GetSenderAsync>d__3::MoveNext`
- size: `280`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1ff0`
- `0x2090`
- `0x20a0`
- `0x4060`

## pseudocode

```c

```

## disassembly

```asm
0x4060  ldarg.0
0x4061  ldfld    int32 <GetSenderAsync>d__3::<>1__state
0x4066  stloc.0
0x4067  ldloc.0
0x4068  brfalse  loc_4102
0x406d  ldarg.0
0x406e  ldarg.0
0x406f  ldflda   valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__3::senderOptions
0x4074  call     instance class [System]System.Uri Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::get_AudienceUri()
0x4079  dup
0x407a  brtrue.s loc_4088
0x407c  pop
0x407d  ldstr    aNoAuth// "no-auth"
0x4082  ldc.i4.2
0x4083  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x4088  stfld    class [System]System.Uri <GetSenderAsync>d__3::<cacheKey>5__1
0x408d  ldarg.0
0x408e  ldflda   valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__3::senderOptions
0x4093  call     instance bool Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions::get_ForceRefresh()
0x4098  brtrue.s loc_40BB
0x409a  ldarg.0
0x409b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache <GetSenderAsync>d__3::<>4__this
0x40a0  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<class [System]System.Uri, class [System.Net.Http]System.Net.Http.HttpMessageInvoker> Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::cache
0x40a5  ldarg.0
0x40a6  ldfld    class [System]System.Uri <GetSenderAsync>d__3::<cacheKey>5__1
0x40ab  ldloca.s 2
0x40ad  callvirt instance bool class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<class [System]System.Uri, class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::TryGet(var<u1>, !!T0)
0x40b2  brfalse.s loc_40BB
0x40b4  ldloc.2
0x40b5  stloc.1
0x40b6  leave    loc_4163
0x40bb  ldarg.0
0x40bc  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache <GetSenderAsync>d__3::<>4__this
0x40c1  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IHttpSenderFactory Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::innerFactory
0x40c6  ldarg.0
0x40c7  ldfld    valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__3::senderOptions
0x40cc  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.IHttpSenderFactory::GetSenderAsync([opt] valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions senderOptions)
0x40d1  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::GetAwaiter()
0x40d6  stloc.s  4
0x40d8  ldloca.s 4
0x40da  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::get_IsCompleted()
0x40df  brtrue.s loc_411F
0x40e1  ldarg.0
0x40e2  ldc.i4.0
0x40e3  dup
0x40e4  stloc.0
0x40e5  stfld    int32 <GetSenderAsync>d__3::<>1__state
0x40ea  ldarg.0
0x40eb  ldloc.s  4
0x40ed  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>u__1
0x40f2  ldarg.0
0x40f3  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>t__builder
0x40f8  ldloca.s 4
0x40fa  ldarg.0
0x40fb  call     T0x2B000085
0x4100  leave.s  loc_4177
0x4102  ldarg.0
0x4103  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>u__1
0x4108  stloc.s  4
0x410a  ldarg.0
0x410b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>u__1
0x4110  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>
0x4116  ldarg.0
0x4117  ldc.i4.m1
0x4118  dup
0x4119  stloc.0
0x411a  stfld    int32 <GetSenderAsync>d__3::<>1__state
0x411f  ldloca.s 4
0x4121  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::GetResult()
0x4126  ldloca.s 4
0x4128  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>
0x412e  stloc.3
0x412f  ldarg.0
0x4130  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache <GetSenderAsync>d__3::<>4__this
0x4135  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<class [System]System.Uri, class [System.Net.Http]System.Net.Http.HttpMessageInvoker> Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::cache
0x413a  ldarg.0
0x413b  ldfld    class [System]System.Uri <GetSenderAsync>d__3::<cacheKey>5__1
0x4140  ldloc.3
0x4141  callvirt instance void class Microsoft.Xrm.Async.Bridges.FromCommon.ICache`2<class [System]System.Uri, class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::Put(var<u1>, !!T0)
0x4146  ldloc.3
0x4147  stloc.1
0x4148  leave.s  loc_4163
0x414a  stloc.s  5
0x414c  ldarg.0
0x414d  ldc.i4.s 0xFE
0x414f  stfld    int32 <GetSenderAsync>d__3::<>1__state
0x4154  ldarg.0
0x4155  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>t__builder
0x415a  ldloc.s  5
0x415c  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::SetException(class [mscorlib]System.Exception)
0x4161  leave.s  loc_4177
0x4163  ldarg.0
0x4164  ldc.i4.s 0xFE
0x4166  stfld    int32 <GetSenderAsync>d__3::<>1__state
0x416b  ldarg.0
0x416c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>t__builder
0x4171  ldloc.1
0x4172  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::SetResult(var<u1>)
0x4177  ret
```
