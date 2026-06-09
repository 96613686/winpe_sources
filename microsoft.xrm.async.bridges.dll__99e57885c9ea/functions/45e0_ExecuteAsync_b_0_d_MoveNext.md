# <<ExecuteAsync>b__0>d::MoveNext

- ea: `0x45e0`
- end: `0x4692`
- name: `<<ExecuteAsync>b__0>d::MoveNext`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0xd0`
- `0x45e0`

## pseudocode

```c

```

## disassembly

```asm
0x45e0  ldarg.0
0x45e1  ldfld    int32 <<ExecuteAsync>b__0>d::<>1__state
0x45e6  stloc.0
0x45e7  ldloc.0
0x45e8  brfalse.s loc_463A
0x45ea  ldarg.0
0x45eb  ldfld    class <>c__DisplayClass3_0 <<ExecuteAsync>b__0>d::<>4__this
0x45f0  ldfld    class Microsoft.Xrm.Async.Bridges.AcceptingAsyncHandlerHost <>c__DisplayClass3_0::<>4__this
0x45f5  ldarg.0
0x45f6  ldfld    class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> <<ExecuteAsync>b__0>d::task
0x45fb  ldarg.0
0x45fc  ldfld    class <>c__DisplayClass3_0 <<ExecuteAsync>b__0>d::<>4__this
0x4601  ldfld    class Microsoft.Xrm.Async.Bridges.OperationRequest <>c__DisplayClass3_0::operationRequest
0x4606  call     instance class [mscorlib]System.Threading.Tasks.Task Microsoft.Xrm.Async.Bridges.AcceptingAsyncHandlerHost::HandleResultAsync(class [mscorlib]System.Threading.Tasks.Task`1<class Microsoft.Xrm.Async.Bridges.Providers.Crm.IAsyncHandlerResult> taskResult, class Microsoft.Xrm.Async.Bridges.OperationRequest operationRequest)
0x460b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x4610  stloc.1
0x4611  ldloca.s 1
0x4613  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x4618  brtrue.s loc_4656
0x461a  ldarg.0
0x461b  ldc.i4.0
0x461c  dup
0x461d  stloc.0
0x461e  stfld    int32 <<ExecuteAsync>b__0>d::<>1__state
0x4623  ldarg.0
0x4624  ldloc.1
0x4625  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<ExecuteAsync>b__0>d::<>u__1
0x462a  ldarg.0
0x462b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<ExecuteAsync>b__0>d::<>t__builder
0x4630  ldloca.s 1
0x4632  ldarg.0
0x4633  call     T0x2B00008B
0x4638  leave.s  loc_4691
0x463a  ldarg.0
0x463b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<ExecuteAsync>b__0>d::<>u__1
0x4640  stloc.1
0x4641  ldarg.0
0x4642  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <<ExecuteAsync>b__0>d::<>u__1
0x4647  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x464d  ldarg.0
0x464e  ldc.i4.m1
0x464f  dup
0x4650  stloc.0
0x4651  stfld    int32 <<ExecuteAsync>b__0>d::<>1__state
0x4656  ldloca.s 1
0x4658  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x465d  ldloca.s 1
0x465f  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x4665  leave.s  loc_467E
0x4667  stloc.2
0x4668  ldarg.0
0x4669  ldc.i4.s 0xFE
0x466b  stfld    int32 <<ExecuteAsync>b__0>d::<>1__state
0x4670  ldarg.0
0x4671  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<ExecuteAsync>b__0>d::<>t__builder
0x4676  ldloc.2
0x4677  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x467c  leave.s  loc_4691
0x467e  ldarg.0
0x467f  ldc.i4.s 0xFE
0x4681  stfld    int32 <<ExecuteAsync>b__0>d::<>1__state
0x4686  ldarg.0
0x4687  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <<ExecuteAsync>b__0>d::<>t__builder
0x468c  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x4691  ret
```
