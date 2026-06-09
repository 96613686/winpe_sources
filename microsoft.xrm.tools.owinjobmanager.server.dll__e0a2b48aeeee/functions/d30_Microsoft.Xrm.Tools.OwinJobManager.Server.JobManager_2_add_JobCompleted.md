# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::add_JobCompleted

- ea: `0xd30`
- end: `0xd59`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::add_JobCompleted`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xd30`

## pseudocode

```c

```

## disassembly

```asm
0xd30  ldarg.0
0xd31  ldfld    class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobCompleted
0xd36  stloc.0
0xd37  ldloc.0
0xd38  stloc.1
0xd39  ldloc.1
0xd3a  ldarg.1
0xd3b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xd40  castclass class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs>
0xd45  stloc.2
0xd46  ldarg.0
0xd47  ldflda   class [mscorlib]System.EventHandler`1<class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobEventArgs> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::JobCompleted
0xd4c  ldloc.2
0xd4d  ldloc.1
0xd4e  call     T0x2B000001
0xd53  stloc.0
0xd54  ldloc.0
0xd55  ldloc.1
0xd56  bne.un.s loc_D37
0xd58  ret
```
