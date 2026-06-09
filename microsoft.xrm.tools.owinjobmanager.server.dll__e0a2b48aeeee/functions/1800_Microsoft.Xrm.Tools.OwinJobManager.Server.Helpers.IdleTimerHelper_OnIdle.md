# Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::OnIdle

- ea: `0x1800`
- end: `0x1852`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::OnIdle`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18a0`

## callees

- `0x1800`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldarg.0
0x1801  ldfld    object Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timerLock
0x1806  stloc.0
0x1807  ldc.i4.0
0x1808  stloc.1
0x1809  ldloc.0
0x180a  ldloca.s 1
0x180c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1811  ldarg.0
0x1812  ldfld    class [mscorlib]System.Threading.Timer Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timer
0x1817  dup
0x1818  brtrue.s loc_181D
0x181a  pop
0x181b  br.s     loc_1822
0x181d  call     instance void [mscorlib]System.Threading.Timer::Dispose()
0x1822  ldarg.0
0x1823  ldarg.0
0x1824  ldftn    instance void Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::<OnIdle>b__6_0(object _)
0x182a  newobj   instance void [mscorlib]System.Threading.TimerCallback::.ctor(object, native int)
0x182f  ldnull
0x1830  ldarg.0
0x1831  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timeout
0x1836  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.Threading.Timeout::InfiniteTimeSpan
0x183b  newobj   instance void [mscorlib]System.Threading.Timer::.ctor(class [mscorlib]System.Threading.TimerCallback, object, valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1840  stfld    class [mscorlib]System.Threading.Timer Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timer
0x1845  leave.s  loc_1851
0x1847  ldloc.1
0x1848  brfalse.s loc_1850
0x184a  ldloc.0
0x184b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1850  endfinally
0x1851  ret
```
