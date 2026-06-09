# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManagerExtensions::ConnectIdleTimer

- ea: `0xc60`
- end: `0xcb6`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManagerExtensions::ConnectIdleTimer`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0xc60`
- `0x13c0`
- `0x13e0`
- `0x1880`

## pseudocode

```c

```

## disassembly

```asm
0xc60  newobj   instance void <>c__DisplayClass0_0::.ctor()
0xc65  stloc.0
0xc66  ldloc.0
0xc67  ldarg.1
0xc68  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper <>c__DisplayClass0_0::idleTimerHelper
0xc6d  ldloc.0
0xc6e  ldarg.0
0xc6f  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJobManager <>c__DisplayClass0_0::jobManager
0xc74  ldloc.0
0xc75  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper <>c__DisplayClass0_0::idleTimerHelper
0xc7a  brtrue.s loc_C87
0xc7c  ldstr    aIdletimerhelpe// "idleTimerHelper"
0xc81  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xc86  throw
0xc87  ldloc.0
0xc88  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJobManager <>c__DisplayClass0_0::jobManager
0xc8d  ldloc.0
0xc8e  ldftn    instance void <>c__DisplayClass0_0::<ConnectIdleTimer>b__0(object _, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs __)
0xc94  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs>::.ctor(object, native int)
0xc99  callvirt instance void Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJobManager::add_JobAdded(class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> value)
0xc9e  ldloc.0
0xc9f  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJobManager <>c__DisplayClass0_0::jobManager
0xca4  ldloc.0
0xca5  ldftn    instance void <>c__DisplayClass0_0::<ConnectIdleTimer>b__1(object _, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs __)
0xcab  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs>::.ctor(object, native int)
0xcb0  callvirt instance void Microsoft.Xrm.Tools.OwinJobManager.Server.Model.IJobManager::add_JobCompleted(class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> value)
0xcb5  ret
```
