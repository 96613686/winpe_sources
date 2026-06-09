# Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcess

- ea: `0x7370`
- end: `0x74ed`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcess`
- size: `381`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4830`
- `0xba70`
- `0xbf70`

## callees

- `0x7370`
- `0x7610`
- `0x7770`

## string_xrefs

- `0x73c0`: `SandboxWorkerManager.GetWorkerProcess:Thread[{0:d4}]: No worker process returned from GetWorkerProcessInternal. UseDrawbridge: {1}. Number of clean Drawbridge process: {2}. Number of Drawbridge Processes to be initialized: {3}. Number of clean Native Process: {4}. Number of Native Process to be initialized: {5}.  Number of attempts: {6}.`
- `0x743b`: `SandboxWorkerManager.GetWorkerProcess:Thread[{0:d4}]: Worker process successfully returned from GetWorkerProcessInternal. UseDrawbridge: {1}. Number of clean Drawbridge process: {2}. Number of Drawbridge Processes to be initialized: {3}. Number of clean Native Process: {4}. Number of Native Process to be initialized: {5}.  Number of attempts: {6}.`

## pseudocode

```c

```

## disassembly

```asm
0x7370  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x7375  stloc.0
0x7376  ldnull
0x7377  stloc.1
0x7378  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x737d  ldc.r8   30.0
0x7386  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x738b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x7390  stloc.2
0x7391  ldarg.2
0x7392  ldc.i4.0
0x7393  stind.i4
0x7394  ldarg.3
0x7395  ldc.i4.0
0x7396  stind.i4
0x7397  ldarg.s  4
0x7399  ldc.i4.0
0x739a  stind.i4
0x739b  ldarg.s  5
0x739d  ldc.i4.0
0x739e  stind.i4
0x739f  ldarg.s  6
0x73a1  ldc.i4.0
0x73a2  stind.i4
0x73a3  ldc.i4.0
0x73a4  stloc.3
0x73a5  br       loc_74AF
0x73aa  ldarg.0
0x73ab  ldarg.1
0x73ac  ldarg.2
0x73ad  ldarg.3
0x73ae  ldarg.s  4
0x73b0  ldarg.s  5
0x73b2  ldarg.s  6
0x73b4  call     class Microsoft.Crm.Sandbox.SandboxWorkerProcess Microsoft.Crm.Sandbox.SandboxWorkerManager::GetWorkerProcessInternal(valuetype [mscorlib]System.Guid organizationId, bool useDrawbridgeIsolation, [out] int32& orgCleanBucketsCount, [out] int32& orgReadyBucketsCount, [out] int32& orgInitializingBucketsCount, [out] int32& orgWaitingInitializingBucketCount, [out] int32& orgInactiveBucketCount)
0x73b9  stloc.1
0x73ba  ldloc.1
0x73bb  brtrue.s loc_7438
0x73bd  ldarg.0
0x73be  ldc.i4.s 0x21
0x73c0  ldstr    aSandboxworkerm_45// "SandboxWorkerManager.GetWorkerProcess:T"...
0x73c5  ldc.i4.7
0x73c6  newarr   [mscorlib]System.Object
0x73cb  dup
0x73cc  ldc.i4.0
0x73cd  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x73d2  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x73d7  box      [mscorlib]System.Int32
0x73dc  stelem.ref
0x73dd  dup
0x73de  ldc.i4.1
0x73df  ldarg.1
0x73e0  box      [mscorlib]System.Boolean
0x73e5  stelem.ref
0x73e6  dup
0x73e7  ldc.i4.2
0x73e8  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x73ed  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x73f2  box      [mscorlib]System.Int32
0x73f7  stelem.ref
0x73f8  dup
0x73f9  ldc.i4.3
0x73fa  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x73ff  box      [mscorlib]System.Int32
0x7404  stelem.ref
0x7405  dup
0x7406  ldc.i4.4
0x7407  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x740c  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x7411  box      [mscorlib]System.Int32
0x7416  stelem.ref
0x7417  dup
0x7418  ldc.i4.5
0x7419  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x741e  box      [mscorlib]System.Int32
0x7423  stelem.ref
0x7424  dup
0x7425  ldc.i4.6
0x7426  ldloc.3
0x7427  box      [mscorlib]System.Int32
0x742c  stelem.ref
0x742d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7432  ldloc.3
0x7433  ldc.i4.1
0x7434  add
0x7435  stloc.3
0x7436  br.s     loc_74AF
0x7438  ldarg.0
0x7439  ldc.i4.s 0x21
0x743b  ldstr    aSandboxworkerm_46// "SandboxWorkerManager.GetWorkerProcess:T"...
0x7440  ldc.i4.7
0x7441  newarr   [mscorlib]System.Object
0x7446  dup
0x7447  ldc.i4.0
0x7448  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x744d  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x7452  box      [mscorlib]System.Int32
0x7457  stelem.ref
0x7458  dup
0x7459  ldc.i4.1
0x745a  ldarg.1
0x745b  box      [mscorlib]System.Boolean
0x7460  stelem.ref
0x7461  dup
0x7462  ldc.i4.2
0x7463  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x7468  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x746d  box      [mscorlib]System.Int32
0x7472  stelem.ref
0x7473  dup
0x7474  ldc.i4.3
0x7475  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x747a  box      [mscorlib]System.Int32
0x747f  stelem.ref
0x7480  dup
0x7481  ldc.i4.4
0x7482  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x7487  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x748c  box      [mscorlib]System.Int32
0x7491  stelem.ref
0x7492  dup
0x7493  ldc.i4.5
0x7494  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x7499  box      [mscorlib]System.Int32
0x749e  stelem.ref
0x749f  dup
0x74a0  ldc.i4.6
0x74a1  ldloc.3
0x74a2  box      [mscorlib]System.Int32
0x74a7  stelem.ref
0x74a8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x74ad  br.s     loc_74BF
0x74af  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x74b4  ldloc.2
0x74b5  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x74ba  brtrue   loc_73AA
0x74bf  ldloc.0
0x74c0  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x74c5  ldloc.0
0x74c6  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x74cb  conv.r8
0x74cc  ldarg.0
0x74cd  ldstr    aSandboxworkerm_47// "SandboxWorkerManager.GetWorkerProcess"
0x74d2  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::LogExecutionTime(float64 elapsedTimeInMSecs, valuetype [mscorlib]System.Guid organizationId, string methodName)
0x74d7  ldloc.1
0x74d8  brtrue.s loc_74EB
0x74da  ldc.i4   0x8004418D
0x74df  ldc.i4.0
0x74e0  newarr   [mscorlib]System.Object
0x74e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x74ea  throw
0x74eb  ldloc.1
0x74ec  ret
```
