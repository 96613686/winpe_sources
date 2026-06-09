# Microsoft.Crm.Asynchronous.AsyncService::StartServiceComponents

- ea: `0xe20`
- end: `0xfe0`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StartServiceComponents`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callees

- `0x860`
- `0xc40`
- `0xc50`
- `0xe20`
- `0xfe0`
- `0x1040`
- `0x1120`
- `0x1200`
- `0x13d0`
- `0x1570`
- `0x1650`
- `0x1830`
- `0x1850`
- `0x1860`
- `0x1900`
- `0x1ea0`
- `0x1f50`
- `0x1fc0`

## string_xrefs

- `0xee9`: `Starting AsyncService: {0}`
- `0xf51`: `Started AsyncService: {0}`
- `0xfb4`: `Exception while starting async service: {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe20  newobj   instance void [Autofac]Autofac.ContainerBuilder::.ctor()
0xe25  stloc.0
0xe26  newobj   instance void Microsoft.Crm.Asynchronous.AsyncServiceTransientErrorDetectionStrategy::.ctor()
0xe2b  newobj   instance void Microsoft.Crm.Asynchronous.AsyncServiceConnectionRetryPolicy::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ITransientErrorDetectionStrategy retryStrategy)
0xe30  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::set_RetryPolicy(class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.IConnectionRetryPolicy)
0xe35  ldc.i4.1
0xe36  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCacheConfig::set_LoadMethod(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LoadMethod)
0xe3b  ldarg.0
0xe3c  call     instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0xe41  stloc.1
0xe42  ldloca.s 1
0xe44  constrained. [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext
0xe4a  callvirt instance string [mscorlib]System.Object::ToString()
0xe4f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceProcessSettings::set_Identifier(string)
0xe54  ldarg.0
0xe55  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xe5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmSqlConnectionManagerFactory::set_ApplicationName(string)
0xe5f  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0xe64  ldarg.0
0xe65  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncService::get_AsyncStartStopActivityId()
0xe6a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceProcessSettings::get_Identifier()
0xe6f  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncStart(valuetype [mscorlib]System.Guid, string)
0xe74  ldarg.0
0xe75  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpTraceListener::.ctor()
0xe7a  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpTraceListener Microsoft.Crm.Asynchronous.AsyncService::_miniDumpTraceListener
0xe7f  call     class [System]System.Diagnostics.TraceListenerCollection [System]System.Diagnostics.Trace::get_Listeners()
0xe84  ldarg.0
0xe85  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.MiniDumpTraceListener Microsoft.Crm.Asynchronous.AsyncService::_miniDumpTraceListener
0xe8a  callvirt instance int32 [System]System.Diagnostics.TraceListenerCollection::Add(class [System]System.Diagnostics.TraceListener)
0xe8f  pop
0xe90  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Initialize()
0xe95  ldarg.0
0xe96  call     instance void Microsoft.Crm.Asynchronous.AsyncService::InitializeServiceComponents()
0xe9b  ldarg.0
0xe9c  ldarg.0
0xe9d  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xea2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::CreateEventLog(string serviceName)
0xea7  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::_eventLog
0xeac  ldarg.0
0xead  ldarg.0
0xeae  ldarg.0
0xeaf  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper Microsoft.Crm.Asynchronous.AsyncService::queueStatisticsHelper
0xeb4  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ConfigurationFactory::Create(class Microsoft.Crm.Asynchronous.AsyncService service, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper queueStatisticsHelper)
0xeb9  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.AsyncService::_config
0xebe  ldarg.0
0xebf  ldc.i4.4
0xec0  ldc.i4   0x4000440B
0xec5  conv.i8
0xec6  ldc.i4.2
0xec7  newarr   [mscorlib]System.Object
0xecc  dup
0xecd  ldc.i4.0
0xece  call     string Microsoft.Crm.Asynchronous.AsyncService::get_HostName()
0xed3  stelem.ref
0xed4  dup
0xed5  ldc.i4.1
0xed6  ldarg.0
0xed7  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xedc  stelem.ref
0xedd  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventLogId, object[] parameters)
0xee2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xee7  ldc.i4.s 0x15
0xee9  ldstr    aStartingAsyncs// "Starting AsyncService: {0}"
0xeee  ldc.i4.1
0xeef  newarr   [mscorlib]System.Object
0xef4  dup
0xef5  ldc.i4.0
0xef6  ldarg.0
0xef7  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xefc  stelem.ref
0xefd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf02  ldarg.0
0xf03  ldarg.0
0xf04  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xf09  call     instance void Microsoft.Crm.Asynchronous.AsyncService::CreatePerformanceCounters(string serviceName)
0xf0e  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::StartUnusedCacheRemovalThread()
0xf13  ldarg.0
0xf14  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StartLocatorCacheSync()
0xf19  ldarg.0
0xf1a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration>::.ctor()
0xf1f  call     instance void Microsoft.Crm.Asynchronous.AsyncService::set_OperationCommandTypes(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, valuetype Microsoft.Crm.Asynchronous.AsyncEventHandlerCommandRegistration> value)
0xf24  ldarg.0
0xf25  ldarg.0
0xf26  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup> Microsoft.Crm.Asynchronous.AsyncHandlerFactory::CreateHandlerGroups(class Microsoft.Crm.Asynchronous.AsyncService service)
0xf2b  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup> Microsoft.Crm.Asynchronous.AsyncService::_handlerGroups
0xf30  ldarg.0
0xf31  ldloc.0
0xf32  call     instance void Microsoft.Crm.Asynchronous.AsyncService::InitializeComponents(class [Autofac]Autofac.ContainerBuilder builder)
0xf37  ldarg.0
0xf38  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StartComponents()
0xf3d  ldarg.0
0xf3e  call     instance void Microsoft.Crm.Asynchronous.AsyncService::SetThreadPoolLimits()
0xf43  ldarg.0
0xf44  ldloc.0
0xf45  call     instance void Microsoft.Crm.Asynchronous.AsyncService::EnableOptionalFeatures(class [Autofac]Autofac.ContainerBuilder builder)
0xf4a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xf4f  ldc.i4.s 0x15
0xf51  ldstr    aStartedAsyncse// "Started AsyncService: {0}"
0xf56  ldc.i4.1
0xf57  newarr   [mscorlib]System.Object
0xf5c  dup
0xf5d  ldc.i4.0
0xf5e  ldarg.0
0xf5f  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xf64  stelem.ref
0xf65  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf6a  ldarg.0
0xf6b  ldc.i4.4
0xf6c  ldc.i4   0x40004400
0xf71  conv.i8
0xf72  ldc.i4.1
0xf73  newarr   [mscorlib]System.Object
0xf78  dup
0xf79  ldc.i4.0
0xf7a  call     string Microsoft.Crm.Asynchronous.AsyncService::get_HostName()
0xf7f  stelem.ref
0xf80  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventLogId, object[] parameters)
0xf85  leave.s  loc_FDF
0xf87  stloc.2
0xf88  ldarg.0
0xf89  ldc.i4.1
0xf8a  ldc.i4   0xC0004402
0xf8f  conv.u8
0xf90  ldc.i4.2
0xf91  newarr   [mscorlib]System.Object
0xf96  dup
0xf97  ldc.i4.0
0xf98  call     string Microsoft.Crm.Asynchronous.AsyncService::get_HostName()
0xf9d  stelem.ref
0xf9e  dup
0xf9f  ldc.i4.1
0xfa0  ldloc.2
0xfa1  callvirt instance string [mscorlib]System.Object::ToString()
0xfa6  stelem.ref
0xfa7  call     instance void Microsoft.Crm.Asynchronous.AsyncService::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventLogId, object[] parameters)
0xfac  ldloc.2
0xfad  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xfb2  ldc.i4.s 0x15
0xfb4  ldstr    aExceptionWhile_0// "Exception while starting async service:"...
0xfb9  ldc.i4.2
0xfba  newarr   [mscorlib]System.Object
0xfbf  dup
0xfc0  ldc.i4.0
0xfc1  ldarg.0
0xfc2  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0xfc7  stelem.ref
0xfc8  dup
0xfc9  ldc.i4.1
0xfca  ldloc.2
0xfcb  stelem.ref
0xfcc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfd1  rethrow
0xfd3  ldarg.0
0xfd4  ldfld    class [mscorlib]System.Threading.ManualResetEventSlim Microsoft.Crm.Asynchronous.AsyncService::_startSequenceCompleted
0xfd9  callvirt instance void [mscorlib]System.Threading.ManualResetEventSlim::Set()
0xfde  endfinally
0xfdf  ret
```
