# Microsoft.Crm.Asynchronous.PriorityOperationQueueManager::CreateTimers

- ea: `0xec00`
- end: `0xec3a`
- name: `Microsoft.Crm.Asynchronous.PriorityOperationQueueManager::CreateTimers`
- size: `58`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x4bd0`
- `0x4c20`
- `0x5a20`
- `0x6e60`
- `0x9d70`
- `0x9de0`

## pseudocode

```c

```

## disassembly

```asm
0xec00  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::.ctor()
0xec05  stloc.0
0xec06  ldloc.0
0xec07  ldarg.0
0xec08  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.QueueManager::CreateSelectTimerOperation()
0xec0d  ldarg.0
0xec0e  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0xec13  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_SelectPriorityJobInterval()
0xec18  stloc.1
0xec19  ldloca.s 1
0xec1b  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xec20  newobj   instance void Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation, float64 interval)
0xec25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0xec2a  ldarg.0
0xec2b  ldloc.0
0xec2c  call     instance void Microsoft.Crm.Asynchronous.QueueManager::AddDiagnosticModeTimerEvent(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> timers)
0xec31  ldarg.0
0xec32  ldloc.0
0xec33  call     instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateCommonTimers(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> timers)
0xec38  ldloc.0
0xec39  ret
```
