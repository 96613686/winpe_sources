# Microsoft.Crm.Sandbox.SandboxWorkerManager::Stop

- ea: `0x7230`
- end: `0x736f`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::Stop`
- size: `319`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x70`

## callees

- `0x7230`
- `0x9790`
- `0x9840`
- `0x98f0`
- `0xb250`
- `0xb7b0`

## string_xrefs

- `0x7286`: `SandboxWorkerManager.Stop: Signaled shutdown thread`

## pseudocode

```c

```

## disassembly

```asm
0x7230  ldc.i4.1
0x7231  volatile.
0x7233  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_shutdown
0x7238  ldsfld   class [mscorlib]System.Threading.AutoResetEvent Microsoft.Crm.Sandbox.SandboxWorkerManager::_autoEventBackgroundThread
0x723d  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x7242  pop
0x7243  ldsfld   class [mscorlib]System.Threading.CancellationTokenSource Microsoft.Crm.Sandbox.SandboxWorkerManager::_cancellationToken
0x7248  callvirt instance void [mscorlib]System.Threading.CancellationTokenSource::Cancel()
0x724d  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Thread> Microsoft.Crm.Sandbox.SandboxWorkerManager::_addWorkerThreads
0x7252  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Thread>::GetEnumerator()
0x7257  stloc.2
0x7258  br.s     loc_7266
0x725a  ldloca.s 2
0x725c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Thread>::get_Current()
0x7261  callvirt instance void [mscorlib]System.Threading.Thread::Join()
0x7266  ldloca.s 2
0x7268  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Thread>::MoveNext()
0x726d  brtrue.s loc_725A
0x726f  leave.s  loc_727F
0x7271  ldloca.s 2
0x7273  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.Thread>
0x7279  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x727e  endfinally
0x727f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7284  ldc.i4.s 0x26
0x7286  ldstr    aSandboxworkerm_43// "SandboxWorkerManager.Stop: Signaled shu"...
0x728b  ldc.i4.0
0x728c  newarr   [mscorlib]System.Object
0x7291  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7296  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x729b  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x72a0  stloc.0
0x72a1  ldc.i4   0xAFC8
0x72a6  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x72ab  ldc.i4.0
0x72ac  stloc.1
0x72ad  ldloc.0
0x72ae  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::GetEnumerator()
0x72b3  stloc.3
0x72b4  br.s     loc_7305
0x72b6  ldloc.3
0x72b7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Current()
0x72bc  stloc.s  4
0x72be  br.s     loc_72CE
0x72c0  ldloc.1
0x72c1  ldc.i4.1
0x72c2  add
0x72c3  stloc.1
0x72c4  ldc.i4   0x3E8
0x72c9  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x72ce  ldloc.s  4
0x72d0  callvirt instance int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount()
0x72d5  ldc.i4.0
0x72d6  ble.s    loc_72DD
0x72d8  ldloc.1
0x72d9  ldc.i4.s 0x78
0x72db  ble.s    loc_72C0
0x72dd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x72e2  ldc.i4.s 0x26
0x72e4  ldstr    aSandboxworkerm_44// "SandboxWorkerManager.Stop: Terminating "...
0x72e9  ldc.i4.1
0x72ea  newarr   [mscorlib]System.Object
0x72ef  dup
0x72f0  ldc.i4.0
0x72f1  ldloc.s  4
0x72f3  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x72f8  stelem.ref
0x72f9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x72fe  ldloc.s  4
0x7300  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateProcess()
0x7305  ldloc.3
0x7306  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x730b  brtrue.s loc_72B6
0x730d  leave.s  loc_7319
0x730f  ldloc.3
0x7310  brfalse.s loc_7318
0x7312  ldloc.3
0x7313  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7318  endfinally
0x7319  ldloc.0
0x731a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::GetEnumerator()
0x731f  stloc.3
0x7320  br.s     loc_732D
0x7322  ldloc.3
0x7323  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Current()
0x7328  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::ForceShutdownIfPending()
0x732d  ldloc.3
0x732e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7333  brtrue.s loc_7322
0x7335  leave.s  loc_7341
0x7337  ldloc.3
0x7338  brfalse.s loc_7340
0x733a  ldloc.3
0x733b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7340  endfinally
0x7341  ldloc.0
0x7342  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::GetEnumerator()
0x7347  stloc.3
0x7348  br.s     loc_735A
0x734a  ldloc.3
0x734b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Current()
0x7350  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x7355  callvirt instance void [System]System.Diagnostics.Process::WaitForExit()
0x735a  ldloc.3
0x735b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7360  brtrue.s loc_734A
0x7362  leave.s  loc_736E
0x7364  ldloc.3
0x7365  brfalse.s loc_736D
0x7367  ldloc.3
0x7368  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x736d  endfinally
0x736e  ret
```
