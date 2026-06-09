# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::SendAsync

- ea: `0x23d0`
- end: `0x2419`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler::SendAsync`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x23d0  ldloca.s 0
0x23d2  ldarg.0
0x23d3  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticatingHandler <SendAsync>d__3::<>4__this
0x23d8  ldloca.s 0
0x23da  ldarg.1
0x23db  stfld    class [System.Net.Http]System.Net.Http.HttpRequestMessage <SendAsync>d__3::request
0x23e0  ldloca.s 0
0x23e2  ldarg.2
0x23e3  stfld    valuetype [mscorlib]System.Threading.CancellationToken <SendAsync>d__3::cancellationToken
0x23e8  ldloca.s 0
0x23ea  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::Create()
0x23ef  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>t__builder
0x23f4  ldloca.s 0
0x23f6  ldc.i4.m1
0x23f7  stfld    int32 <SendAsync>d__3::<>1__state
0x23fc  ldloc.0
0x23fd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>t__builder
0x2402  stloc.1
0x2403  ldloca.s 1
0x2405  ldloca.s 0
0x2407  call     T0x2B000060
0x240c  ldloca.s 0
0x240e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage> <SendAsync>d__3::<>t__builder
0x2413  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpResponseMessage>::get_Task()
0x2418  ret
```
