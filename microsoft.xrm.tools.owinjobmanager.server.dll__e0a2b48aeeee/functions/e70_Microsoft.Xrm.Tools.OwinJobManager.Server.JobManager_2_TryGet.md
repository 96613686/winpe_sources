# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::TryGet

- ea: `0xe70`
- end: `0xe99`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::TryGet`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xe70`

## pseudocode

```c

```

## disassembly

```asm
0xe70  ldarg.1
0xe71  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe76  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe7b  brfalse.s loc_E88
0xe7d  ldstr    aJobid// "jobId"
0xe82  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe87  throw
0xe88  ldarg.0
0xe89  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::jobs
0xe8e  ldarg.1
0xe8f  ldloca.s 0
0xe91  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::TryGetValue(var<u1>, !!T0)
0xe96  pop
0xe97  ldloc.0
0xe98  ret
```
