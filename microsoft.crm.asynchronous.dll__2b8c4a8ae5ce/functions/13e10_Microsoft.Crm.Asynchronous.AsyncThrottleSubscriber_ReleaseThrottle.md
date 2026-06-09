# Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::ReleaseThrottle

- ea: `0x13e10`
- end: `0x13ec7`
- name: `Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::ReleaseThrottle`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x122a0`
- `0x136c0`
- `0x137b0`
- `0x13e10`
- `0x13ed0`
- `0x13ef0`

## string_xrefs

- `0x13e68`: `Attempting to release throttle held by AsyncEvent ID {0} Type {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x13e10  ldarg.0
0x13e11  ldflda   int32 Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_subscriptionStatus
0x13e16  ldc.i4.0
0x13e17  ldc.i4.1
0x13e18  call     int32 [mscorlib]System.Threading.Interlocked::CompareExchange(int32&, int32, int32)
0x13e1d  stloc.0
0x13e1e  ldc.i4.2
0x13e1f  ldloc.0
0x13e20  bne.un   loc_13EC6
0x13e25  ldarg.0
0x13e26  ldfld    class Microsoft.Crm.Asynchronous.IThrottlingScope Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_currentThrottlingScope
0x13e2b  ldnull
0x13e2c  cgt.un
0x13e2e  ldstr    aTheCurrentThro// "The current throttling-scope is not set"...
0x13e33  ldc.i4.1
0x13e34  newarr   [mscorlib]System.Object
0x13e39  dup
0x13e3a  ldc.i4.0
0x13e3b  ldarg.0
0x13e3c  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13e41  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13e46  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x13e4b  box      [mscorlib]System.Int32
0x13e50  stelem.ref
0x13e51  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x13e56  ldarg.0
0x13e57  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13e5c  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13e61  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x13e66  ldc.i4.s 0x15
0x13e68  ldstr    aAttemptingToRe// "Attempting to release throttle held by "...
0x13e6d  ldc.i4.2
0x13e6e  newarr   [mscorlib]System.Object
0x13e73  dup
0x13e74  ldc.i4.0
0x13e75  ldarg.0
0x13e76  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13e7b  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13e80  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x13e85  box      [mscorlib]System.Guid
0x13e8a  stelem.ref
0x13e8b  dup
0x13e8c  ldc.i4.1
0x13e8d  ldarg.0
0x13e8e  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13e93  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13e98  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x13e9d  box      [mscorlib]System.Int32
0x13ea2  stelem.ref
0x13ea3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13ea8  call     class Microsoft.Crm.Asynchronous.AsyncExecutionThrottler Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::get_Instance()
0x13ead  ldarg.0
0x13eae  ldfld    class Microsoft.Crm.Asynchronous.IThrottlingScope Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_currentThrottlingScope
0x13eb3  ldarg.0
0x13eb4  callvirt instance void Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::ReleaseThrottle(class Microsoft.Crm.Asynchronous.IThrottlingScope throttlingScope, class Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber subscriber)
0x13eb9  ldarg.0
0x13eba  ldc.i4.0
0x13ebb  call     instance void Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::set_Status(valuetype Microsoft.Crm.Asynchronous.AsyncThrottleSubscriptionStatus value)
0x13ec0  ldarg.0
0x13ec1  callvirt instance void Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::UpdateAsyncEventStatistics()
0x13ec6  ret
```
