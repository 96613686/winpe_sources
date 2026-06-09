# Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::UpdateAsyncDelay

- ea: `0xdde0`
- end: `0xe056`
- name: `Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::UpdateAsyncDelay`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe110`

## callees

- `0xdc50`
- `0xdc60`
- `0xdc70`
- `0xdc80`
- `0xdcc0`
- `0xdcd0`
- `0xdce0`
- `0xdcf0`
- `0xdd30`
- `0xdd40`
- `0xdd50`
- `0xdd60`
- `0xdda0`
- `0xddb0`
- `0xddc0`
- `0xdde0`
- `0x10900`
- `0x11420`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x12220`
- `0x12230`
- `0x12250`
- `0x12340`
- `0x12420`
- `0x12440`

## pseudocode

```c

```

## disassembly

```asm
0xdde0  ldarg.1
0xdde1  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.IAsyncEvent::get_ExecutionManager()
0xdde6  callvirt instance float64 Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_CurrentExecutionTimeSeconds()
0xddeb  stloc.0
0xddec  ldloc.0
0xdded  ldc.r8   0.0
0xddf6  bge.un.s loc_DE61
0xddf8  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xddfd  ldstr    aInvaliddelayin// "InvalidDelayInfo"
0xde02  ldstr    asc_276F8// ""
0xde07  ldarg.0
0xde08  call     instance string Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_QueueName()
0xde0d  ldarg.1
0xde0e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0xde13  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xde18  ldc.i4.0
0xde19  ldc.i4.0
0xde1a  ldc.i4.0
0xde1b  ldc.i4.0
0xde1c  ldc.i4.0
0xde1d  ldc.i4.0
0xde1e  ldc.i4.0
0xde1f  conv.i8
0xde20  ldstr    asc_276F8// ""
0xde25  ldc.r8   0.0
0xde2e  ldarg.1
0xde2f  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xde34  ldarg.1
0xde35  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0xde3a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xde3f  ldloc.0
0xde40  ldc.r8   0.0
0xde49  ldc.r8   0.0
0xde52  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xde57  ldc.r8   0.0
0xde60  stloc.0
0xde61  ldarg.0
0xde62  ldarg.0
0xde63  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_TotalExecutionTimeInSeconds()
0xde68  ldloc.0
0xde69  add
0xde6a  call     instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::set_TotalExecutionTimeInSeconds(float64 value)
0xde6f  ldarg.0
0xde70  ldarg.0
0xde71  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_MaxExecutionTimeInSeconds()
0xde76  ldloc.0
0xde77  bgt.s    loc_DE7C
0xde79  ldloc.0
0xde7a  br.s     loc_DE82
0xde7c  ldarg.0
0xde7d  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_MaxExecutionTimeInSeconds()
0xde82  call     instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::set_MaxExecutionTimeInSeconds(float64 value)
0xde87  ldarg.1
0xde88  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEvent::get_PostponeUntil()
0xde8d  stloc.s  4
0xde8f  ldloca.s 4
0xde91  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0xde96  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0xde9b  stloc.s  4
0xde9d  ldloca.s 4
0xde9f  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0xdea4  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xdea9  brfalse.s loc_DEBE
0xdeab  ldarg.1
0xdeac  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEvent::get_PostponeUntil()
0xdeb1  ldarg.1
0xdeb2  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEvent::get_ModifiedOn()
0xdeb7  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdebc  brtrue.s loc_DEC6
0xdebe  ldarg.1
0xdebf  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEvent::get_ModifiedOn()
0xdec4  br.s     loc_DECC
0xdec6  ldarg.1
0xdec7  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEvent::get_PostponeUntil()
0xdecc  stloc.1
0xdecd  ldarg.1
0xdece  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.IAsyncEvent::get_ExecutionManager()
0xded3  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_EnqueueTime()
0xded8  ldloc.1
0xded9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdede  stloc.s  5
0xdee0  ldloca.s 5
0xdee2  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xdee7  stloc.2
0xdee8  ldloc.2
0xdee9  ldc.r8   0.0
0xdef2  bge.un.s loc_DF5D
0xdef4  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xdef9  ldstr    aInvaliddelayin// "InvalidDelayInfo"
0xdefe  ldstr    asc_276F8// ""
0xdf03  ldarg.0
0xdf04  call     instance string Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_QueueName()
0xdf09  ldarg.1
0xdf0a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0xdf0f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xdf14  ldc.i4.0
0xdf15  ldc.i4.0
0xdf16  ldc.i4.0
0xdf17  ldc.i4.0
0xdf18  ldc.i4.0
0xdf19  ldc.i4.0
0xdf1a  ldc.i4.0
0xdf1b  conv.i8
0xdf1c  ldstr    asc_276F8// ""
0xdf21  ldc.r8   0.0
0xdf2a  ldarg.1
0xdf2b  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xdf30  ldarg.1
0xdf31  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0xdf36  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xdf3b  ldc.r8   0.0
0xdf44  ldc.r8   0.0
0xdf4d  ldloc.2
0xdf4e  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xdf53  ldc.r8   0.0
0xdf5c  stloc.2
0xdf5d  ldarg.0
0xdf5e  ldarg.0
0xdf5f  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_MaxDbDelayInSeconds()
0xdf64  ldloc.2
0xdf65  bgt.s    loc_DF6A
0xdf67  ldloc.2
0xdf68  br.s     loc_DF70
0xdf6a  ldarg.0
0xdf6b  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_MaxDbDelayInSeconds()
0xdf70  call     instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::set_MaxDbDelayInSeconds(float64 value)
0xdf75  ldarg.0
0xdf76  ldarg.0
0xdf77  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_TotalDbDelayInSeconds()
0xdf7c  ldloc.2
0xdf7d  add
0xdf7e  call     instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::set_TotalDbDelayInSeconds(float64 value)
0xdf83  ldarg.1
0xdf84  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.IAsyncEvent::get_ExecutionManager()
0xdf89  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_DequeueTime()
0xdf8e  ldarg.1
0xdf8f  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.IAsyncEvent::get_ExecutionManager()
0xdf94  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_EnqueueTime()
0xdf99  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xdf9e  stloc.s  5
0xdfa0  ldloca.s 5
0xdfa2  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0xdfa7  stloc.3
0xdfa8  ldarg.0
0xdfa9  ldarg.0
0xdfaa  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_MaxInMemoryDelayInSeconds()
0xdfaf  ldloc.3
0xdfb0  bgt.s    loc_DFB5
0xdfb2  ldloc.3
0xdfb3  br.s     loc_DFBB
0xdfb5  ldarg.0
0xdfb6  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_MaxInMemoryDelayInSeconds()
0xdfbb  call     instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::set_MaxInMemoryDelayInSeconds(float64 value)
0xdfc0  ldloc.3
0xdfc1  ldc.r8   0.0
0xdfca  bge.un.s loc_E035
0xdfcc  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xdfd1  ldstr    aInvaliddelayin// "InvalidDelayInfo"
0xdfd6  ldstr    asc_276F8// ""
0xdfdb  ldarg.0
0xdfdc  call     instance string Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_QueueName()
0xdfe1  ldarg.1
0xdfe2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0xdfe7  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xdfec  ldc.i4.0
0xdfed  ldc.i4.0
0xdfee  ldc.i4.0
0xdfef  ldc.i4.0
0xdff0  ldc.i4.0
0xdff1  ldc.i4.0
0xdff2  ldc.i4.0
0xdff3  conv.i8
0xdff4  ldstr    asc_276F8// ""
0xdff9  ldc.r8   0.0
0xe002  ldarg.1
0xe003  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xe008  ldarg.1
0xe009  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0xe00e  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0xe013  ldc.r8   0.0
0xe01c  ldloc.3
0xe01d  ldc.r8   0.0
0xe026  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncSemaphoreDiagnosticInfo(string diagnosticInfoName, [opt] string semaphoreName, [opt] string queueName, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] int32 estimatedSemaphoreInUse, [opt] int32 actualSemaphoreInUse, [opt] int32 semaphoreLeak, [opt] int32 releaseCount, [opt] int32 currentSemaphoreCount, [opt] int32 semaphoreMaxCount, [opt] int64 elapsedTimeInSec, [opt] string message, [opt] float64 timeIntervalInMinutes, [opt] int32 operationType, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> eventId, [opt] float64 executionTime, [opt] float64 inMemoryDelay, [opt] float64 dbDelay)
0xe02b  ldc.r8   0.0
0xe034  stloc.3
0xe035  ldarg.0
0xe036  ldarg.0
0xe037  call     instance float64 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_TotalInMemoryDelayInSeconds()
0xe03c  ldloc.3
0xe03d  add
0xe03e  call     instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::set_TotalInMemoryDelayInSeconds(float64 value)
0xe043  ldarg.0
0xe044  call     instance int32 Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::get_EventCount()
0xe049  stloc.s  6
0xe04b  ldarg.0
0xe04c  ldloc.s  6
0xe04e  ldc.i4.1
0xe04f  add
0xe050  call     instance void Microsoft.Crm.Asynchronous.AsyncEventDelayTracker::set_EventCount(int32 value)
0xe055  ret
```
