# Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::RequestThrottle

- ea: `0x13c00`
- end: `0x13e02`
- name: `Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::RequestThrottle`
- size: `514`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x11b90`
- `0x12150`
- `0x12160`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x122a0`
- `0x123c0`
- `0x136c0`
- `0x13700`
- `0x13c00`
- `0x13ed0`
- `0x13ee0`
- `0x13ef0`

## string_xrefs

- `0x13c57`: `Subscriber (Operation Type: {0}), requesting throttle with scope {1}, is already holding a throttle for a different throttling-scope {2}.`
- `0x13ca8`: `AsyncEvent ID {0} Type {1} is already holding a throttle.`

## pseudocode

```c

```

## disassembly

```asm
0x13c00  ldarg.0
0x13c01  call     instance valuetype Microsoft.Crm.Asynchronous.AsyncThrottleSubscriptionStatus Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_Status()
0x13c06  ldc.i4.1
0x13c07  ceq
0x13c09  ldc.i4.0
0x13c0a  ceq
0x13c0c  ldstr    aSubscriberOper// "Subscriber (Operation Type: {0}) is cur"...
0x13c11  ldc.i4.1
0x13c12  newarr   [mscorlib]System.Object
0x13c17  dup
0x13c18  ldc.i4.0
0x13c19  ldarg.0
0x13c1a  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13c1f  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13c24  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x13c29  box      [mscorlib]System.Int32
0x13c2e  stelem.ref
0x13c2f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x13c34  ldarg.0
0x13c35  call     instance valuetype Microsoft.Crm.Asynchronous.AsyncThrottleSubscriptionStatus Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_Status()
0x13c3a  ldc.i4.2
0x13c3b  bne.un   loc_13CEA
0x13c40  ldarg.1
0x13c41  callvirt instance string Microsoft.Crm.Asynchronous.IThrottlingScope::get_UniqueKey()
0x13c46  ldarg.0
0x13c47  ldfld    class Microsoft.Crm.Asynchronous.IThrottlingScope Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_currentThrottlingScope
0x13c4c  callvirt instance string Microsoft.Crm.Asynchronous.IThrottlingScope::get_UniqueKey()
0x13c51  ldc.i4.4
0x13c52  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x13c57  ldstr    aSubscriberOper_0// "Subscriber (Operation Type: {0}), reque"...
0x13c5c  ldc.i4.3
0x13c5d  newarr   [mscorlib]System.Object
0x13c62  dup
0x13c63  ldc.i4.0
0x13c64  ldarg.0
0x13c65  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13c6a  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13c6f  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x13c74  box      [mscorlib]System.Int32
0x13c79  stelem.ref
0x13c7a  dup
0x13c7b  ldc.i4.1
0x13c7c  ldarg.1
0x13c7d  callvirt instance string Microsoft.Crm.Asynchronous.IThrottlingScope::get_UniqueKey()
0x13c82  stelem.ref
0x13c83  dup
0x13c84  ldc.i4.2
0x13c85  ldarg.0
0x13c86  ldfld    class Microsoft.Crm.Asynchronous.IThrottlingScope Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_currentThrottlingScope
0x13c8b  callvirt instance string Microsoft.Crm.Asynchronous.IThrottlingScope::get_UniqueKey()
0x13c90  stelem.ref
0x13c91  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x13c96  ldarg.0
0x13c97  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13c9c  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13ca1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x13ca6  ldc.i4.s 0x15
0x13ca8  ldstr    aAsynceventId0T_2// "AsyncEvent ID {0} Type {1} is already h"...
0x13cad  ldc.i4.2
0x13cae  newarr   [mscorlib]System.Object
0x13cb3  dup
0x13cb4  ldc.i4.0
0x13cb5  ldarg.0
0x13cb6  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13cbb  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13cc0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x13cc5  box      [mscorlib]System.Guid
0x13cca  stelem.ref
0x13ccb  dup
0x13ccc  ldc.i4.1
0x13ccd  ldarg.0
0x13cce  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13cd3  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13cd8  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x13cdd  box      [mscorlib]System.Int32
0x13ce2  stelem.ref
0x13ce3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13ce8  ldc.i4.1
0x13ce9  ret
0x13cea  ldarg.0
0x13ceb  ldarg.1
0x13cec  stfld    class Microsoft.Crm.Asynchronous.IThrottlingScope Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_currentThrottlingScope
0x13cf1  ldarg.1
0x13cf2  callvirt instance bool Microsoft.Crm.Asynchronous.IThrottlingScope::get_IsThrottled()
0x13cf7  brtrue.s loc_13D60
0x13cf9  ldarg.0
0x13cfa  call     instance valuetype Microsoft.Crm.Asynchronous.AsyncThrottleSubscriptionStatus Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::get_Status()
0x13cff  ldc.i4.0
0x13d00  ceq
0x13d02  ldstr    aAsyncthrottles// "AsyncThrottleSubscriptionStatus should "...
0x13d07  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x13d0c  ldarg.0
0x13d0d  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13d12  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13d17  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x13d1c  ldc.i4.s 0x15
0x13d1e  ldstr    aAsynceventId0T_3// "AsyncEvent ID {0} Type {1} does not req"...
0x13d23  ldc.i4.2
0x13d24  newarr   [mscorlib]System.Object
0x13d29  dup
0x13d2a  ldc.i4.0
0x13d2b  ldarg.0
0x13d2c  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13d31  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13d36  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x13d3b  box      [mscorlib]System.Guid
0x13d40  stelem.ref
0x13d41  dup
0x13d42  ldc.i4.1
0x13d43  ldarg.0
0x13d44  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13d49  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13d4e  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x13d53  box      [mscorlib]System.Int32
0x13d58  stelem.ref
0x13d59  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13d5e  ldc.i4.1
0x13d5f  ret
0x13d60  call     class Microsoft.Crm.Asynchronous.AsyncExecutionThrottler Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::get_Instance()
0x13d65  ldarg.1
0x13d66  ldarg.0
0x13d67  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncExecutionThrottler::RequestThrottle(class Microsoft.Crm.Asynchronous.IThrottlingScope throttlingScope, class Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber subscriber)
0x13d6c  brfalse.s loc_13DCF
0x13d6e  ldarg.0
0x13d6f  ldc.i4.2
0x13d70  call     instance void Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::set_Status(valuetype Microsoft.Crm.Asynchronous.AsyncThrottleSubscriptionStatus value)
0x13d75  ldarg.0
0x13d76  callvirt instance void Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::UpdateAsyncEventStatistics()
0x13d7b  ldarg.0
0x13d7c  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13d81  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13d86  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x13d8b  ldc.i4.s 0x15
0x13d8d  ldstr    aThrottleObtain// "Throttle obtained successfully for Asyn"...
0x13d92  ldc.i4.2
0x13d93  newarr   [mscorlib]System.Object
0x13d98  dup
0x13d99  ldc.i4.0
0x13d9a  ldarg.0
0x13d9b  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13da0  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13da5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x13daa  box      [mscorlib]System.Guid
0x13daf  stelem.ref
0x13db0  dup
0x13db1  ldc.i4.1
0x13db2  ldarg.0
0x13db3  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13db8  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0x13dbd  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0x13dc2  box      [mscorlib]System.Int32
0x13dc7  stelem.ref
0x13dc8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x13dcd  ldc.i4.1
0x13dce  ret
0x13dcf  ldarg.0
0x13dd0  ldc.i4.1
0x13dd1  call     instance void Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::set_Status(valuetype Microsoft.Crm.Asynchronous.AsyncThrottleSubscriptionStatus value)
0x13dd6  ldarg.0
0x13dd7  callvirt instance void Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::UpdateAsyncEventStatistics()
0x13ddc  ldarg.0
0x13ddd  ldfld    class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_asyncEventManager
0x13de2  ldarg.0
0x13de3  dup
0x13de4  ldvirtftn instance class Microsoft.Crm.Asynchronous.AsyncHandlerResult Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::ResumeExecution(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x13dea  newobj   instance void Microsoft.Crm.Asynchronous.AsyncEventExecutionHandler::.ctor(object object, native int method)
0x13def  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::set_ExecutionHandler(class Microsoft.Crm.Asynchronous.AsyncEventExecutionHandler value)
0x13df4  ldarg.0
0x13df5  ldfld    class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Asynchronous.AsyncThrottleSubscriber::_throttledEvent
0x13dfa  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x13dff  pop
0x13e00  ldc.i4.0
0x13e01  ret
```
