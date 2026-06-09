# Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::StartInternal

- ea: `0x5dfb0`
- end: `0x5e101`
- name: `Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::StartInternal`
- size: `337`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5dea0`
- `0x5deb0`

## callees

- `0x5db20`
- `0x5dd10`
- `0x5ddf0`
- `0x5de00`
- `0x5df20`
- `0x5dfb0`

## string_xrefs

- `0x5dfc2`: `LocatorCacheSyncManager`
- `0x5e065`: `LocatorCacheSyncManager`
- `0x5dfb5`: `Starting {0} for service {1}, in process {2}, thread {3}`
- `0x5e058`: `{0}: Cache synchronization job started. Wait='{1}'`
- `0x5e0dd`: `Finished initialization of Locator Cache Sync Manager.`

## pseudocode

```c

```

## disassembly

```asm
0x5dfb0  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5dfb5  ldstr    aStarting0ForSe// "Starting {0} for service {1}, in proces"...
0x5dfba  ldc.i4.4
0x5dfbb  newarr   [mscorlib]System.Object
0x5dfc0  dup
0x5dfc1  ldc.i4.0
0x5dfc2  ldstr    aLocatorcachesy_4// "LocatorCacheSyncManager"
0x5dfc7  stelem.ref
0x5dfc8  dup
0x5dfc9  ldc.i4.1
0x5dfca  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x5dfcf  stelem.ref
0x5dfd0  dup
0x5dfd1  ldc.i4.2
0x5dfd2  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ProcessName()
0x5dfd7  stelem.ref
0x5dfd8  dup
0x5dfd9  ldc.i4.3
0x5dfda  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x5dfdf  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x5dfe4  box      [mscorlib]System.Int32
0x5dfe9  stelem.ref
0x5dfea  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5dfef  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x5dff4  stloc.0
0x5dff5  ldloc.0
0x5dff6  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CrmServiceName
0x5dffb  call     string Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::get_ServiceIdentifier()
0x5e000  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5e005  ldloc.0
0x5e006  ldsfld   string Microsoft.Crm.CustomPropertyConstants::CacheSyncManagerState
0x5e00b  ldarg.0
0x5e00c  ldflda   bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_isExecuting
0x5e011  call     instance string [mscorlib]System.Boolean::ToString()
0x5e016  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x5e01b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e020  ldsfld   string Microsoft.Crm.CustomMetricNames::LocatorCacheSyncStart
0x5e025  ldloc.0
0x5e026  ldc.i4.1
0x5e027  conv.i8
0x5e028  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::LogMetric(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string>, int64)
0x5e02d  ldarg.0
0x5e02e  ldfld    bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_isExecuting
0x5e033  brtrue   loc_5E100
0x5e038  ldsfld   object Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::ExecutionLock
0x5e03d  stloc.1
0x5e03e  ldc.i4.0
0x5e03f  stloc.2
0x5e040  ldloc.1
0x5e041  ldloca.s 2
0x5e043  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5e048  ldarg.0
0x5e049  ldfld    bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_isExecuting
0x5e04e  brtrue   loc_5E0F4
0x5e053  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e058  ldstr    a0CacheSynchron_0// "{0}: Cache synchronization job started."...
0x5e05d  ldc.i4.2
0x5e05e  newarr   [mscorlib]System.Object
0x5e063  dup
0x5e064  ldc.i4.0
0x5e065  ldstr    aLocatorcachesy_4// "LocatorCacheSyncManager"
0x5e06a  stelem.ref
0x5e06b  dup
0x5e06c  ldc.i4.1
0x5e06d  ldarg.1
0x5e06e  box      [mscorlib]System.Boolean
0x5e073  stelem.ref
0x5e074  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5e079  ldarg.0
0x5e07a  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_locatorCacheSettingAccessor
0x5e07f  callvirt instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor::get_Settings()
0x5e084  callvirt instance bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings::get_Enabled()
0x5e089  stloc.3
0x5e08a  ldloc.3
0x5e08b  brfalse.s loc_5E0A1
0x5e08d  ldarg.0
0x5e08e  call     instance bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::TryPopulateCacheFromPersistentStore()
0x5e093  brfalse.s loc_5E0A1
0x5e095  ldarg.0
0x5e096  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_writeToCacheEvent
0x5e09b  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x5e0a0  pop
0x5e0a1  ldarg.0
0x5e0a2  newobj   instance void [mscorlib]System.Threading.CancellationTokenSource::.ctor()
0x5e0a7  stfld    class [mscorlib]System.Threading.CancellationTokenSource Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_workerCancellationTokenSource
0x5e0ac  ldarg.0
0x5e0ad  ldftn    instance void Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::<StartInternal>b__23_0(object state)
0x5e0b3  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0x5e0b8  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback)
0x5e0bd  pop
0x5e0be  ldarg.1
0x5e0bf  ldloc.3
0x5e0c0  and
0x5e0c1  brfalse.s loc_5E0ED
0x5e0c3  ldc.i4.1
0x5e0c4  newarr   [mscorlib]System.Threading.WaitHandle
0x5e0c9  dup
0x5e0ca  ldc.i4.0
0x5e0cb  ldarg.0
0x5e0cc  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_writeToCacheEvent
0x5e0d1  stelem.ref
0x5e0d2  call     bool [mscorlib]System.Threading.WaitHandle::WaitAll(class [mscorlib]System.Threading.WaitHandle[])
0x5e0d7  pop
0x5e0d8  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::Logger
0x5e0dd  ldstr    aFinishedInitia// "Finished initialization of Locator Cach"...
0x5e0e2  ldc.i4.0
0x5e0e3  newarr   [mscorlib]System.Object
0x5e0e8  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5e0ed  ldarg.0
0x5e0ee  ldc.i4.1
0x5e0ef  stfld    bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSyncManager::_isExecuting
0x5e0f4  leave.s  loc_5E100
0x5e0f6  ldloc.2
0x5e0f7  brfalse.s loc_5E0FF
0x5e0f9  ldloc.1
0x5e0fa  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5e0ff  endfinally
0x5e100  ret
```
