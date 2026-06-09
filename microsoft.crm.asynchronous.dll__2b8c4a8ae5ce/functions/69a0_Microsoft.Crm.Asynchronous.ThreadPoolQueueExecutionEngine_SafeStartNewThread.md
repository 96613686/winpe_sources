# Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::SafeStartNewThread

- ea: `0x69a0`
- end: `0x6a39`
- name: `Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::SafeStartNewThread`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x6970`
- `0x9600`

## callees

- `0x69a0`
- `0x6a40`
- `0xd110`
- `0x10900`
- `0x11420`

## string_xrefs

- `0x69d2`: `NewThreadCreationTimeOut`
- `0x69dc`: `New thread creation was blocked for semaphore diagnostic run. Wait time(in minitues): `

## pseudocode

```c

```

## disassembly

```asm
0x69a0  ldstr    aAsyncsemaphore_0// "AsyncSemaphoreDiagnosticMaxExecutionTim"...
0x69a5  ldc.i4.s 0xF
0x69a7  call     int32 Microsoft.Crm.Asynchronous.ServerConfiguration::GetRegkeyValueInMilliSecFromMinutes(string keyName, int32 defaultValue)
0x69ac  stloc.0
0x69ad  ldarg.0
0x69ae  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueReadWriteLock
0x69b3  ldloc.0
0x69b4  callvirt instance bool [System.Core]System.Threading.ReaderWriterLockSlim::TryEnterReadLock(int32)
0x69b9  brfalse.s loc_69CD
0x69bb  ldarg.0
0x69bc  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueReadWriteLock
0x69c1  callvirt instance void [System.Core]System.Threading.ReaderWriterLockSlim::ExitReadLock()
0x69c6  ldarg.0
0x69c7  call     instance void Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::StartNewThread()
0x69cc  ret
0x69cd  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x69d2  ldstr    aNewthreadcreat// "NewThreadCreationTimeOut"
0x69d7  ldstr    asc_276F8// ""
0x69dc  ldstr    aNewThreadCreat// "New thread creation was blocked for sem"...
0x69e1  ldloc.0
0x69e2  box      [mscorlib]System.Int32
0x69e7  call     string [mscorlib]System.String::Concat(object, object)
0x69ec  stloc.1
0x69ed  ldarg.0
0x69ee  ldfld    string Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::_queueName
0x69f3  ldloca.s 2
0x69f5  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x69fb  ldloc.2
0x69fc  ldc.i4.0
0x69fd  ldc.i4.0
0x69fe  ldc.i4.0
0x69ff  ldc.i4.0
0x6a00  ldc.i4.0
0x6a01  ldc.i4.0
0x6a02  ldc.i4.0
0x6a03  conv.i8
0x6a04  ldloc.1
0x6a05  ldc.r8   0.0
0x6a0e  ldc.i4.0
0x6a0f  ldloca.s 2
0x6a11  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x6a17  ldloc.2
0x6a18  ldc.r8   0.0
0x6a21  ldc.r8   0.0
0x6a2a  ldc.r8   0.0
0x6a33  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0x6a38  ret
```
