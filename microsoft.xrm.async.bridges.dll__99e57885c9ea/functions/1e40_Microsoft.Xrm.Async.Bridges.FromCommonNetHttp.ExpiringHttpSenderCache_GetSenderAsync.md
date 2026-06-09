# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::GetSenderAsync

- ea: `0x1e40`
- end: `0x1e81`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache::GetSenderAsync`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1e40  ldloca.s 0
0x1e42  ldarg.0
0x1e43  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.ExpiringHttpSenderCache <GetSenderAsync>d__3::<>4__this
0x1e48  ldloca.s 0
0x1e4a  ldarg.1
0x1e4b  stfld    valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__3::senderOptions
0x1e50  ldloca.s 0
0x1e52  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::Create()
0x1e57  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>t__builder
0x1e5c  ldloca.s 0
0x1e5e  ldc.i4.m1
0x1e5f  stfld    int32 <GetSenderAsync>d__3::<>1__state
0x1e64  ldloc.0
0x1e65  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>t__builder
0x1e6a  stloc.1
0x1e6b  ldloca.s 1
0x1e6d  ldloca.s 0
0x1e6f  call     T0x2B00004E
0x1e74  ldloca.s 0
0x1e76  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__3::<>t__builder
0x1e7b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::get_Task()
0x1e80  ret
```
