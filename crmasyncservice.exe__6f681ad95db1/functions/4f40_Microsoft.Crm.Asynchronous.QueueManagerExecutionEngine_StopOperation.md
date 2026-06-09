# Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::StopOperation

- ea: `0x4f40`
- end: `0x4fea`
- name: `Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::StopOperation`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x4f40`

## string_xrefs

- `0x4fa3`: `Completed waiting on shutdown events with signal: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x4f40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.WaitHandle>::.ctor()
0x4f45  stloc.0
0x4f46  ldarg.0
0x4f47  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager> Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::_queueManagers
0x4f4c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager>::GetEnumerator()
0x4f51  stloc.2
0x4f52  br.s     loc_4F6D
0x4f54  ldloc.2
0x4f55  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager>::get_Current()
0x4f5a  stloc.3
0x4f5b  ldloc.3
0x4f5c  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager::StopMonitoring()
0x4f61  ldloc.0
0x4f62  ldloc.3
0x4f63  callvirt instance class [mscorlib]System.Threading.AutoResetEvent [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager::get_ShutdownEvent()
0x4f68  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.WaitHandle>::Add(var<u1>)
0x4f6d  ldloc.2
0x4f6e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4f73  brtrue.s loc_4F54
0x4f75  leave.s  loc_4F81
0x4f77  ldloc.2
0x4f78  brfalse.s loc_4F80
0x4f7a  ldloc.2
0x4f7b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f80  endfinally
0x4f81  ldloc.0
0x4f82  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.WaitHandle>::ToArray()
0x4f87  ldc.r8   120.0
0x4f90  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x4f95  ldc.i4.0
0x4f96  call     bool [mscorlib]System.Threading.WaitHandle::WaitAll(class [mscorlib]System.Threading.WaitHandle[], valuetype [mscorlib]System.TimeSpan, bool)
0x4f9b  stloc.1
0x4f9c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x4fa1  ldc.i4.s 0x15
0x4fa3  ldstr    aCompletedWaiti// "Completed waiting on shutdown events wi"...
0x4fa8  ldc.i4.1
0x4fa9  newarr   [mscorlib]System.Object
0x4fae  dup
0x4faf  ldc.i4.0
0x4fb0  ldloc.1
0x4fb1  box      [mscorlib]System.Boolean
0x4fb6  stelem.ref
0x4fb7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4fbc  ldarg.0
0x4fbd  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager> Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::_queueManagers
0x4fc2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager>::GetEnumerator()
0x4fc7  stloc.2
0x4fc8  br.s     loc_4FD5
0x4fca  ldloc.2
0x4fcb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager>::get_Current()
0x4fd0  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncManager::ExecuteFinalShutdownSteps()
0x4fd5  ldloc.2
0x4fd6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4fdb  brtrue.s loc_4FCA
0x4fdd  leave.s  loc_4FE9
0x4fdf  ldloc.2
0x4fe0  brfalse.s loc_4FE8
0x4fe2  ldloc.2
0x4fe3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4fe8  endfinally
0x4fe9  ret
```
