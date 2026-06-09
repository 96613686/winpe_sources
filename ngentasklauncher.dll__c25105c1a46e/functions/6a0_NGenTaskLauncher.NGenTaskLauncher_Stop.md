# NGenTaskLauncher.NGenTaskLauncher::Stop

- ea: `0x6a0`
- end: `0x726`
- name: `NGenTaskLauncher.NGenTaskLauncher::Stop`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x120`

## callees

- `0x6a0`
- `0x7d0`

## string_xrefs

- `0x707`: `Error stopping NGen Task`

## pseudocode

```c

```

## disassembly

```asm
0x6a0  ldarg.0
0x6a1  ldfld    object NGenTaskLauncher.NGenTaskLauncher::m_stopLock
0x6a6  stloc.0
0x6a7  ldc.i4.0
0x6a8  stloc.1
0x6a9  ldloc.0
0x6aa  ldloca.s 1
0x6ac  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6b1  ldarg.0
0x6b2  ldc.i4.1
0x6b3  volatile.
0x6b5  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTaskLauncher.NGenTaskLauncher::m_stopRequested
0x6ba  ldarg.0
0x6bb  ldfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x6c0  brfalse.s loc_719
0x6c2  ldarg.0
0x6c3  ldfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x6c8  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x6cd  brtrue.s loc_719
0x6cf  ldarg.0
0x6d0  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTaskLauncher.NGenTaskLauncher::m_childStopEvent
0x6d5  brfalse.s loc_6F6
0x6d7  ldarg.0
0x6d8  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTaskLauncher.NGenTaskLauncher::m_childStopEvent
0x6dd  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x6e2  brfalse.s loc_6F6
0x6e4  ldarg.0
0x6e5  ldfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x6ea  ldc.i4   0x7D0
0x6ef  callvirt instance bool [System]System.Diagnostics.Process::WaitForExit(int32)
0x6f4  brtrue.s loc_719
0x6f6  nop
0x6f7  ldarg.0
0x6f8  ldfld    class [System]System.Diagnostics.Process NGenTaskLauncher.NGenTaskLauncher::m_childProcess
0x6fd  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x702  leave.s  loc_725
0x704  stloc.2
0x705  ldc.i4.0
0x706  ldloc.2
0x707  ldstr    aErrorStoppingN// "Error stopping NGen Task"
0x70c  ldc.i4.0
0x70d  newarr   [mscorlib]System.Object
0x712  call     void NGenTaskLauncher.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x717  leave.s  loc_725
0x719  leave.s  loc_725
0x71b  ldloc.1
0x71c  brfalse.s loc_724
0x71e  ldloc.0
0x71f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x724  endfinally
0x725  ret
```
