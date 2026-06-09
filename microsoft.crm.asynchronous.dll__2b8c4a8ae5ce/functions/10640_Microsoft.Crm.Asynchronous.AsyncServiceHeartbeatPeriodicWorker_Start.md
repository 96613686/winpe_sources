# Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::Start

- ea: `0x10640`
- end: `0x1068d`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::Start`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10640`

## string_xrefs

- `0x10664`: `AsyncServiceHeartbeatTimer`

## pseudocode

```c

```

## disassembly

```asm
0x10640  ldarg.0
0x10641  ldfld    int32 Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::period
0x10646  ldc.i4   0x3E8
0x1064b  mul
0x1064c  stloc.0
0x1064d  ldarg.0
0x1064e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::timer
0x10653  ldnull
0x10654  cgt.un
0x10656  brfalse.s loc_10663
0x10658  ldarg.0
0x10659  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::timer
0x1065e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer::Stop()
0x10663  ldarg.0
0x10664  ldstr    aAsyncservicehe// "AsyncServiceHeartbeatTimer"
0x10669  ldloc.0
0x1066a  conv.r8
0x1066b  ldarg.0
0x1066c  ldftn    instance void Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::Elapsed(object sender, class [Microsoft.Crm.Core]Microsoft.Crm.Timers.ElapsedEventArgs elapsedEventArgs)
0x10672  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Core]Microsoft.Crm.Timers.ElapsedEventArgs>::.ctor(object, native int)
0x10677  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer::.ctor(string, float64, class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Core]Microsoft.Crm.Timers.ElapsedEventArgs>)
0x1067c  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::timer
0x10681  ldarg.0
0x10682  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Asynchronous.AsyncServiceHeartbeatPeriodicWorker::timer
0x10687  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer::Start()
0x1068c  ret
```
