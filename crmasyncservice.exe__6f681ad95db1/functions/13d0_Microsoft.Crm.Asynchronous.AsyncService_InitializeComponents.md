# Microsoft.Crm.Asynchronous.AsyncService::InitializeComponents

- ea: `0x13d0`
- end: `0x14eb`
- name: `Microsoft.Crm.Asynchronous.AsyncService::InitializeComponents`
- size: `283`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`

## callees

- `0xc40`
- `0x13d0`
- `0x14f0`

## string_xrefs

- `0x1467`: `Async service is ready for processing event.`
- `0x14cb`: `Exception while initializing components: {0} - {1}`

## pseudocode

```c

```

## disassembly

```asm
0x13d0  ldarg.0
0x13d1  call     class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandlerFactory::CreateDefault()
0x13d6  stfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.ErrorHandler Microsoft.Crm.Asynchronous.AsyncService::_errorHandler
0x13db  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x13e0  ldc.i4.s 0x15
0x13e2  ldstr    a0// "{0}"
0x13e7  ldc.i4.1
0x13e8  newarr   [mscorlib]System.Object
0x13ed  dup
0x13ee  ldc.i4.0
0x13ef  ldarg.0
0x13f0  ldftn    instance string Microsoft.Crm.Asynchronous.AsyncService::<InitializeComponents>b__38_0()
0x13f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDelayedTracing/DelayedStringConverter::.ctor(object, native int)
0x13fb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDelayedTracing::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDelayedTracing/DelayedStringConverter)
0x1400  stelem.ref
0x1401  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1406  ldarg.0
0x1407  ldarg.1
0x1408  call     instance void Microsoft.Crm.Asynchronous.AsyncService::InitializeAsyncManagerGroup(class [Autofac]Autofac.ContainerBuilder builder)
0x140d  ldarg.0
0x140e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache::get_Instance()
0x1413  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeCache Microsoft.Crm.Asynchronous.AsyncService::_pluginTypeCache
0x1418  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor::get_Instance()
0x141d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Etm.RequestGovernor::Initialize()
0x1422  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Statistics.StatisticsCollector [Microsoft.Crm.Platform.Server]Microsoft.Crm.Statistics.StatisticsCollector::get_Instance()
0x1427  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Statistics.StatisticsCollector::StartStatisticsCollectorThreads()
0x142c  ldarg.0
0x142d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup> Microsoft.Crm.Asynchronous.AsyncService::_handlerGroups
0x1432  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::GetEnumerator()
0x1437  stloc.0
0x1438  br.s     loc_1447
0x143a  ldloca.s 0
0x143c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::get_Current()
0x1441  ldarg.0
0x1442  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup::StartProcessing(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService)
0x1447  ldloca.s 0
0x1449  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::MoveNext()
0x144e  brtrue.s loc_143A
0x1450  leave.s  loc_1460
0x1452  ldloca.s 0
0x1454  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>
0x145a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x145f  endfinally
0x1460  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1465  ldc.i4.s 0x15
0x1467  ldstr    aAsyncServiceIs// "Async service is ready for processing e"...
0x146c  ldc.i4.0
0x146d  newarr   [mscorlib]System.Object
0x1472  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1477  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.DBNotificationsProvider::.ctor()
0x147c  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::StartNotificationsThread(class [Microsoft.Crm.Core]Microsoft.Crm.INotificationsProvider)
0x1481  ldarg.0
0x1482  call     instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x1487  brfalse.s loc_1492
0x1489  ldarg.0
0x148a  call     instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x148f  ldc.i4.3
0x1490  bne.un.s loc_14B1
0x1492  ldtoken  [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WhoAmIRequest
0x1497  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x149c  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x14a1  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x14a6  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x14ab  pop
0x14ac  call     void [Microsoft.Crm.Sandbox.Client]Microsoft.Crm.Sandbox.SandboxHostManager::Initialize()
0x14b1  call     class [Microsoft.Crm.Core]Microsoft.Crm.FeatureControlChecker [Microsoft.Crm.Core]Microsoft.Crm.FeatureControlChecker::get_Current()
0x14b6  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.OrganizationFeatureControlChecks::.ctor()
0x14bb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureControlChecker::AddCheck(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControlCheck)
0x14c0  leave.s  loc_14EA
0x14c2  stloc.1
0x14c3  ldloc.1
0x14c4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x14c9  ldc.i4.s 0x15
0x14cb  ldstr    aExceptionWhile_1// "Exception while initializing components"...
0x14d0  ldc.i4.2
0x14d1  newarr   [mscorlib]System.Object
0x14d6  dup
0x14d7  ldc.i4.0
0x14d8  ldarg.0
0x14d9  call     instance string [System.ServiceProcess]System.ServiceProcess.ServiceBase::get_ServiceName()
0x14de  stelem.ref
0x14df  dup
0x14e0  ldc.i4.1
0x14e1  ldloc.1
0x14e2  stelem.ref
0x14e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14e8  rethrow
0x14ea  ret
```
