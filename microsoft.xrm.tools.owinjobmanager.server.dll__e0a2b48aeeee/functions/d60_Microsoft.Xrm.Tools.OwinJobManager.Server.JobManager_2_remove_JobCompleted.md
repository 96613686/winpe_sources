# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::remove_JobCompleted

- ea: `0xd60`
- end: `0xd89`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::remove_JobCompleted`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.0
0xd61  ldfld    class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobCompleted
0xd66  stloc.0
0xd67  ldloc.0
0xd68  stloc.1
0xd69  ldloc.1
0xd6a  ldarg.1
0xd6b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xd70  castclass class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs>
0xd75  stloc.2
0xd76  ldarg.0
0xd77  ldflda   class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobCompleted
0xd7c  ldloc.2
0xd7d  ldloc.1
0xd7e  call     T0x2B000001
0xd83  stloc.0
0xd84  ldloc.0
0xd85  ldloc.1
0xd86  bne.un.s loc_D67
0xd88  ret
```
