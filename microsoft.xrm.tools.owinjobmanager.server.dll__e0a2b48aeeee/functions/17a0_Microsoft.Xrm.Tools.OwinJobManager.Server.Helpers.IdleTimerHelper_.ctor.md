# Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::.ctor

- ea: `0x17a0`
- end: `0x17ce`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x17a0`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  ldarg.0
0x17a1  newobj   instance void [mscorlib]System.Object::.ctor()
0x17a6  stfld    object Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timerLock
0x17ab  ldarg.0
0x17ac  call     instance void [mscorlib]System.Object::.ctor()
0x17b1  ldarg.2
0x17b2  brtrue.s loc_17BF
0x17b4  ldstr    aSignal// "signal"
0x17b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17be  throw
0x17bf  ldarg.0
0x17c0  ldarg.1
0x17c1  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timeout
0x17c6  ldarg.0
0x17c7  ldarg.2
0x17c8  stfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::signal
0x17cd  ret
```
