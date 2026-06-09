# Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::<.ctor>b__5_1

- ea: `0x1650`
- end: `0x16a7`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2::<.ctor>b__5_1`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1650`

## pseudocode

```c

```

## disassembly

```asm
0x1650  ldarg.0
0x1651  ldfld    class [System]System.Diagnostics.Stopwatch class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::watch
0x1656  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x165b  ldarg.1
0x165c  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::get_IsFaulted()
0x1661  brfalse.s loc_1678
0x1663  ldarg.0
0x1664  ldarg.1
0x1665  callvirt instance class [mscorlib]System.AggregateException [mscorlib]System.Threading.Tasks.Task::get_Exception()
0x166a  call     instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::set_Exception(class [mscorlib]System.Exception)
0x166f  ldarg.0
0x1670  ldc.i4.3
0x1671  call     instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::set_Status(valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus)
0x1676  br.s     loc_1690
0x1678  ldarg.1
0x1679  callvirt instance bool [mscorlib]System.Threading.Tasks.Task::get_IsCanceled()
0x167e  brfalse.s loc_1689
0x1680  ldarg.0
0x1681  ldc.i4.2
0x1682  call     instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::set_Status(valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus)
0x1687  br.s     loc_1690
0x1689  ldarg.0
0x168a  ldc.i4.4
0x168b  call     instance void class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::set_Status(valuetype Microsoft.Xrm.Tools.OwinJobManager.Server.Model.JobStatus)
0x1690  ldarg.0
0x1691  ldfld    class [mscorlib]System.EventHandler class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>::JobCompleted
0x1696  dup
0x1697  brtrue.s loc_169B
0x1699  pop
0x169a  ret
0x169b  ldarg.0
0x169c  ldsfld   class [mscorlib]System.EventArgs [mscorlib]System.EventArgs::Empty
0x16a1  callvirt instance void [mscorlib]System.EventHandler::Invoke(object, class [mscorlib]System.EventArgs)
0x16a6  ret
```
