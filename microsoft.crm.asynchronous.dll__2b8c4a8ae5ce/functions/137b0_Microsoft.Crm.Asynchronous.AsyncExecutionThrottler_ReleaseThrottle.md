# Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::ReleaseThrottle

- ea: `0x137b0`
- end: `0x13837`
- name: `Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::ReleaseThrottle`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x13e10`

## callees

- `0x10900`
- `0x11590`
- `0x12150`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x122a0`
- `0x122f0`
- `0x137b0`
- `0x13930`
- `0x13f30`

## string_xrefs

- `0x137dd`: `Async service requested to release throttle in spite of sss synchronous exectuion.`

## pseudocode

```c

```

## disassembly

```asm
0x137b0  ldarg.2
0x137b1  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x137b6  ldarg.2
0x137b7  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x137bc  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x137c1  callvirt instance bool Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::IsSSSSynchronousEwsEnabled(class Microsoft.Crm.Asynchronous.IAsyncEvent AsyncEvent)
0x137c6  brfalse.s loc_1380D
0x137c8  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x137cd  ldarg.2
0x137ce  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x137d3  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x137d8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x137dd  ldstr    aAsyncServiceRe_0// "Async service requested to release thro"...
0x137e2  ldarg.2
0x137e3  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x137e8  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x137ed  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x137f2  ldarg.2
0x137f3  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x137f8  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x137fd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x13802  ldstr    aSssreleasethro// "SSSReleaseThrottle"
0x13807  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncOperationUnhandledException(valuetype [mscorlib]System.Guid organizationId, string stackTrace, int32 operationType, valuetype [mscorlib]System.Guid eventId, string operationName)
0x1380c  ret
0x1380d  ldarg.0
0x1380e  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.Crm.Asynchronous.AsyncThrottle> Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::_throttleCollection
0x13813  ldarg.1
0x13814  callvirt instance string Microsoft.Crm.Asynchronous.IThrottlingScope::get_UniqueKey()
0x13819  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.Crm.Asynchronous.AsyncThrottle>::get_Item(void)
0x1381e  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncThrottle::Release()
0x13823  brfalse.s loc_13836
0x13825  ldarg.0
0x13826  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.Crm.Asynchronous.AsyncThrottle> Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::_throttleCollection
0x1382b  ldarg.1
0x1382c  callvirt instance string Microsoft.Crm.Asynchronous.IThrottlingScope::get_UniqueKey()
0x13831  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x13836  ret
```
