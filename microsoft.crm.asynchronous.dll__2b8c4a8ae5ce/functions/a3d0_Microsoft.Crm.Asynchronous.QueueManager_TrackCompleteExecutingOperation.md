# Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteExecutingOperation

- ea: `0xa3d0`
- end: `0xa453`
- name: `Microsoft.Crm.Asynchronous.QueueManager::TrackCompleteExecutingOperation`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x8a70`

## callees

- `0x27d0`
- `0x27e0`
- `0xa240`
- `0xa3d0`
- `0x12060`
- `0x121e0`
- `0x121f0`
- `0x122a0`
- `0x12310`

## pseudocode

```c

```

## disassembly

```asm
0xa3d0  ldarg.0
0xa3d1  ldarg.1
0xa3d2  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_CurrentExecutionTime()
0xa3d7  stloc.0
0xa3d8  ldloca.s 0
0xa3da  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xa3df  conv.i4
0xa3e0  ldarg.1
0xa3e1  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa3e6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0xa3eb  call     instance void Microsoft.Crm.Asynchronous.QueueManager::HandleCompletedJobStatistics(int32 elapsedTime, valuetype [mscorlib]System.Guid organizationId)
0xa3f0  ldarg.0
0xa3f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_executingOperations
0xa3f6  stloc.1
0xa3f7  ldc.i4.0
0xa3f8  stloc.2
0xa3f9  ldloc.1
0xa3fa  ldloca.s 2
0xa3fc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa401  ldarg.0
0xa402  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_executingOperations
0xa407  ldarg.1
0xa408  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>::Remove(var<u1>)
0xa40d  brfalse.s loc_A425
0xa40f  ldarg.0
0xa410  ldfld    class Microsoft.Crm.Asynchronous.IQueuePerformanceCounters Microsoft.Crm.Asynchronous.QueueManager::_counters
0xa415  ldarg.1
0xa416  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa41b  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xa420  callvirt instance void Microsoft.Crm.Asynchronous.IQueuePerformanceCounters::TrackCompleteExecutingOperation(int32 operationType)
0xa425  ldarg.0
0xa426  call     instance bool Microsoft.Crm.Asynchronous.AsyncManagerBase::get_ShuttingDown()
0xa42b  brfalse.s loc_A446
0xa42d  ldarg.0
0xa42e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_executingOperations
0xa433  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>::get_Count()
0xa438  brtrue.s loc_A446
0xa43a  ldarg.0
0xa43b  call     instance class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Asynchronous.AsyncManagerBase::get_ShutdownEvent()
0xa440  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xa445  pop
0xa446  leave.s  loc_A452
0xa448  ldloc.2
0xa449  brfalse.s loc_A451
0xa44b  ldloc.1
0xa44c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa451  endfinally
0xa452  ret
```
