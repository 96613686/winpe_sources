# Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteOutstandingOperation

- ea: `0xa140`
- end: `0xa1c8`
- name: `Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteOutstandingOperation`
- size: `136`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x8a70`
- `0x9680`
- `0x9b70`

## callees

- `0x2730`
- `0xa140`
- `0xa1d0`
- `0xe110`
- `0x12070`
- `0x121f0`
- `0x122a0`
- `0x12300`
- `0x123f0`
- `0x13050`
- `0x17920`

## pseudocode

```c

```

## disassembly

```asm
0xa140  ldarg.0
0xa141  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_outstandingOperations
0xa146  stloc.0
0xa147  ldc.i4.0
0xa148  stloc.1
0xa149  ldloc.0
0xa14a  ldloca.s 1
0xa14c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa151  ldarg.0
0xa152  ldfld    class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.AsyncEventDelayTracker>> Microsoft.Crm.Asynchronous.QueueManager::_orgWiseDelayTracker
0xa157  ldarg.1
0xa158  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa15d  ldarg.0
0xa15e  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xa163  call     void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::UpdateAsyncDelayByOrgDictionary(class [mscorlib]System.Lazy`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Asynchronous.AsyncEventDelayTracker>> orgWiseDictionary, class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent, string queueName)
0xa168  ldarg.1
0xa169  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventSemaphoreManager Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_SemaphoreManager()
0xa16e  brfalse.s loc_A17B
0xa170  ldarg.1
0xa171  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventSemaphoreManager Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_SemaphoreManager()
0xa176  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncEventSemaphoreManager::ReleaseSemaphores()
0xa17b  ldarg.0
0xa17c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_outstandingOperations
0xa181  ldarg.1
0xa182  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>::Remove(var<u1>)
0xa187  brfalse.s loc_A1BB
0xa189  ldarg.0
0xa18a  ldfld    class Microsoft.Crm.Asynchronous.IQueuePerformanceCounters Microsoft.Crm.Asynchronous.QueueManager::_counters
0xa18f  ldarg.1
0xa190  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa195  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xa19a  ldarg.2
0xa19b  ldarg.1
0xa19c  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_ExecutionTime()
0xa1a1  callvirt instance void Microsoft.Crm.Asynchronous.IQueuePerformanceCounters::TrackCompleteOutstandingOperation(int32 operationType, class Microsoft.Crm.Asynchronous.AsyncHandlerResult result, valuetype [mscorlib]System.TimeSpan elapsedTime)
0xa1a6  ldarg.3
0xa1a7  brfalse.s loc_A1B4
0xa1a9  ldarg.0
0xa1aa  ldfld    class StartThread Microsoft.Crm.Asynchronous.QueueManager::_startThreadHandler
0xa1af  callvirt instance void StartThread::Invoke()
0xa1b4  ldarg.0
0xa1b5  ldarg.1
0xa1b6  callvirt instance void Microsoft.Crm.Asynchronous.QueueManager::OnTrackCompleteOutstandingOperation(class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager asyncEventManager)
0xa1bb  leave.s  loc_A1C7
0xa1bd  ldloc.1
0xa1be  brfalse.s loc_A1C6
0xa1c0  ldloc.0
0xa1c1  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa1c6  endfinally
0xa1c7  ret
```
