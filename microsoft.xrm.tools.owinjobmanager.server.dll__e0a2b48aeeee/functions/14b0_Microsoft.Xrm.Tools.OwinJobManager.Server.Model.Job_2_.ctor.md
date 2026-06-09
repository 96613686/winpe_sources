# Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::.ctor

- ea: `0x14b0`
- end: `0x153e`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::.ctor`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x14b0  ldarg.0
0x14b1  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x14b6  stfld    valuetype [mscorlib]System.Guid class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::<Id>k__BackingField
0x14bb  newobj   instance void class <>c__DisplayClass5_0<var<u1>, !!T0>::.ctor()
0x14c0  stloc.0
0x14c1  ldloc.0
0x14c2  ldarg.2
0x14c3  stfld    class [mscorlib]System.Action`3<var<u1>, !!T0, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>> class <>c__DisplayClass5_0<var<u1>, !!T0>::processor
0x14c8  ldloc.0
0x14c9  ldarg.1
0x14ca  stfld    var<u1> class <>c__DisplayClass5_0<var<u1>, !!T0>::input
0x14cf  ldarg.0
0x14d0  call     instance void [mscorlib]System.Object::.ctor()
0x14d5  ldloc.0
0x14d6  ldarg.0
0x14d7  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::<>4__this
0x14dc  ldarg.0
0x14dd  ldloc.0
0x14de  ldfld    var<u1> class <>c__DisplayClass5_0<var<u1>, !!T0>::input
0x14e3  stfld    var<u1> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::<Input>k__BackingField
0x14e8  ldarg.0
0x14e9  newobj   instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>::.ctor()
0x14ee  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::<Output>k__BackingField
0x14f3  ldarg.0
0x14f4  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x14f9  stfld    class [mscorlib]System.Threading.CancellationTokenSource class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::cts
0x14fe  ldarg.0
0x14ff  ldloc.0
0x1500  ldftn    instance void class <>c__DisplayClass5_0<var<u1>, !!T0>::<.ctor>b__0()
0x1506  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x150b  ldarg.0
0x150c  ldfld    class [mscorlib]System.Threading.CancellationTokenSource class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::cts
0x1511  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x1516  call     class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::Run(class [mscorlib]System.Action, valuetype [mscorlib]System.Threading.CancellationToken)
0x151b  stfld    class [mscorlib]System.Threading.Tasks.Task class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::<Task>k__BackingField
0x1520  ldarg.0
0x1521  ldarg.0
0x1522  call     instance class [mscorlib]System.Threading.Tasks.Task class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Task()
0x1527  ldarg.0
0x1528  ldftn    instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::<.ctor>b__5_1(class [mscorlib]System.Threading.Tasks.Task)
0x152e  newobj   instance void class [mscorlib]System.Action`1<class [mscorlib]System.Threading.Tasks.Task>::.ctor(object, native int)
0x1533  callvirt instance class [mscorlib]System.Threading.Tasks.Task [mscorlib]System.Threading.Tasks.Task::ContinueWith(class [mscorlib]System.Action`1<class [mscorlib]System.Threading.Tasks.Task>)
0x1538  stfld    class [mscorlib]System.Threading.Tasks.Task class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::<PostProcessTask>k__BackingField
0x153d  ret
```
