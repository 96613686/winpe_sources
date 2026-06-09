# Microsoft.Crm.Sandbox.SandboxWorkerManager::AddWorker

- ea: `0x7e30`
- end: `0x803c`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::AddWorker`
- size: `524`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x5980`
- `0x7e30`
- `0x8df0`
- `0x9790`
- `0x98f0`
- `0xa020`
- `0xa0f0`
- `0xb250`

## string_xrefs

- `0x7ea2`: `SandboxWorkerManager.AddWorker: Thread:`
- `0x7eb1`: ` exiting because the cancellation token was issued `
- `0x7ff8`: `SandboxWorkerManager.AddWorker: Stopping AddWorker Thread.`

## pseudocode

```c

```

## disassembly

```asm
0x7e30  ldstr    aSandboxworkerm_70// "SandboxWorkerManager.AddWorker["
0x7e35  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7e3a  callvirt instance string [mscorlib]System.Threading.Thread::get_Name()
0x7e3f  brfalse.s loc_7E4D
0x7e41  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7e46  callvirt instance string [mscorlib]System.Threading.Thread::get_Name()
0x7e4b  br.s     loc_7E52
0x7e4d  ldstr    aNoname// "NoName"
0x7e52  ldstr    asc_17D78// "]"
0x7e57  call     string [mscorlib]System.String::Concat(string, string, string)
0x7e5c  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string)
0x7e61  stloc.0
0x7e62  ldarg.0
0x7e63  unbox.any [mscorlib]System.Boolean
0x7e68  stloc.1
0x7e69  ldloc.1
0x7e6a  brfalse.s loc_7E83
0x7e6c  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_drawbridgeProcessQueue
0x7e71  ldsfld   class [mscorlib]System.Threading.CancellationTokenSource Microsoft.Crm.Sandbox.SandboxWorkerManager::_cancellationToken
0x7e76  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x7e7b  callvirt instance var<u1> class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::Take(!!T0)
0x7e80  pop
0x7e81  br.s     loc_7E98
0x7e83  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_nativeProcessQueue
0x7e88  ldsfld   class [mscorlib]System.Threading.CancellationTokenSource Microsoft.Crm.Sandbox.SandboxWorkerManager::_cancellationToken
0x7e8d  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x7e92  callvirt instance var<u1> class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::Take(!!T0)
0x7e97  pop
0x7e98  leave.s  loc_7ECB
0x7e9a  pop
0x7e9b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7ea0  ldc.i4.s 0x26
0x7ea2  ldstr    aSandboxworkerm_71// "SandboxWorkerManager.AddWorker: Thread:"
0x7ea7  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x7eac  callvirt instance string [mscorlib]System.Threading.Thread::get_Name()
0x7eb1  ldstr    aExitingBecause// " exiting because the cancellation token"...
0x7eb6  call     string [mscorlib]System.String::Concat(string, string, string)
0x7ebb  ldc.i4.0
0x7ebc  newarr   [mscorlib]System.Object
0x7ec1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7ec6  leave    loc_800D
0x7ecb  nop
0x7ecc  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> Microsoft.Crm.Sandbox.SandboxWorkerManager::_portsQueue
0x7ed1  ldloca.s 2
0x7ed3  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32>::TryDequeue(var<u1>&)
0x7ed8  brfalse  loc_7F97
0x7edd  ldloc.1
0x7ede  brfalse.s loc_7EEE
0x7ee0  ldloc.2
0x7ee1  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> Microsoft.Crm.Sandbox.SandboxWorkerManager::_portsQueue
0x7ee6  newobj   instance void Microsoft.Crm.Sandbox.SandboxWorkerDrawbridgeProcess::.ctor(int32 port, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> portsQueue)
0x7eeb  stloc.3
0x7eec  br.s     loc_7EFA
0x7eee  ldloc.2
0x7eef  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> Microsoft.Crm.Sandbox.SandboxWorkerManager::_portsQueue
0x7ef4  newobj   instance void Microsoft.Crm.Sandbox.SandboxWorkerNativeProcess::.ctor(int32 port, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> portsQueue)
0x7ef9  stloc.3
0x7efa  ldloc.3
0x7efb  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::CreateWorkerProcess()
0x7f00  ldloc.3
0x7f01  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x7f06  brtrue.s loc_7F2B
0x7f08  ldnull
0x7f09  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f0e  ldc.i4.s 0x26
0x7f10  ldstr    aSandboxworkerm_72// "SandboxWorkerManager.AddWorker: Could n"...
0x7f15  ldc.i4.0
0x7f16  newarr   [mscorlib]System.Object
0x7f1b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7f20  ldloc.3
0x7f21  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateProcess()
0x7f26  br       loc_7FAF
0x7f2b  ldloc.3
0x7f2c  callvirt instance bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::InitializeWorkerClient()
0x7f31  pop
0x7f32  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x7f37  ldloc.3
0x7f38  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x7f3d  ldloc.3
0x7f3e  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::TryAdd(var<u1>, !!T0)
0x7f43  brfalse.s loc_7F77
0x7f45  ldloc.1
0x7f46  brtrue.s loc_7F4F
0x7f48  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x7f4d  br.s     loc_7F54
0x7f4f  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x7f54  ldloc.3
0x7f55  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x7f5a  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::Enqueue(var<u1>)
0x7f5f  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [mscorlib]System.Threading.AutoResetEvent> Microsoft.Crm.Sandbox.SandboxWorkerManager::_autoEventWorkerAvailable
0x7f64  ldloca.s 4
0x7f66  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [mscorlib]System.Threading.AutoResetEvent>::TryDequeue(var<u1>&)
0x7f6b  brfalse.s loc_7FAF
0x7f6d  ldloc.s  4
0x7f6f  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x7f74  pop
0x7f75  br.s     loc_7FAF
0x7f77  ldloc.3
0x7f78  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerProcess::TerminateProcess()
0x7f7d  ldnull
0x7f7e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f83  ldc.i4.s 0x26
0x7f85  ldstr    aSandboxworkerm_73// "SandboxWorkerManager.AddWorker: Could n"...
0x7f8a  ldc.i4.0
0x7f8b  newarr   [mscorlib]System.Object
0x7f90  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7f95  br.s     loc_7FAF
0x7f97  ldnull
0x7f98  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f9d  ldc.i4.s 0x26
0x7f9f  ldstr    aSandboxworkerm_74// "SandboxWorkerManager.AddWorker: Could n"...
0x7fa4  ldc.i4.0
0x7fa5  newarr   [mscorlib]System.Object
0x7faa  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7faf  leave.s  loc_7FD3
0x7fb1  stloc.s  5
0x7fb3  ldloc.s  5
0x7fb5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7fba  ldc.i4.s 0x26
0x7fbc  ldstr    aSandboxworkerm_75// "SandboxWorkerManager.AddWorker: {0}"
0x7fc1  ldc.i4.1
0x7fc2  newarr   [mscorlib]System.Object
0x7fc7  dup
0x7fc8  ldc.i4.0
0x7fc9  ldloc.s  5
0x7fcb  stelem.ref
0x7fcc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7fd1  rethrow
0x7fd3  leave.s  loc_7FF1
0x7fd5  ldloc.1
0x7fd6  brfalse.s loc_7FE5
0x7fd8  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x7fdd  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x7fe2  pop
0x7fe3  br.s     loc_7FF0
0x7fe5  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x7fea  call     int32 [mscorlib]System.Threading.Interlocked::Decrement(int32&)
0x7fef  pop
0x7ff0  endfinally
0x7ff1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7ff6  ldc.i4.s 0x26
0x7ff8  ldstr    aSandboxworkerm_76// "SandboxWorkerManager.AddWorker: Stoppin"...
0x7ffd  ldc.i4.0
0x7ffe  newarr   [mscorlib]System.Object
0x8003  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8008  br       loc_7E62
0x800d  leave.s  loc_803B
0x800f  stloc.s  6
0x8011  ldloc.s  6
0x8013  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8018  ldc.i4.s 0x26
0x801a  ldstr    aSandboxworkerm_77// "SandboxWorkerManager.AddWorker: EXCEPTI"...
0x801f  ldc.i4.1
0x8020  newarr   [mscorlib]System.Object
0x8025  dup
0x8026  ldc.i4.0
0x8027  ldloc.s  6
0x8029  stelem.ref
0x802a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x802f  rethrow
0x8031  ldloc.0
0x8032  brfalse.s loc_803A
0x8034  ldloc.0
0x8035  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x803a  endfinally
0x803b  ret
```
