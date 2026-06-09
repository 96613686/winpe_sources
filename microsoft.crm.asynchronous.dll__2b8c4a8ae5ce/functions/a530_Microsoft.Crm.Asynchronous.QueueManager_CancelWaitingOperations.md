# Microsoft.Crm.Asynchronous.QueueManager::CancelWaitingOperations

- ea: `0xa530`
- end: `0xa63e`
- name: `Microsoft.Crm.Asynchronous.QueueManager::CancelWaitingOperations`
- size: `270`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa530`
- `0x121d0`
- `0x121e0`
- `0x121f0`
- `0x122a0`
- `0x12350`
- `0x123a0`

## string_xrefs

- `0xa5e1`: `Cancelling operation (ID: {0} Type: {1}) because its waiting time has exceeded the AsyncWaitingTimeout configured for the deployment.`

## pseudocode

```c

```

## disassembly

```asm
0xa530  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::.ctor()
0xa535  stloc.0
0xa536  ldarga.s 2
0xa538  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0xa53d  brfalse.s loc_A557
0xa53f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xa544  ldc.i4.s 0x15
0xa546  ldstr    aAbortingCancel// "Aborting cancellation of timed-out oper"...
0xa54b  ldc.i4.0
0xa54c  newarr   [mscorlib]System.Object
0xa551  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa556  ret
0xa557  ldarg.0
0xa558  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object> Microsoft.Crm.Asynchronous.QueueManager::_waitingOperations
0xa55d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>::GetEnumerator()
0xa562  stloc.1
0xa563  br.s     loc_A589
0xa565  ldloc.1
0xa566  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>>::get_Current()
0xa56b  stloc.2
0xa56c  ldloca.s 2
0xa56e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager, object>::get_Key()
0xa573  stloc.3
0xa574  ldloc.3
0xa575  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_WaitingForCompletionTime()
0xa57a  ldarg.1
0xa57b  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xa580  brfalse.s loc_A589
0xa582  ldloc.0
0xa583  ldloc.3
0xa584  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::Add(var<u1>)
0xa589  ldloc.1
0xa58a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa58f  brtrue.s loc_A565
0xa591  leave.s  loc_A59D
0xa593  ldloc.1
0xa594  brfalse.s loc_A59C
0xa596  ldloc.1
0xa597  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa59c  endfinally
0xa59d  ldloc.0
0xa59e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::GetEnumerator()
0xa5a3  stloc.s  4
0xa5a5  br.s     loc_A621
0xa5a7  ldloca.s 4
0xa5a9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::get_Current()
0xa5ae  stloc.s  5
0xa5b0  ldarga.s 2
0xa5b2  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0xa5b7  brfalse.s loc_A5D2
0xa5b9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xa5be  ldc.i4.s 0x15
0xa5c0  ldstr    aAbortingCancel// "Aborting cancellation of timed-out oper"...
0xa5c5  ldc.i4.0
0xa5c6  newarr   [mscorlib]System.Object
0xa5cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa5d0  leave.s  loc_A63D
0xa5d2  ldnull
0xa5d3  ldloc.s  5
0xa5d5  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa5da  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0xa5df  ldc.i4.s 0x15
0xa5e1  ldstr    aCancellingOper// "Cancelling operation (ID: {0} Type: {1}"...
0xa5e6  ldc.i4.2
0xa5e7  newarr   [mscorlib]System.Object
0xa5ec  dup
0xa5ed  ldc.i4.0
0xa5ee  ldloc.s  5
0xa5f0  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa5f5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0xa5fa  box      [mscorlib]System.Guid
0xa5ff  stelem.ref
0xa600  dup
0xa601  ldc.i4.1
0xa602  ldloc.s  5
0xa604  callvirt instance class Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::get_AsyncEvent()
0xa609  callvirt instance int32 Microsoft.Crm.Asynchronous.IAsyncEvent::get_OperationType()
0xa60e  box      [mscorlib]System.Int32
0xa613  stelem.ref
0xa614  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa619  ldloc.s  5
0xa61b  ldc.i4.3
0xa61c  callvirt instance void Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager::ResumeExecution(valuetype Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus newExecutionStatus)
0xa621  ldloca.s 4
0xa623  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>::MoveNext()
0xa628  brtrue   loc_A5A7
0xa62d  leave.s  loc_A63D
0xa62f  ldloca.s 4
0xa631  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.IAsyncEventExecutionManager>
0xa637  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa63c  endfinally
0xa63d  ret
```
