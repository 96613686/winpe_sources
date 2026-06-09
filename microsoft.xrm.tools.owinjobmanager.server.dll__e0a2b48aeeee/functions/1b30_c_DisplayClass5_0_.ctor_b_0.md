# <>c__DisplayClass5_0::<.ctor>b__0

- ea: `0x1b30`
- end: `0x1b89`
- name: `<>c__DisplayClass5_0::<.ctor>b__0`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x1b30  ldarg.0
0x1b31  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::<>4__this
0x1b36  ldc.i4.1
0x1b37  call     instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::set_Status(valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus)
0x1b3c  ldarg.0
0x1b3d  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::<>4__this
0x1b42  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0x1b47  stfld    class [System]System.Diagnostics.Stopwatch class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::watch
0x1b4c  ldarg.0
0x1b4d  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::<>4__this
0x1b52  ldfld    class [System]System.Diagnostics.Stopwatch class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::watch
0x1b57  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0x1b5c  ldarg.0
0x1b5d  ldfld    class [mscorlib]System.Action`3<var<u1>, !!T0, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>> class <>c__DisplayClass5_0<var<u1>, !!T0>::processor
0x1b62  ldarg.0
0x1b63  ldfld    var<u1> class <>c__DisplayClass5_0<var<u1>, !!T0>::input
0x1b68  ldarg.0
0x1b69  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::<>4__this
0x1b6e  call     instance class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>> class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Output()
0x1b73  ldarg.0
0x1b74  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass5_0<var<u1>, !!T0>::<>4__this
0x1b79  ldfld    class [mscorlib]System.Threading.CancellationTokenSource class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::cts
0x1b7e  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x1b83  callvirt instance void class [mscorlib]System.Action`3<var<u1>, !!T0, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>>::Invoke(var<u1>, !!T0, var<u1>)
0x1b88  ret
```
