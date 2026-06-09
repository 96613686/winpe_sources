# Microsoft.Crm.Asynchronous.QueueManager::OnSemaphoreDiagnosticTimerEvent

- ea: `0xa9d0`
- end: `0xac54`
- name: `Microsoft.Crm.Asynchronous.QueueManager::OnSemaphoreDiagnosticTimerEvent`
- size: `644`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0xb430`

## callees

- `0x2730`
- `0x6cd0`
- `0x6cf0`
- `0xa9d0`
- `0xac60`
- `0xacc0`
- `0xacd0`
- `0xad30`
- `0xae90`
- `0xaf50`
- `0xb1a0`
- `0xb280`
- `0xd0f0`
- `0xd110`
- `0x10900`
- `0x11420`

## string_xrefs

- `0xaa6e`: `DiagnosticModeFailedToAcquireReadWriteLock`
- `0xaa90`: `Diagnostic mode failed to acquire multi-org queue write lock. Max wait time(in minutes) to acquire read-write lock : `
- `0xab60`: `UnexpectedExceptionDuringDiagnostic`

## pseudocode

```c

```

## disassembly

```asm
0xa9d0  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0xa9d5  stloc.0
0xa9d6  ldarg.0
0xa9d7  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32> Microsoft.Crm.Asynchronous.QueueManager::GetOrgMaxParallelSettings()
0xa9dc  stloc.1
0xa9dd  ldloc.0
0xa9de  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xa9e3  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xa9e8  ldstr    aSemaphorediagn_0// "SemaphoreDiagnosticModeStarted"
0xa9ed  ldstr    asc_276F8// ""
0xa9f2  ldarg.0
0xa9f3  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xa9f8  ldloca.s 4
0xa9fa  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xaa00  ldloc.s  4
0xaa02  ldc.i4.0
0xaa03  ldc.i4.0
0xaa04  ldc.i4.0
0xaa05  ldc.i4.0
0xaa06  ldc.i4.0
0xaa07  ldc.i4.0
0xaa08  ldc.i4.0
0xaa09  conv.i8
0xaa0a  ldstr    asc_276F8// ""
0xaa0f  ldc.r8   0.0
0xaa18  ldc.i4.0
0xaa19  ldloca.s 4
0xaa1b  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xaa21  ldloc.s  4
0xaa23  ldc.r8   0.0
0xaa2c  ldc.r8   0.0
0xaa35  ldc.r8   0.0
0xaa3e  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xaa43  ldstr    aAsyncsemaphore_1// "AsyncSemaphoreDiagnosticWaitTimeInSecon"...
0xaa48  ldc.i4.2
0xaa49  call     int32 Microsoft.Crm.Asynchronous.ServerConfiguration::GetRegkeyValueInMilliSecFromSeconds(string keyName, int32 defaultValue)
0xaa4e  stloc.2
0xaa4f  ldstr    aAsyncsemaphore_2// "AsyncSemaphoreLockAcquireWaitTimeInMinu"...
0xaa54  ldc.i4.5
0xaa55  call     int32 Microsoft.Crm.Asynchronous.ServerConfiguration::GetRegkeyValueInMilliSecFromMinutes(string keyName, int32 defaultValue)
0xaa5a  stloc.3
0xaa5b  ldarg.0
0xaa5c  ldfld    class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::_executionEngine
0xaa61  ldloc.3
0xaa62  callvirt instance bool Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::TryPauseQueueOperations(int32 timeout)
0xaa67  brtrue.s loc_AAD9
0xaa69  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xaa6e  ldstr    aDiagnosticmode// "DiagnosticModeFailedToAcquireReadWriteL"...
0xaa73  ldstr    asc_276F8// ""
0xaa78  ldarg.0
0xaa79  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xaa7e  ldloca.s 4
0xaa80  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xaa86  ldloc.s  4
0xaa88  ldc.i4.0
0xaa89  ldc.i4.0
0xaa8a  ldc.i4.0
0xaa8b  ldc.i4.0
0xaa8c  ldc.i4.0
0xaa8d  ldc.i4.0
0xaa8e  ldc.i4.0
0xaa8f  conv.i8
0xaa90  ldstr    aDiagnosticMode// "Diagnostic mode failed to acquire multi"...
0xaa95  ldloc.3
0xaa96  box      [mscorlib]System.Int32
0xaa9b  call     string [mscorlib]System.String::Concat(object, object)
0xaaa0  ldc.r8   0.0
0xaaa9  ldc.i4.0
0xaaaa  ldloca.s 4
0xaaac  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xaab2  ldloc.s  4
0xaab4  ldc.r8   0.0
0xaabd  ldc.r8   0.0
0xaac6  ldc.r8   0.0
0xaacf  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xaad4  leave    loc_AC53
0xaad9  ldloc.2
0xaada  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xaadf  ldarg.0
0xaae0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_executingOperations
0xaae5  stloc.s  5
0xaae7  ldc.i4.0
0xaae8  stloc.s  6
0xaaea  ldloc.s  5
0xaaec  ldloca.s 6
0xaaee  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xaaf3  ldarg.0
0xaaf4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_outstandingOperations
0xaaf9  stloc.s  7
0xaafb  ldc.i4.0
0xaafc  stloc.s  8
0xaafe  ldloc.s  7
0xab00  ldloca.s 8
0xab02  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xab07  ldarg.0
0xab08  call     instance void Microsoft.Crm.Asynchronous.QueueManager::DetectLongRunningExecutingJobs()
0xab0d  ldarg.0
0xab0e  call     instance void Microsoft.Crm.Asynchronous.QueueManager::LogOrgWiseAsyncDelay()
0xab13  ldloc.2
0xab14  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xab19  ldarg.0
0xab1a  call     instance void Microsoft.Crm.Asynchronous.QueueManager::DiagnoseThreadCountSemaphore()
0xab1f  ldarg.0
0xab20  call     instance void Microsoft.Crm.Asynchronous.QueueManager::DiagnoseLockedDownOrgSemaphore()
0xab25  ldarg.0
0xab26  ldloc.1
0xab27  call     instance void Microsoft.Crm.Asynchronous.QueueManager::DiagnoseOrgMaxParallelThreadCountSemapohore(class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32> orgMaxParallelSettings)
0xab2c  ldarg.0
0xab2d  call     instance void Microsoft.Crm.Asynchronous.QueueManager::DiagnoseOperationTypeSemaphore()
0xab32  ldarg.0
0xab33  callvirt instance void Microsoft.Crm.Asynchronous.QueueManager::HandleLostEvents()
0xab38  leave.s  loc_AB46
0xab3a  ldloc.s  8
0xab3c  brfalse.s loc_AB45
0xab3e  ldloc.s  7
0xab40  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xab45  endfinally
0xab46  leave.s  loc_AB54
0xab48  ldloc.s  6
0xab4a  brfalse.s loc_AB53
0xab4c  ldloc.s  5
0xab4e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xab53  endfinally
0xab54  leave    loc_AC53
0xab59  stloc.s  9
0xab5b  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xab60  ldstr    aUnexpectedexce// "UnexpectedExceptionDuringDiagnostic"
0xab65  ldstr    asc_276F8// ""
0xab6a  ldarg.0
0xab6b  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xab70  ldloca.s 4
0xab72  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xab78  ldloc.s  4
0xab7a  ldc.i4.0
0xab7b  ldc.i4.0
0xab7c  ldc.i4.0
0xab7d  ldc.i4.0
0xab7e  ldc.i4.0
0xab7f  ldc.i4.0
0xab80  ldc.i4.0
0xab81  conv.i8
0xab82  ldloc.s  9
0xab84  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0xab89  ldc.r8   0.0
0xab92  ldc.i4.0
0xab93  ldloca.s 4
0xab95  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xab9b  ldloc.s  4
0xab9d  ldc.r8   0.0
0xaba6  ldc.r8   0.0
0xabaf  ldc.r8   0.0
0xabb8  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xabbd  leave    loc_AC53
0xabc2  ldarg.0
0xabc3  ldfld    class Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine Microsoft.Crm.Asynchronous.QueueManager::_executionEngine
0xabc8  callvirt instance void Microsoft.Crm.Asynchronous.ThreadPoolQueueExecutionEngine::ResumeQueueOperations()
0xabcd  ldloc.0
0xabce  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0xabd3  ldloc.0
0xabd4  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0xabd9  ldc.i4   0x3E8
0xabde  conv.i8
0xabdf  div
0xabe0  stloc.s  0xA
0xabe2  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xabe7  ldstr    aSemaphorediagn_1// "SemaphoreDiagnosticModeEnded"
0xabec  ldstr    asc_276F8// ""
0xabf1  ldarg.0
0xabf2  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0xabf7  ldloca.s 4
0xabf9  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xabff  ldloc.s  4
0xac01  ldc.i4.0
0xac02  ldc.i4.0
0xac03  ldc.i4.0
0xac04  ldc.i4.0
0xac05  ldc.i4.0
0xac06  ldc.i4.0
0xac07  ldstr    aElapsedTimeInS// "Elapsed Time(in seconds):"
0xac0c  ldloc.s  0xA
0xac0e  box      [mscorlib]System.Int64
0xac13  call     string [mscorlib]System.String::Concat(object, object)
0xac18  stloc.s  0xB
0xac1a  ldloc.s  0xA
0xac1c  ldloc.s  0xB
0xac1e  ldc.r8   0.0
0xac27  ldc.i4.0
0xac28  ldloca.s 4
0xac2a  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xac30  ldloc.s  4
0xac32  ldc.r8   0.0
0xac3b  ldc.r8   0.0
0xac44  ldc.r8   0.0
0xac4d  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xac52  endfinally
0xac53  ret
```
