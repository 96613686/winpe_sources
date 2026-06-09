# <SendAsync>d__3::MoveNext

- ea: `0x41a0`
- end: `0x42e8`
- name: `<SendAsync>d__3::MoveNext`
- size: `328`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x2420`
- `0x2950`
- `0x41a0`

## pseudocode

```c

```

## disassembly

```asm
0x41a0  ldarg.0
0x41a1  ldfld    int32 <SendAsync>d__3::<>1__state
0x41a6  stloc.0
0x41a7  ldloc.0
0x41a8  brfalse.s loc_4204
0x41aa  ldloc.0
0x41ab  ldc.i4.1
0x41ac  beq      loc_428B
0x41b1  ldarg.0
0x41b2  ldarg.0
0x41b3  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__3::request
0x41b8  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x41bd  stfld    class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders <SendAsync>d__3::<>7__wrap1
0x41c2  ldarg.0
0x41c3  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler <SendAsync>d__3::<>4__this
0x41c8  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::authProvider
0x41cd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider::GetAsync()
0x41d2  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>::GetAwaiter()
0x41d7  stloc.3
0x41d8  ldloca.s 3
0x41da  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>::get_IsCompleted()
0x41df  brtrue.s loc_4220
0x41e1  ldarg.0
0x41e2  ldc.i4.0
0x41e3  dup
0x41e4  stloc.0
0x41e5  stfld    int32 <SendAsync>d__3::<>1__state
0x41ea  ldarg.0
0x41eb  ldloc.3
0x41ec  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <SendAsync>d__3::<>u__1
0x41f1  ldarg.0
0x41f2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>t__builder
0x41f7  ldloca.s 3
0x41f9  ldarg.0
0x41fa  call     T0x2B000086
0x41ff  leave    loc_42E7
0x4204  ldarg.0
0x4205  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <SendAsync>d__3::<>u__1
0x420a  stloc.3
0x420b  ldarg.0
0x420c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <SendAsync>d__3::<>u__1
0x4211  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>
0x4217  ldarg.0
0x4218  ldc.i4.m1
0x4219  dup
0x421a  stloc.0
0x421b  stfld    int32 <SendAsync>d__3::<>1__state
0x4220  ldloca.s 3
0x4222  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>::GetResult()
0x4227  ldloca.s 3
0x4229  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>
0x422f  stloc.2
0x4230  ldarg.0
0x4231  ldfld    class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders <SendAsync>d__3::<>7__wrap1
0x4236  ldloc.2
0x4237  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::set_Authorization(class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue)
0x423c  ldarg.0
0x423d  ldnull
0x423e  stfld    class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders <SendAsync>d__3::<>7__wrap1
0x4243  ldarg.0
0x4244  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler <SendAsync>d__3::<>4__this
0x4249  ldarg.0
0x424a  ldfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__3::request
0x424f  ldarg.0
0x4250  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <SendAsync>d__3::cancellationToken
0x4255  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::<>n__0(class [System.Net.Http]System.Net.Http.HttpRequestMessage request, valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x425a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetAwaiter()
0x425f  stloc.s  4
0x4261  ldloca.s 4
0x4263  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_IsCompleted()
0x4268  brtrue.s loc_42A8
0x426a  ldarg.0
0x426b  ldc.i4.1
0x426c  dup
0x426d  stloc.0
0x426e  stfld    int32 <SendAsync>d__3::<>1__state
0x4273  ldarg.0
0x4274  ldloc.s  4
0x4276  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>u__2
0x427b  ldarg.0
0x427c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>t__builder
0x4281  ldloca.s 4
0x4283  ldarg.0
0x4284  call     T0x2B000087
0x4289  leave.s  loc_42E7
0x428b  ldarg.0
0x428c  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>u__2
0x4291  stloc.s  4
0x4293  ldarg.0
0x4294  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>u__2
0x4299  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x429f  ldarg.0
0x42a0  ldc.i4.m1
0x42a1  dup
0x42a2  stloc.0
0x42a3  stfld    int32 <SendAsync>d__3::<>1__state
0x42a8  ldloca.s 4
0x42aa  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::GetResult()
0x42af  ldloca.s 4
0x42b1  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>
0x42b7  stloc.1
0x42b8  leave.s  loc_42D3
0x42ba  stloc.s  5
0x42bc  ldarg.0
0x42bd  ldc.i4.s 0xFE
0x42bf  stfld    int32 <SendAsync>d__3::<>1__state
0x42c4  ldarg.0
0x42c5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>t__builder
0x42ca  ldloc.s  5
0x42cc  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetException(class [mscorlib]System.Exception)
0x42d1  leave.s  loc_42E7
0x42d3  ldarg.0
0x42d4  ldc.i4.s 0xFE
0x42d6  stfld    int32 <SendAsync>d__3::<>1__state
0x42db  ldarg.0
0x42dc  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>t__builder
0x42e1  ldloc.1
0x42e2  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::SetResult(var<u1>)
0x42e7  ret
```
