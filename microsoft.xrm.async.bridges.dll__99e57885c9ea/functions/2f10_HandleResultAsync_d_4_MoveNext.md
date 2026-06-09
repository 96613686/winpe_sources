# <HandleResultAsync>d__4::MoveNext

- ea: `0x2f10`
- end: `0x2fe9`
- name: `<HandleResultAsync>d__4::MoveNext`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x2a0`
- `0x430`
- `0x2f10`

## pseudocode

```c

```

## disassembly

```asm
0x2f10  ldarg.0
0x2f11  ldfld    int32 <HandleResultAsync>d__4::<>1__state
0x2f16  stloc.0
0x2f17  ldloc.0
0x2f18  brfalse.s loc_2F91
0x2f1a  ldarg.0
0x2f1b  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> <HandleResultAsync>d__4::taskResult
0x2f20  callvirt instance valuetype [mscorlib]System.Threading.Tasks.TaskStatus [mscorlib]System.Threading.Tasks.Task::get_Status()
0x2f25  ldc.i4.5
0x2f26  bne.un.s loc_2F35
0x2f28  ldarg.0
0x2f29  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> <HandleResultAsync>d__4::taskResult
0x2f2e  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult>::get_Result()
0x2f33  brtrue.s loc_2F3F
0x2f35  ldc.i4.s 0x1F
0x2f37  call     class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult Microsoft.Xrm.Async.Bridges.AsyncHandlerResult::Create([opt] valuetype Microsoft.Xrm.Async.Bridges.Providers.Crm.AsyncOperationStatusCode resultCode)
0x2f3c  stloc.1
0x2f3d  br.s     loc_2F4B
0x2f3f  ldarg.0
0x2f40  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> <HandleResultAsync>d__4::taskResult
0x2f45  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult>::get_Result()
0x2f4a  stloc.1
0x2f4b  ldarg.0
0x2f4c  ldfld    class Microsoft.Xrm.Async.Bridges.AcceptingAsyncHandlerHost <HandleResultAsync>d__4::<>4__this
0x2f51  ldfld    class Microsoft.Xrm.Async.Bridges.ICallbackSubmitter Microsoft.Xrm.Async.Bridges.AcceptingAsyncHandlerHost::callbackSubmitter
0x2f56  ldloc.1
0x2f57  ldarg.0
0x2f58  ldfld    class Microsoft.Xrm.Async.Bridges.OperationRequest <HandleResultAsync>d__4::operationRequest
0x2f5d  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.Xrm.Async.Bridges.ICallbackSubmitter::SubmitAsync(class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult result, class Microsoft.Xrm.Async.Bridges.OperationRequest operationRequest)
0x2f62  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x2f67  stloc.2
0x2f68  ldloca.s 2
0x2f6a  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x2f6f  brtrue.s loc_2FAD
0x2f71  ldarg.0
0x2f72  ldc.i4.0
0x2f73  dup
0x2f74  stloc.0
0x2f75  stfld    int32 <HandleResultAsync>d__4::<>1__state
0x2f7a  ldarg.0
0x2f7b  ldloc.2
0x2f7c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleResultAsync>d__4::<>u__1
0x2f81  ldarg.0
0x2f82  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleResultAsync>d__4::<>t__builder
0x2f87  ldloca.s 2
0x2f89  ldarg.0
0x2f8a  call     T0x2B000077
0x2f8f  leave.s  loc_2FE8
0x2f91  ldarg.0
0x2f92  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleResultAsync>d__4::<>u__1
0x2f97  stloc.2
0x2f98  ldarg.0
0x2f99  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <HandleResultAsync>d__4::<>u__1
0x2f9e  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x2fa4  ldarg.0
0x2fa5  ldc.i4.m1
0x2fa6  dup
0x2fa7  stloc.0
0x2fa8  stfld    int32 <HandleResultAsync>d__4::<>1__state
0x2fad  ldloca.s 2
0x2faf  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x2fb4  ldloca.s 2
0x2fb6  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x2fbc  leave.s  loc_2FD5
0x2fbe  stloc.3
0x2fbf  ldarg.0
0x2fc0  ldc.i4.s 0xFE
0x2fc2  stfld    int32 <HandleResultAsync>d__4::<>1__state
0x2fc7  ldarg.0
0x2fc8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleResultAsync>d__4::<>t__builder
0x2fcd  ldloc.3
0x2fce  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x2fd3  leave.s  loc_2FE8
0x2fd5  ldarg.0
0x2fd6  ldc.i4.s 0xFE
0x2fd8  stfld    int32 <HandleResultAsync>d__4::<>1__state
0x2fdd  ldarg.0
0x2fde  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <HandleResultAsync>d__4::<>t__builder
0x2fe3  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x2fe8  ret
```
