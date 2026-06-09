# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::remove_JobAdded

- ea: `0xd00`
- end: `0xd29`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::remove_JobAdded`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xd00`

## pseudocode

```c

```

## disassembly

```asm
0xd00  ldarg.0
0xd01  ldfld    class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobAdded
0xd06  stloc.0
0xd07  ldloc.0
0xd08  stloc.1
0xd09  ldloc.1
0xd0a  ldarg.1
0xd0b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xd10  castclass class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs>
0xd15  stloc.2
0xd16  ldarg.0
0xd17  ldflda   class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobAdded
0xd1c  ldloc.2
0xd1d  ldloc.1
0xd1e  call     T0x2B000001
0xd23  stloc.0
0xd24  ldloc.0
0xd25  ldloc.1
0xd26  bne.un.s loc_D07
0xd28  ret
```
