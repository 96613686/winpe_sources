# Microsoft.Crm.Throttler::StartTimers

- ea: `0x1f0`
- end: `0x273`
- name: `Microsoft.Crm.Throttler::StartTimers`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x190`

## callees

- `0x1f0`

## pseudocode

```c

```

## disassembly

```asm
0x1f0  ldsfld   class [System]System.Timers.Timer Microsoft.Crm.Throttler::_timer
0x1f5  brfalse.s loc_1F8
0x1f7  ret
0x1f8  ldsfld   object Microsoft.Crm.Throttler::_timerSync
0x1fd  stloc.0
0x1fe  ldc.i4.0
0x1ff  stloc.1
0x200  ldloc.0
0x201  ldloca.s 1
0x203  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x208  ldsfld   class [System]System.Timers.Timer Microsoft.Crm.Throttler::_timer
0x20d  brfalse.s loc_211
0x20f  leave.s  loc_272
0x211  newobj   instance void [System]System.Timers.Timer::.ctor()
0x216  stsfld   class [System]System.Timers.Timer Microsoft.Crm.Throttler::_timer
0x21b  ldsfld   class [System]System.Timers.Timer Microsoft.Crm.Throttler::_timer
0x220  ldc.r8   5.0
0x229  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x22e  stloc.2
0x22f  ldloca.s 2
0x231  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x236  callvirt instance void [System]System.Timers.Timer::set_Interval(float64)
0x23b  ldsfld   class [System]System.Timers.Timer Microsoft.Crm.Throttler::_timer
0x240  ldc.i4.1
0x241  callvirt instance void [System]System.Timers.Timer::set_AutoReset(bool)
0x246  ldsfld   class [System]System.Timers.Timer Microsoft.Crm.Throttler::_timer
0x24b  ldnull
0x24c  ldftn    void Microsoft.Crm.Throttler::TimerElapsed(object sender, class [System]System.Timers.ElapsedEventArgs e)
0x252  newobj   instance void [System]System.Timers.ElapsedEventHandler::.ctor(object, native int)
0x257  callvirt instance void [System]System.Timers.Timer::add_Elapsed(class [System]System.Timers.ElapsedEventHandler)
0x25c  ldsfld   class [System]System.Timers.Timer Microsoft.Crm.Throttler::_timer
0x261  callvirt instance void [System]System.Timers.Timer::Start()
0x266  leave.s  loc_272
0x268  ldloc.1
0x269  brfalse.s loc_271
0x26b  ldloc.0
0x26c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x271  endfinally
0x272  ret
```
