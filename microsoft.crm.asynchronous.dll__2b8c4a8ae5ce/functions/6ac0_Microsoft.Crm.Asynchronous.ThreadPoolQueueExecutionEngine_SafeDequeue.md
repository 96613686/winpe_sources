# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::SafeDequeue

- ea: `0x6ac0`
- end: `0x6b6c`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::SafeDequeue`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x6a60`

## callees

- `0x6ac0`
- `0x6b70`
- `0x10900`
- `0x11420`

## pseudocode

```c

```

## disassembly

```asm
0x6ac0  ldnull
0x6ac1  stloc.0
0x6ac2  ldarg.0
0x6ac3  ldflda   int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_dequeueThreadsCount
0x6ac8  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x6acd  pop
0x6ace  ldc.i4.s 0xA
0x6ad0  stloc.1
0x6ad1  ldarg.0
0x6ad2  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueReadWriteLock
0x6ad7  ldloc.1
0x6ad8  callvirt instance bool [System.Core]System.Threading.ReaderWriterLockSlim::TryEnterReadLock(int32)
0x6add  ldarg.0
0x6ade  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueReadWriteLock
0x6ae3  callvirt instance bool [System.Core]System.Threading.ReaderWriterLockSlim::get_IsReadLockHeld()
0x6ae8  brfalse.s loc_6AF5
0x6aea  ldarg.0
0x6aeb  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueReadWriteLock
0x6af0  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitReadLock()
0x6af5  brfalse.s loc_6B00
0x6af7  ldarg.0
0x6af8  call     instance class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::Dequeue()
0x6afd  stloc.0
0x6afe  br.s     loc_6B5E
0x6b00  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x6b05  ldstr    aDequeueskipped// "DequeueSkippedForDiagnosticMode"
0x6b0a  ldstr    asc_276F8// ""
0x6b0f  ldarg.0
0x6b10  ldfld    string Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueName
0x6b15  ldloca.s 2
0x6b17  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x6b1d  ldloc.2
0x6b1e  ldc.i4.0
0x6b1f  ldc.i4.0
0x6b20  ldc.i4.0
0x6b21  ldc.i4.0
0x6b22  ldc.i4.0
0x6b23  ldc.i4.0
0x6b24  ldc.i4.0
0x6b25  conv.i8
0x6b26  ldstr    aDequeueFromMul// "Dequeue from multi-org queue is skipped"...
0x6b2b  ldc.r8   0.0
0x6b34  ldc.i4.0
0x6b35  ldloca.s 2
0x6b37  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x6b3d  ldloc.2
0x6b3e  ldc.r8   0.0
0x6b47  ldc.r8   0.0
0x6b50  ldc.r8   0.0
0x6b59  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0x6b5e  ldarg.0
0x6b5f  ldflda   int32 Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_dequeueThreadsCount
0x6b64  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x6b69  pop
0x6b6a  ldloc.0
0x6b6b  ret
```
