# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::Add

- ea: `0xdc0`
- end: `0xe5f`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::Add`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xdc0`
- `0x1760`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  newobj   instance void class <>c__DisplayClass9_0<var<u1>, !!T0>::.ctor()
0xdc5  stloc.0
0xdc6  ldloc.0
0xdc7  ldarg.0
0xdc8  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::<>4__this
0xdcd  ldloc.0
0xdce  ldarg.1
0xdcf  ldarg.0
0xdd0  ldfld    class [mscorlib]System.Action`3<var<u1>, !!T0, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobOutput`1<var<u1>>> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::processor
0xdd5  newobj   instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::.ctor(var<u1>, !!T0)
0xdda  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::job
0xddf  ldloc.0
0xde0  ldloc.0
0xde1  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::job
0xde6  newobj   instance void Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs::.ctor(class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJob job)
0xdeb  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs class <>c__DisplayClass9_0<var<u1>, !!T0>::jobEventArgs
0xdf0  ldloc.0
0xdf1  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::job
0xdf6  ldloc.0
0xdf7  ldftn    instance void class <>c__DisplayClass9_0<var<u1>, !!T0>::<Add>b__0(object, class [mscorlib]System.EventArgs)
0xdfd  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0xe02  callvirt instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::add_JobCompleted(class [mscorlib]System.EventHandler)
0xe07  ldarg.0
0xe08  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::jobs
0xe0d  ldloc.0
0xe0e  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::job
0xe13  callvirt instance valuetype [mscorlib]System.Guid class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_Id()
0xe18  ldloc.0
0xe19  ldftn    instance class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::<Add>b__1(var<u1>)
0xe1f  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::.ctor(object, native int)
0xe24  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::GetOrAdd(void, var<u1>)
0xe29  pop
0xe2a  ldarg.0
0xe2b  ldfld    class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobAdded
0xe30  dup
0xe31  brtrue.s loc_E36
0xe33  pop
0xe34  br.s     loc_E42
0xe36  ldarg.0
0xe37  ldloc.0
0xe38  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs class <>c__DisplayClass9_0<var<u1>, !!T0>::jobEventArgs
0xe3d  callvirt instance void class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs>::Invoke(object, var<u1>)
0xe42  ldarg.2
0xe43  ldc.i4.0
0xe44  ble.s    loc_E58
0xe46  ldloc.0
0xe47  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::job
0xe4c  callvirt instance class [mscorlib]System.Threading.Tasks.Task class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::get_PostProcessTask()
0xe51  ldarg.2
0xe52  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::Wait(int32)
0xe57  pop
0xe58  ldloc.0
0xe59  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0> class <>c__DisplayClass9_0<var<u1>, !!T0>::job
0xe5e  ret
```
