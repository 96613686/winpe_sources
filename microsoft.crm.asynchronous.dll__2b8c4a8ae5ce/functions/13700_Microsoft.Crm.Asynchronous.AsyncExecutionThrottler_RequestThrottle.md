# Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::RequestThrottle

- ea: `0x13700`
- end: `0x137af`
- name: `Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::RequestThrottle`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x13700`
- `0x13c00`

## callees

- `0x10900`
- `0x11590`
- `0x12150`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x122a0`
- `0x122f0`
- `0x13700`
- `0x138c0`
- `0x13f30`
- `0x17ed0`

## string_xrefs

- `0x1373a`: `Async service requested to grant throttle in spite of sss synchronous exectuion.`

## pseudocode

```c

```

## disassembly

```asm
0x13700  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x13705  stloc.0
0x13706  ldloc.0
0x13707  ldarg.1
0x13708  stfld    class Microsoft.Crm.Asynchronous.IThrottlingScope <>c__DisplayClass4_0::throttlingScope
0x1370d  ldarg.2
0x1370e  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x13713  ldarg.2
0x13714  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x13719  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x1371e  callvirt instance bool Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::IsSSSSynchronousEwsEnabled(class Microsoft.Crm.Asynchronous.IAsyncEvent AsyncEvent)
0x13723  brfalse.s loc_1376B
0x13725  call     class Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x1372a  ldarg.2
0x1372b  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x13730  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13735  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x1373a  ldstr    aAsyncServiceRe// "Async service requested to grant thrott"...
0x1373f  ldarg.2
0x13740  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x13745  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x1374a  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x1374f  ldarg.2
0x13750  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_AsyncEventManager()
0x13755  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x1375a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x1375f  ldstr    aSssrequestthro// "SSSRequestThrottle"
0x13764  callvirt instance void Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogAsyncOperationUnhandledException(valuetype [mscorlib]System.Guid organizationId, string stackTrace, int32 operationType, valuetype [mscorlib]System.Guid eventId, string operationName)
0x13769  ldc.i4.1
0x1376a  ret
0x1376b  ldarg.0
0x1376c  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.Crm.Asynchronous.AsyncThrottle> Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::_throttleCollection
0x13771  ldloc.0
0x13772  ldfld    class Microsoft.Crm.Asynchronous.IThrottlingScope <>c__DisplayClass4_0::throttlingScope
0x13777  callvirt instance string Microsoft.Crm.Asynchronous.IThrottlingScope::get_UniqueKey()
0x1377c  ldloc.0
0x1377d  ldftn    instance class Microsoft.Crm.Asynchronous.AsyncThrottle <>c__DisplayClass4_0::<RequestThrottle>b__0(string x)
0x13783  newobj   instance void class [mscorlib]System.Func`2<string, class Microsoft.Crm.Asynchronous.AsyncThrottle>::.ctor(object, native int)
0x13788  callvirt instance var<u1> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class Microsoft.Crm.Asynchronous.AsyncThrottle>::GetOrAdd(void, var<u1>)
0x1378d  ldarg.2
0x1378e  callvirt instance valuetype Microsoft.Crm.Asynchronous.RequestThrottleResult Microsoft.Crm.Asynchronous.AsyncThrottle::Request(class Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber subscriber)
0x13793  stloc.1
0x13794  ldloc.1
0x13795  brfalse.s loc_1379D
0x13797  ldloc.1
0x13798  ldc.i4.1
0x13799  beq.s    loc_1379F
0x1379b  br.s     loc_137A1
0x1379d  ldc.i4.1
0x1379e  ret
0x1379f  ldc.i4.0
0x137a0  ret
0x137a1  ldarg.0
0x137a2  ldloc.0
0x137a3  ldfld    class Microsoft.Crm.Asynchronous.IThrottlingScope <>c__DisplayClass4_0::throttlingScope
0x137a8  ldarg.2
0x137a9  call     instance bool Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::RequestThrottle(class Microsoft.Crm.Asynchronous.IThrottlingScope throttlingScope, class Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber subscriber)
0x137ae  ret
```
