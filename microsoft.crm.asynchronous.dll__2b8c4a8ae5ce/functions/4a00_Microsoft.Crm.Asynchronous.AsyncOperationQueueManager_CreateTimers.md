# Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateTimers

- ea: `0x4a00`
- end: `0x4a58`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateTimers`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x4a80`
- `0x4ab0`
- `0x4bd0`
- `0x4c20`
- `0x5990`
- `0x59b0`
- `0x6e60`
- `0x9d30`

## pseudocode

```c

```

## disassembly

```asm
0x4a00  ldarg.0
0x4a01  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> Microsoft.Crm.Asynchronous.QueueManager::CreateTimers()
0x4a06  stloc.0
0x4a07  ldloc.0
0x4a08  ldarg.0
0x4a09  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateOnMoveSuspendedToReadyTimerOperation()
0x4a0e  ldarg.0
0x4a0f  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x4a14  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_MoveToReadyInterval()
0x4a19  stloc.1
0x4a1a  ldloca.s 1
0x4a1c  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x4a21  newobj   instance void Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation, float64 interval)
0x4a26  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x4a2b  ldloc.0
0x4a2c  ldarg.0
0x4a2d  call     instance class Microsoft.Crm.Asynchronous.Operations.IServiceOperation Microsoft.Crm.Asynchronous.AsyncOperationQueueManager::CreateOnTimeoutLockedTimerOperation()
0x4a32  ldarg.0
0x4a33  call     instance class Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::get_FullConfiguration()
0x4a38  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncOperationQueueConfiguration::get_TimeoutLockedInterval()
0x4a3d  stloc.1
0x4a3e  ldloca.s 1
0x4a40  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x4a45  newobj   instance void Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine::.ctor(class Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation, float64 interval)
0x4a4a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine>::Add(var<u1>)
0x4a4f  ldarg.0
0x4a50  ldloc.0
0x4a51  call     instance void Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase::CreateCommonTimers(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.TimerBasedExecutionEngine> timers)
0x4a56  ldloc.0
0x4a57  ret
```
