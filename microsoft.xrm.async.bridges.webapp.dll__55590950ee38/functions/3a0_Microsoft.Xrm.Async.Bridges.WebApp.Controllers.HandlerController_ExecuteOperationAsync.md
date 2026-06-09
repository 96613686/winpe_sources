# Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::ExecuteOperationAsync

- ea: `0x3a0`
- end: `0x3e1`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController::ExecuteOperationAsync`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  ldloca.s 0
0x3a2  ldarg.0
0x3a3  stfld    class Microsoft.Xrm.Async.Bridges.WebApp.Controllers.HandlerController <ExecuteOperationAsync>d__4::<>4__this
0x3a8  ldloca.s 0
0x3aa  ldarg.1
0x3ab  stfld    class [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.AsyncOperation <ExecuteOperationAsync>d__4::operation
0x3b0  ldloca.s 0
0x3b2  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::Create()
0x3b7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <ExecuteOperationAsync>d__4::<>t__builder
0x3bc  ldloca.s 0
0x3be  ldc.i4.m1
0x3bf  stfld    int32 <ExecuteOperationAsync>d__4::<>1__state
0x3c4  ldloc.0
0x3c5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <ExecuteOperationAsync>d__4::<>t__builder
0x3ca  stloc.1
0x3cb  ldloca.s 1
0x3cd  ldloca.s 0
0x3cf  call     T0x2B00000F
0x3d4  ldloca.s 0
0x3d6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult> <ExecuteOperationAsync>d__4::<>t__builder
0x3db  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Web.Http]System.Web.Http.IHttpActionResult>::get_Task()
0x3e0  ret
```
