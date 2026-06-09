# Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcessFromQueueInternal

- ea: `0x78c0`
- end: `0x7ad5`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcessFromQueueInternal`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x77f0`

## callees

- `0x5770`
- `0x5780`
- `0x78c0`
- `0x9780`
- `0x9790`
- `0x9de0`

## string_xrefs

- `0x78cc`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] cleanProcessQueue.Count: {1}`
- `0x790f`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] dequeued clean process from clean queue`
- `0x7949`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] found clean process in process pool`
- `0x798b`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] HasExited returned Error {1}`
- `0x79c3`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] process has exited`
- `0x7a0c`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] no good - status is not Ready`
- `0x7a38`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] found ready process from clean process queue`
- `0x7a61`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] clean process not found in process pool: {1}`
- `0x7a96`: `SandboxWorkerManager.GetWorkerProcessFromQueueInternal:Thread[{0:d4}] no clean process on clean queue: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x78c0  ldnull
0x78c1  stloc.0
0x78c2  ldnull
0x78c3  stloc.1
0x78c4  br       loc_7AC4
0x78c9  ldarg.0
0x78ca  ldc.i4.s 0x21
0x78cc  ldstr    aSandboxworkerm_59// "SandboxWorkerManager.GetWorkerProcessFr"...
0x78d1  ldc.i4.2
0x78d2  newarr   [mscorlib]System.Object
0x78d7  dup
0x78d8  ldc.i4.0
0x78d9  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x78de  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x78e3  box      [mscorlib]System.Int32
0x78e8  stelem.ref
0x78e9  dup
0x78ea  ldc.i4.1
0x78eb  ldarg.2
0x78ec  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x78f1  box      [mscorlib]System.Int32
0x78f6  stelem.ref
0x78f7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x78fc  ldarg.2
0x78fd  ldloca.s 1
0x78ff  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::TryDequeue(var<u1>&)
0x7904  brtrue.s loc_790C
0x7906  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor()
0x790b  throw
0x790c  ldarg.0
0x790d  ldc.i4.s 0x21
0x790f  ldstr    aSandboxworkerm_60// "SandboxWorkerManager.GetWorkerProcessFr"...
0x7914  ldc.i4.1
0x7915  newarr   [mscorlib]System.Object
0x791a  dup
0x791b  ldc.i4.0
0x791c  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7921  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7926  box      [mscorlib]System.Int32
0x792b  stelem.ref
0x792c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7931  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x7936  ldloc.1
0x7937  ldloca.s 0
0x7939  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::TryGetValue(var<u1>, !!T0)
0x793e  brtrue.s loc_7946
0x7940  newobj   instance void [mscorlib]System.Collections.Generic.KeyNotFoundException::.ctor()
0x7945  throw
0x7946  ldarg.0
0x7947  ldc.i4.s 0x21
0x7949  ldstr    aSandboxworkerm_61// "SandboxWorkerManager.GetWorkerProcessFr"...
0x794e  ldc.i4.1
0x794f  newarr   [mscorlib]System.Object
0x7954  dup
0x7955  ldc.i4.0
0x7956  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x795b  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7960  box      [mscorlib]System.Int32
0x7965  stelem.ref
0x7966  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x796b  ldloc.0
0x796c  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x7971  callvirt instance void [System]System.Diagnostics.Process::Refresh()
0x7976  ldc.i4.0
0x7977  stloc.2
0x7978  ldloc.0
0x7979  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x797e  callvirt instance bool [System]System.Diagnostics.Process::get_HasExited()
0x7983  stloc.2
0x7984  leave.s  loc_79BD
0x7986  stloc.3
0x7987  ldloc.3
0x7988  ldarg.0
0x7989  ldc.i4.s 0x21
0x798b  ldstr    aSandboxworkerm_62// "SandboxWorkerManager.GetWorkerProcessFr"...
0x7990  ldc.i4.2
0x7991  newarr   [mscorlib]System.Object
0x7996  dup
0x7997  ldc.i4.0
0x7998  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x799d  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x79a2  box      [mscorlib]System.Int32
0x79a7  stelem.ref
0x79a8  dup
0x79a9  ldc.i4.1
0x79aa  ldloc.3
0x79ab  callvirt instance string [mscorlib]System.Object::ToString()
0x79b0  stelem.ref
0x79b1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x79b6  ldnull
0x79b7  stloc.0
0x79b8  leave    loc_7AC4
0x79bd  ldloc.2
0x79be  brfalse.s loc_79F8
0x79c0  ldarg.0
0x79c1  ldc.i4.s 0x21
0x79c3  ldstr    aSandboxworkerm_63// "SandboxWorkerManager.GetWorkerProcessFr"...
0x79c8  ldc.i4.1
0x79c9  newarr   [mscorlib]System.Object
0x79ce  dup
0x79cf  ldc.i4.0
0x79d0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x79d5  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x79da  box      [mscorlib]System.Int32
0x79df  stelem.ref
0x79e0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x79e5  ldloc.0
0x79e6  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x79eb  ldc.i4.4
0x79ec  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus value)
0x79f1  ldloc.0
0x79f2  ldc.i4.5
0x79f3  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::Exit(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExitReason exitReason)
0x79f8  ldloc.0
0x79f9  brfalse.s loc_7A35
0x79fb  ldloc.0
0x79fc  callvirt instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient()
0x7a01  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus()
0x7a06  ldc.i4.3
0x7a07  beq.s    loc_7A35
0x7a09  ldarg.0
0x7a0a  ldc.i4.s 0x21
0x7a0c  ldstr    aSandboxworkerm_64// "SandboxWorkerManager.GetWorkerProcessFr"...
0x7a11  ldc.i4.1
0x7a12  newarr   [mscorlib]System.Object
0x7a17  dup
0x7a18  ldc.i4.0
0x7a19  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7a1e  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7a23  box      [mscorlib]System.Int32
0x7a28  stelem.ref
0x7a29  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7a2e  ldnull
0x7a2f  stloc.0
0x7a30  leave    loc_7AC4
0x7a35  ldarg.0
0x7a36  ldc.i4.s 0x21
0x7a38  ldstr    aSandboxworkerm_65// "SandboxWorkerManager.GetWorkerProcessFr"...
0x7a3d  ldc.i4.1
0x7a3e  newarr   [mscorlib]System.Object
0x7a43  dup
0x7a44  ldc.i4.0
0x7a45  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7a4a  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7a4f  box      [mscorlib]System.Int32
0x7a54  stelem.ref
0x7a55  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7a5a  leave.s  loc_7AD3
0x7a5c  stloc.s  4
0x7a5e  ldarg.0
0x7a5f  ldc.i4.s 0x21
0x7a61  ldstr    aSandboxworkerm_66// "SandboxWorkerManager.GetWorkerProcessFr"...
0x7a66  ldc.i4.2
0x7a67  newarr   [mscorlib]System.Object
0x7a6c  dup
0x7a6d  ldc.i4.0
0x7a6e  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7a73  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7a78  box      [mscorlib]System.Int32
0x7a7d  stelem.ref
0x7a7e  dup
0x7a7f  ldc.i4.1
0x7a80  ldloc.s  4
0x7a82  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7a87  stelem.ref
0x7a88  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7a8d  leave.s  loc_7A8F
0x7a8f  leave.s  loc_7AC4
0x7a91  stloc.s  5
0x7a93  ldarg.0
0x7a94  ldc.i4.s 0x21
0x7a96  ldstr    aSandboxworkerm_67// "SandboxWorkerManager.GetWorkerProcessFr"...
0x7a9b  ldc.i4.2
0x7a9c  newarr   [mscorlib]System.Object
0x7aa1  dup
0x7aa2  ldc.i4.0
0x7aa3  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7aa8  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7aad  box      [mscorlib]System.Int32
0x7ab2  stelem.ref
0x7ab3  dup
0x7ab4  ldc.i4.1
0x7ab5  ldloc.s  5
0x7ab7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x7abc  stelem.ref
0x7abd  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7ac2  leave.s  loc_7AC4
0x7ac4  ldarg.2
0x7ac5  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x7aca  ldc.i4.0
0x7acb  ble.s    loc_7AD3
0x7acd  ldloc.0
0x7ace  brfalse  loc_78C9
0x7ad3  ldloc.0
0x7ad4  ret
```
