# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::add_JobAdded

- ea: `0xcd0`
- end: `0xcf9`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::add_JobAdded`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xcd0`

## pseudocode

```c

```

## disassembly

```asm
0xcd0  ldarg.0
0xcd1  ldfld    class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobAdded
0xcd6  stloc.0
0xcd7  ldloc.0
0xcd8  stloc.1
0xcd9  ldloc.1
0xcda  ldarg.1
0xcdb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xce0  castclass class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs>
0xce5  stloc.2
0xce6  ldarg.0
0xce7  ldflda   class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobAdded
0xcec  ldloc.2
0xced  ldloc.1
0xcee  call     T0x2B000001
0xcf3  stloc.0
0xcf4  ldloc.0
0xcf5  ldloc.1
0xcf6  bne.un.s loc_CD7
0xcf8  ret
```
