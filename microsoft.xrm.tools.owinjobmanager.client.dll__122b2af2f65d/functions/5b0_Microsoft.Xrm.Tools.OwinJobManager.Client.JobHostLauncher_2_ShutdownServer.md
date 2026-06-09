# Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::ShutdownServer

- ea: `0x5b0`
- end: `0x5e1`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::ShutdownServer`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5b0`

## pseudocode

```c

```

## disassembly

```asm
0x5b0  ldarg.0
0x5b1  ldfld    class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::client
0x5b6  callvirt instance int32 class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::GetHostProcessId()
0x5bb  stloc.0
0x5bc  ldloc.0
0x5bd  brtrue.s loc_5D5
0x5bf  ldstr    aInvalidPdApiHo// "Invalid PD API Host process id returned"...
0x5c4  ldloc.0
0x5c5  box      [mscorlib]System.Int32
0x5ca  call     string [mscorlib]System.String::Concat(object, object)
0x5cf  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x5d4  throw
0x5d5  ldloc.0
0x5d6  call     class [System]System.Diagnostics.Process class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::TryGetProcessById(int32)
0x5db  call     bool class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::TryKill(class [System]System.Diagnostics.Process)
0x5e0  ret
```
