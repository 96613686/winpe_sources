# Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::GetSenderAsync

- ea: `0x1d50`
- end: `0x1d91`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory::GetSenderAsync`
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
0x1d50  ldloca.s 0
0x1d52  ldarg.0
0x1d53  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.AuthenticatedHttpSenderFactory <GetSenderAsync>d__4::<>4__this
0x1d58  ldloca.s 0
0x1d5a  ldarg.1
0x1d5b  stfld    valuetype Microsoft.Xrm.Async.Bridges.FromCommonNetHttp.SenderOptions <GetSenderAsync>d__4::senderOptions
0x1d60  ldloca.s 0
0x1d62  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::Create()
0x1d67  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__4::<>t__builder
0x1d6c  ldloca.s 0
0x1d6e  ldc.i4.m1
0x1d6f  stfld    int32 <GetSenderAsync>d__4::<>1__state
0x1d74  ldloc.0
0x1d75  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__4::<>t__builder
0x1d7a  stloc.1
0x1d7b  ldloca.s 1
0x1d7d  ldloca.s 0
0x1d7f  call     T0x2B00004C
0x1d84  ldloca.s 0
0x1d86  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker> <GetSenderAsync>d__4::<>t__builder
0x1d8b  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.HttpMessageInvoker>::get_Task()
0x1d90  ret
```
