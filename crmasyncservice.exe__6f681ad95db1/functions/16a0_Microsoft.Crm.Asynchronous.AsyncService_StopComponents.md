# Microsoft.Crm.Asynchronous.AsyncService::StopComponents

- ea: `0x16a0`
- end: `0x1713`
- name: `Microsoft.Crm.Asynchronous.AsyncService::StopComponents`
- size: `115`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1210`
- `0x12c0`

## callees

- `0xc40`
- `0x16a0`
- `0x1740`
- `0x1780`

## string_xrefs

- `0x16a7`: `Async service is stopping processing of events.`

## pseudocode

```c

```

## disassembly

```asm
0x16a0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x16a5  ldc.i4.s 0x15
0x16a7  ldstr    aAsyncServiceIs_0// "Async service is stopping processing of"...
0x16ac  ldc.i4.0
0x16ad  newarr   [mscorlib]System.Object
0x16b2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16b7  ldarg.0
0x16b8  ldfld    class Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine Microsoft.Crm.Asynchronous.AsyncService::_asyncManagerGroup
0x16bd  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.ServiceOperationExecutionEngine::StopOperation()
0x16c2  ldarg.0
0x16c3  call     instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::get_Context()
0x16c8  ldc.i4.1
0x16c9  bne.un.s loc_16D7
0x16cb  ldarg.0
0x16cc  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StopKeyManager()
0x16d1  ldarg.0
0x16d2  call     instance void Microsoft.Crm.Asynchronous.AsyncService::StopScalegroupMaintenanceJobsMonitor()
0x16d7  ldarg.0
0x16d8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup> Microsoft.Crm.Asynchronous.AsyncService::_handlerGroups
0x16dd  brfalse.s loc_1712
0x16df  ldarg.0
0x16e0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup> Microsoft.Crm.Asynchronous.AsyncService::_handlerGroups
0x16e5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::GetEnumerator()
0x16ea  stloc.0
0x16eb  br.s     loc_16F9
0x16ed  ldloca.s 0
0x16ef  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::get_Current()
0x16f4  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup::StopProcessing()
0x16f9  ldloca.s 0
0x16fb  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>::MoveNext()
0x1700  brtrue.s loc_16ED
0x1702  leave.s  loc_1712
0x1704  ldloca.s 0
0x1706  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncHandlerGroup>
0x170c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1711  endfinally
0x1712  ret
```
