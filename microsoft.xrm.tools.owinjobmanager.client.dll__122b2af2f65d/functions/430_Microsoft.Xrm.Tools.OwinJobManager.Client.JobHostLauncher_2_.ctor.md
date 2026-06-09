# Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::.ctor

- ea: `0x430`
- end: `0x459`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2::.ctor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x430`

## pseudocode

```c

```

## disassembly

```asm
0x430  ldarg.0
0x431  call     instance void [mscorlib]System.Object::.ctor()
0x436  ldarg.1
0x437  brtrue.s loc_444
0x439  ldstr    aInitprocess// "initProcess"
0x43e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x443  throw
0x444  ldarg.0
0x445  ldarg.1
0x446  stfld    class [mscorlib]System.Action`1<class [System]System.Diagnostics.ProcessStartInfo> class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::initProcess
0x44b  ldarg.0
0x44c  ldarg.2
0x44d  ldarg.3
0x44e  newobj   instance void class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0>::.ctor(string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.TimeSpan>)
0x453  stfld    class Microsoft.Xrm.Tools.OwinJobManager.Client.JobApiClient`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Client.JobHostLauncher`2<var<u1>, !!T0>::client
0x458  ret
```
