# Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteThrottledOperation

- ea: `0xa4e0`
- end: `0xa4fd`
- name: `Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteThrottledOperation`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x8040`

## callees

- `0x12090`
- `0x121f0`
- `0x122a0`
- `0x12350`

## pseudocode

```c

```

## disassembly

```asm
0xa4e0  ldarg.0
0xa4e1  ldfld    class Microsoft.Crm.Asynchronous.IQueuePerformanceCounters Microsoft.Crm.Asynchronous.QueueManager::_counters
0xa4e6  ldarg.1
0xa4e7  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa4ec  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xa4f1  ldarg.1
0xa4f2  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_WaitingForCompletionTime()
0xa4f7  callvirt instance void Microsoft.Crm.Asynchronous.IQueuePerformanceCounters::TrackCompleteThrottledOperation(int32 operationType, valuetype [mscorlib]System.TimeSpan elapsedTime)
0xa4fc  ret
```
