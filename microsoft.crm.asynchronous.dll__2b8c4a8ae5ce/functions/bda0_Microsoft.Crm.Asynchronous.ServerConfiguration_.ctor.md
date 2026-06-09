# Microsoft.Crm.Asynchronous.ServerConfiguration::.ctor

- ea: `0xbda0`
- end: `0xbecc`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::.ctor`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xbda0`
- `0xc120`
- `0xc9d0`
- `0xce20`
- `0xd160`
- `0xd4d0`
- `0x11c40`
- `0x11cb0`
- `0x14d90`
- `0x14f00`

## string_xrefs

- `0xbea1`: `MSCRMAsyncService$maintenance`

## pseudocode

```c

```

## disassembly

```asm
0xbda0  ldarg.0
0xbda1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::.ctor()
0xbda6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xbdab  ldarg.0
0xbdac  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim>::.ctor()
0xbdb1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.ServerConfiguration::_operationTypeThrottle
0xbdb6  ldarg.0
0xbdb7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::.ctor()
0xbdbc  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Asynchronous.ServerConfiguration::_maxOperationTypeThrottle
0xbdc1  ldarg.0
0xbdc2  call     instance void [mscorlib]System.Object::.ctor()
0xbdc7  ldarg.2
0xbdc8  ldstr    aQueuestatistic// "queueStatisticsHelper"
0xbdcd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xbdd2  ldarg.0
0xbdd3  ldarg.1
0xbdd4  call     instance void Microsoft.Crm.Asynchronous.ServerConfiguration::set_OperationsFactory(class Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory value)
0xbdd9  ldarg.0
0xbdda  newobj   instance void Microsoft.Crm.Asynchronous.LegacyOrganizationRetriever::.ctor()
0xbddf  stfld    class Microsoft.Crm.Asynchronous.IOrganizationRetriever Microsoft.Crm.Asynchronous.ServerConfiguration::retriever
0xbde4  ldarg.0
0xbde5  ldarg.3
0xbde6  call     instance void Microsoft.Crm.Asynchronous.ServerConfiguration::InitializeOrganizationList([opt] class Microsoft.Crm.Asynchronous.AsyncDebugContext debugContext)
0xbdeb  ldc.i4.s 0x1A
0xbded  ldarg.0
0xbdee  dup
0xbdef  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbdf5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbdfa  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbdff  ldc.i4.s 0x2B
0xbe01  ldarg.0
0xbe02  dup
0xbe03  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbe09  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbe0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe13  ldc.i4.s 0x2D
0xbe15  ldarg.0
0xbe16  dup
0xbe17  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbe1d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbe22  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe27  ldc.i4.s 0x1B
0xbe29  ldarg.0
0xbe2a  dup
0xbe2b  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbe31  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbe36  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe3b  ldc.i4.s 0x1D
0xbe3d  ldarg.0
0xbe3e  dup
0xbe3f  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbe45  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbe4a  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe4f  ldc.i4.s 0x20
0xbe51  ldarg.0
0xbe52  dup
0xbe53  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbe59  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbe5e  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe63  ldc.i4.s 0x1E
0xbe65  ldarg.0
0xbe66  dup
0xbe67  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbe6d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbe72  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe77  ldc.i4.s 0x45
0xbe79  ldarg.0
0xbe7a  dup
0xbe7b  ldvirtftn instance void Microsoft.Crm.Asynchronous.ServerConfiguration::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbe81  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbe86  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe8b  ldarg.0
0xbe8c  call     instance void Microsoft.Crm.Asynchronous.ServerConfiguration::InitializeOperationThrottleSetting()
0xbe91  ldarg.1
0xbe92  castclass Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory
0xbe97  callvirt instance class Microsoft.Crm.Asynchronous.Operations.IOperationsBasedService Microsoft.Crm.Asynchronous.Operations.ServiceOperationsFactory::get_Service()
0xbe9c  callvirt instance string Microsoft.Crm.Asynchronous.Operations.IOperationsBasedService::get_ServiceName()
0xbea1  ldstr    aMscrmasyncserv// "MSCRMAsyncService$maintenance"
0xbea6  ldc.i4.5
0xbea7  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xbeac  brtrue.s loc_BECB
0xbeae  ldarg.0
0xbeaf  ldarg.2
0xbeb0  newobj   instance void Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer::.ctor(class Microsoft.Crm.Asynchronous.QueueStatisticsHelper queueStatisticsHelper)
0xbeb5  stfld    class Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer Microsoft.Crm.Asynchronous.ServerConfiguration::backlogAnalyzer
0xbeba  ldarg.0
0xbebb  ldfld    class Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer Microsoft.Crm.Asynchronous.ServerConfiguration::backlogAnalyzer
0xbec0  ldarg.0
0xbec1  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::get_AllOrganizationsToMonitor()
0xbec6  callvirt instance void Microsoft.Crm.Asynchronous.AsyncBacklogAnalyzer::Monitor(class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> dictionary)
0xbecb  ret
```
