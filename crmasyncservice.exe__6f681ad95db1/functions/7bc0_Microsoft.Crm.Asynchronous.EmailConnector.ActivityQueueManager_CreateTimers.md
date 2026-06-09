# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::CreateTimers

- ea: `0x7bc0`
- end: `0x7bf5`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::CreateTimers`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x7c00`

## pseudocode

```c

```

## disassembly

```asm
0x7bc0  ldarg.0
0x7bc1  call     instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueManager::CreateTimers()
0x7bc6  dup
0x7bc7  ldarg.0
0x7bc8  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::CreateCancelWaitingOperation()
0x7bcd  ldc.r8   0.2
0x7bd6  ldarg.0
0x7bd7  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IQueueConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueManager::get_Configuration()
0x7bdc  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ISharedQueueConfiguration::get_AsyncWaitingTimeout()
0x7be1  stloc.0
0x7be2  ldloca.s 0
0x7be4  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x7be9  mul
0x7bea  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation, float64)
0x7bef  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x7bf4  ret
```
