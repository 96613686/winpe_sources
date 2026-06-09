# Microsoft.Crm.Asynchronous.AsyncService::.ctor

- ea: `0xb70`
- end: `0xc3c`
- name: `Microsoft.Crm.Asynchronous.AsyncService::.ctor`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd80`

## callees

- `0xb70`

## pseudocode

```c

```

## disassembly

```asm
0xb70  ldarg.0
0xb71  ldc.i4.0
0xb72  newobj   instance void [mscorlib]System.Threading.ManualResetEventSlim::.ctor(bool)
0xb77  stfld    class [mscorlib]System.Threading.ManualResetEventSlim Microsoft.Crm.Asynchronous.AsyncService::_startSequenceCompleted
0xb7c  ldarg.0
0xb7d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0xb82  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncService::_asyncStartStopActivityId
0xb87  ldarg.0
0xb88  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::.ctor()
0xb8d  ldarg.0
0xb8e  ldarg.1
0xb8f  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_ServiceName(string)
0xb94  ldarg.0
0xb95  ldc.i4.0
0xb96  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_AutoLog(bool)
0xb9b  ldarg.0
0xb9c  ldc.i4.1
0xb9d  call     instance void [System.ServiceProcess]System.ServiceProcess.ServiceBase::set_CanPauseAndContinue(bool)
0xba2  ldarg.0
0xba3  ldarg.2
0xba4  stfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0xba9  ldarg.0
0xbaa  ldarg.3
0xbab  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.AsyncService::_debugContext
0xbb0  call     void [Microsoft.Xrm.Kernel.Composition]Microsoft.Xrm.Kernel.Composition.CompositionRoot::Compose()
0xbb5  ldc.i4   0xFC0
0xbba  call     void [System]System.Net.ServicePointManager::set_SecurityProtocol(valuetype [System]System.Net.SecurityProtocolType)
0xbbf  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0xbc4  ldarg.0
0xbc5  ldftn    instance void Microsoft.Crm.Asynchronous.AsyncService::OnUnhandledException(object sender, class [mscorlib]System.UnhandledExceptionEventArgs e)
0xbcb  newobj   instance void [mscorlib]System.UnhandledExceptionEventHandler::.ctor(object, native int)
0xbd0  callvirt instance void [mscorlib]System.AppDomain::add_UnhandledException(class [mscorlib]System.UnhandledExceptionEventHandler)
0xbd5  ldsfld   class [mscorlib]System.EventHandler`1<class [mscorlib]System.Threading.Tasks.UnobservedTaskExceptionEventArgs> <>c::<>9__1_0
0xbda  dup
0xbdb  brtrue.s loc_BF4
0xbdd  pop
0xbde  ldsfld   class <>c <>c::<>9
0xbe3  ldftn    instance void <>c::<.ctor>b__1_0(object sender, class [mscorlib]System.Threading.Tasks.UnobservedTaskExceptionEventArgs eventArgs)
0xbe9  newobj   instance void class [mscorlib]System.EventHandler`1<class [mscorlib]System.Threading.Tasks.UnobservedTaskExceptionEventArgs>::.ctor(object, native int)
0xbee  dup
0xbef  stsfld   class [mscorlib]System.EventHandler`1<class [mscorlib]System.Threading.Tasks.UnobservedTaskExceptionEventArgs> <>c::<>9__1_0
0xbf4  call     void [mscorlib]System.Threading.Tasks.TaskScheduler::add_UnobservedTaskException(class [mscorlib]System.EventHandler`1<class [mscorlib]System.Threading.Tasks.UnobservedTaskExceptionEventArgs>)
0xbf9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ConstantFieldValueToFieldNameMapper::.ctor()
0xbfe  stloc.0
0xbff  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryMetrics::.ctor()
0xc04  stloc.1
0xc05  ldarg.0
0xc06  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryFacade [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.TelemetryFacade::get_Instance()
0xc0b  ldloc.1
0xc0c  ldloc.0
0xc0d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryFacade::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryFacade, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryMetrics, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConstantFieldValueToFieldNameMapper)
0xc12  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade Microsoft.Crm.Asynchronous.AsyncService::telemetryFacade
0xc17  ldarg.0
0xc18  ldarg.0
0xc19  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade Microsoft.Crm.Asynchronous.AsyncService::telemetryFacade
0xc1e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper::.ctor(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade)
0xc23  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.QueueStatisticsHelper Microsoft.Crm.Asynchronous.AsyncService::queueStatisticsHelper
0xc28  ldarg.0
0xc29  ldarg.0
0xc2a  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade Microsoft.Crm.Asynchronous.AsyncService::telemetryFacade
0xc2f  ldc.i4.s 0x3C
0xc31  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePeriodicWorker [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServiceTelemetryFacade::CreateHeartbeatPeriodicWorker(int32)
0xc36  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePeriodicWorker Microsoft.Crm.Asynchronous.AsyncService::heartbeatWorker
0xc3b  ret
```
