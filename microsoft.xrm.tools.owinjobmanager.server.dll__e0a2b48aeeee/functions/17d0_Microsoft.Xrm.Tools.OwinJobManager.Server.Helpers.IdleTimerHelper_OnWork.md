# Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::OnWork

- ea: `0x17d0`
- end: `0x17ff`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::OnWork`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1890`

## callees

- `0x17d0`

## pseudocode

```c

```

## disassembly

```asm
0x17d0  ldarg.0
0x17d1  ldfld    object Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timerLock
0x17d6  stloc.0
0x17d7  ldc.i4.0
0x17d8  stloc.1
0x17d9  ldloc.0
0x17da  ldloca.s 1
0x17dc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x17e1  ldarg.0
0x17e2  ldfld    class [mscorlib]System.Threading.Timer Microsoft.Xrm.Tools.OwinJobManager.Server.Helpers.IdleTimerHelper::timer
0x17e7  dup
0x17e8  brtrue.s loc_17ED
0x17ea  pop
0x17eb  leave.s  loc_17FE
0x17ed  call     instance void [mscorlib]System.Threading.Timer::Dispose()
0x17f2  leave.s  loc_17FE
0x17f4  ldloc.1
0x17f5  brfalse.s loc_17FD
0x17f7  ldloc.0
0x17f8  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x17fd  endfinally
0x17fe  ret
```
