# Microsoft.Crm.Asynchronous.QueueManager::DiagnoseThreadCountSemaphore

- ea: `0xb280`
- end: `0xb356`
- name: `Microsoft.Crm.Asynchronous.QueueManager::DiagnoseThreadCountSemaphore`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0xa9d0`

## callees

- `0x2730`
- `0x6ca0`
- `0x6d50`
- `0x6d70`
- `0x6dc0`
- `0xb0f0`
- `0xb360`
- `0x10900`
- `0x11420`

## string_xrefs

- `0xb28c`: `QueueThreadCountSemaphore`

## pseudocode

```c

```

## disassembly

```asm
0xb280  ldarg.0
0xb281  ldfld    class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::_executionEngine
0xb286  callvirt instance class [mscorlib]System.Threading.SemaphoreSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_ThreadCountSemaphore()
0xb28b  stloc.0
0xb28c  ldstr    aQueuethreadcou// "QueueThreadCountSemaphore"
0xb291  stloc.1
0xb292  ldarg.0
0xb293  call     instance class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::get_ExecutionEngine()
0xb298  callvirt instance int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_MaximumThreadCount()
0xb29d  stloc.2
0xb29e  ldarg.0
0xb29f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_executingOperations
0xb2a4  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>::get_Count()
0xb2a9  ldarg.0
0xb2aa  ldfld    class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::_executionEngine
0xb2af  callvirt instance int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_DequeueThreadsCount()
0xb2b4  add
0xb2b5  stloc.3
0xb2b6  ldarg.0
0xb2b7  ldfld    class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::_executionEngine
0xb2bc  callvirt instance int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_ThreadsInUse()
0xb2c1  stloc.s  4
0xb2c3  ldarg.0
0xb2c4  ldloc.0
0xb2c5  ldloc.s  4
0xb2c7  ldloc.3
0xb2c8  ldloc.2
0xb2c9  ldloc.1
0xb2ca  ldc.i4.m1
0xb2cb  call     instance bool Microsoft.Crm.Asynchronous.QueueManager::DetectAndMitigateLeak(class [mscorlib]System.Threading.SemaphoreSlim semaphore, int32 expectedValue, int32 actualCount, int32 maxSemaphoreCount, string semaphoreName, [opt] int32 operationType)
0xb2d0  pop
0xb2d1  ldloc.s  4
0xb2d3  ldloc.3
0xb2d4  sub
0xb2d5  stloc.s  5
0xb2d7  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xb2dc  ldstr    aSemaphorestatu// "SemaphoreStatus"
0xb2e1  ldloc.1
0xb2e2  ldarg.0
0xb2e3  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xb2e8  ldloca.s 8
0xb2ea  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xb2f0  ldloc.s  8
0xb2f2  ldloc.0
0xb2f3  callvirt instance int32 [mscorlib]System.Threading.SemaphoreSlim::get_CurrentCount()
0xb2f8  stloc.s  6
0xb2fa  ldloc.2
0xb2fb  stloc.s  7
0xb2fd  ldarg.0
0xb2fe  ldfld    class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::_executionEngine
0xb303  callvirt instance int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::get_ThreadsInUse()
0xb308  ldarg.0
0xb309  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_executingOperations
0xb30e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>::get_Count()
0xb313  ldloc.s  5
0xb315  ldc.i4.0
0xb316  ldloc.s  6
0xb318  ldloc.s  7
0xb31a  ldc.i4.0
0xb31b  conv.i8
0xb31c  ldstr    asc_276F8// ""
0xb321  ldc.r8   0.0
0xb32a  ldc.i4.0
0xb32b  ldloca.s 8
0xb32d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xb333  ldloc.s  8
0xb335  ldc.r8   0.0
0xb33e  ldc.r8   0.0
0xb347  ldc.r8   0.0
0xb350  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xb355  ret
```
