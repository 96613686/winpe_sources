# Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::TryRemove

- ea: `0xea0`
- end: `0xec7`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2::TryRemove`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xea0`

## pseudocode

```c

```

## disassembly

```asm
0xea0  ldarg.1
0xea1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xea6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xeab  brfalse.s loc_EB8
0xead  ldstr    aJobid// "jobId"
0xeb2  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xeb7  throw
0xeb8  ldarg.0
0xeb9  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::jobs
0xebe  ldarg.1
0xebf  ldloca.s 0
0xec1  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Xrm.Tools.OwinJobManager.Server.Model.Job`2<var<u1>, !!T0>>::TryRemove(var<u1>, !!T0)
0xec6  ret
```
