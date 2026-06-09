# Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteWaitingOperation

- ea: `0xa490`
- end: `0xa4b9`
- name: `Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteWaitingOperation`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x8040`

## callees

- `0x12080`
- `0x121f0`
- `0x122a0`
- `0x12350`

## pseudocode

```c

```

## disassembly

```asm
0xa490  ldarg.0
0xa491  ldfld    class Microsoft.Crm.Asynchronous.IQueuePerformanceCounters Microsoft.Crm.Asynchronous.QueueManager::_counters
0xa496  ldarg.1
0xa497  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa49c  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xa4a1  ldarg.1
0xa4a2  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_WaitingForCompletionTime()
0xa4a7  callvirt instance void Microsoft.Crm.Asynchronous.IQueuePerformanceCounters::TrackCompleteWaitingOperation(int32 operationType, valuetype [mscorlib]System.TimeSpan elapsedTime)
0xa4ac  ldarg.0
0xa4ad  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_waitingOperations
0xa4b2  ldarg.1
0xa4b3  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0xa4b8  ret
```
