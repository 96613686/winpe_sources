# Microsoft.Crm.Sandbox.SandboxWorkerManager::ProcessDeletedWorker

- ea: `0x8620`
- end: `0x8878`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::ProcessDeletedWorker`
- size: `600`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x9de0`
- `0xb250`

## callees

- `0x24c0`
- `0x62f0`
- `0x8620`
- `0x8880`
- `0x9720`
- `0x9730`
- `0x9770`
- `0x9790`
- `0x97a0`
- `0x98f0`

## string_xrefs

- `0x862b`: `SandboxWorkerManager.ProcessDeletedWorkers: no worker process provided`
- `0x864c`: `SandboxWorkerManager.ProcessDeletedWorkers: no worker system process provided`
- `0x8664`: `SandboxWorkerManager.ProcessDeletedWorkers: deleting worker process: {0}`
- `0x86b2`: `SandboxWorkerManager.ProcessDeletedWorker: Attempting to remove worker process from _processPool: {0}`
- `0x8717`: `SandboxWorkerManager.ProcessDeletedWorker: Removed worker process from _processPool: {0}`
- `0x873d`: `SandboxWorkerManager.ProcessDeletedWorker: TryRemove() Could not remove worker process from _processPool. It might have been removed in a different thread: {0}`
- `0x87ad`: `SandboxWorkerManager.ProcessDeletedWorkers: WorkerProcessExit: {0}`
- `0x87f4`: `SandboxWorkerManager.ProcessDeletedWorker: Removing worker process from organizationWorkerList: {0}`
- `0x8830`: `SandboxWorkerManager.ProcessDeletedWorker: The workerId in the _processPool is different than the one we want to remove. Worker To Remove: {0}, Worker In _processPool: {1}`
- `0x885e`: `SandboxWorkerManager.ProcessDeletedWorker: The worker process is not found in the _processPool: {0}. It might be removed already.`

## pseudocode

```c

```

## disassembly

```asm
0x8620  ldarg.0
0x8621  brtrue.s loc_863C
0x8623  ldnull
0x8624  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8629  ldc.i4.s 0x28
0x862b  ldstr    aSandboxworkerm_83// "SandboxWorkerManager.ProcessDeletedWork"...
0x8630  ldc.i4.0
0x8631  newarr   [mscorlib]System.Object
0x8636  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x863b  ret
0x863c  ldarg.0
0x863d  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x8642  brtrue.s loc_865D
0x8644  ldnull
0x8645  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x864a  ldc.i4.s 0x28
0x864c  ldstr    aSandboxworkerm_84// "SandboxWorkerManager.ProcessDeletedWork"...
0x8651  ldc.i4.0
0x8652  newarr   [mscorlib]System.Object
0x8657  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x865c  ret
0x865d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8662  ldc.i4.s 0x28
0x8664  ldstr    aSandboxworkerm_85// "SandboxWorkerManager.ProcessDeletedWork"...
0x8669  ldc.i4.1
0x866a  newarr   [mscorlib]System.Object
0x866f  dup
0x8670  ldc.i4.0
0x8671  ldarg.0
0x8672  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x8677  stelem.ref
0x8678  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x867d  ldarg.0
0x867e  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x8683  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x8688  call     int32 [mscorlib]System.Convert::ToInt32(int32)
0x868d  stloc.0
0x868e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x8693  ldloc.0
0x8694  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::ContainsKey(var<u1>)
0x8699  brfalse.s loc_86A7
0x869b  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]> Microsoft.Crm.Sandbox.SandboxWorkerManager::get_WorkerProcessIterationCounter()
0x86a0  ldloc.0
0x86a1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32[]>::Remove(var<u1>)
0x86a6  pop
0x86a7  ldnull
0x86a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x86ad  ldc.i4.3
0x86ae  ldc.i4.s 0x26
0x86b0  ldc.i4.0
0x86b1  ldc.i4.1
0x86b2  ldstr    aSandboxworkerm_86// "SandboxWorkerManager.ProcessDeletedWork"...
0x86b7  ldc.i4.1
0x86b8  newarr   [mscorlib]System.Object
0x86bd  dup
0x86be  ldc.i4.0
0x86bf  ldarg.0
0x86c0  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x86c5  stelem.ref
0x86c6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x86cb  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x86d0  ldarg.0
0x86d1  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x86d6  ldloca.s 1
0x86d8  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::TryGetValue(var<u1>, !!T0)
0x86dd  brfalse  loc_8825
0x86e2  ldloc.1
0x86e3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x86e8  ldarg.0
0x86e9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerId()
0x86ee  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x86f3  brfalse  loc_8825
0x86f8  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x86fd  ldarg.0
0x86fe  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x8703  ldloca.s 1
0x8705  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::TryRemove(var<u1>, !!T0)
0x870a  brfalse.s loc_8732
0x870c  ldnull
0x870d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8712  ldc.i4.3
0x8713  ldc.i4.s 0x26
0x8715  ldc.i4.0
0x8716  ldc.i4.1
0x8717  ldstr    aSandboxworkerm_87// "SandboxWorkerManager.ProcessDeletedWork"...
0x871c  ldc.i4.1
0x871d  newarr   [mscorlib]System.Object
0x8722  dup
0x8723  ldc.i4.0
0x8724  ldloc.1
0x8725  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x872a  stelem.ref
0x872b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x8730  br.s     loc_8756
0x8732  ldnull
0x8733  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8738  ldc.i4.2
0x8739  ldc.i4.s 0x26
0x873b  ldc.i4.0
0x873c  ldc.i4.1
0x873d  ldstr    aSandboxworkerm_88// "SandboxWorkerManager.ProcessDeletedWork"...
0x8742  ldc.i4.1
0x8743  newarr   [mscorlib]System.Object
0x8748  dup
0x8749  ldc.i4.0
0x874a  ldarg.0
0x874b  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x8750  stelem.ref
0x8751  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x8756  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x875b  ldarg.0
0x875c  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x8761  call     T0x2B00000F
0x8766  brfalse.s loc_8778
0x8768  ldarg.0
0x8769  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x876e  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0x8773  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::RemoveValueFromQueue(class [System]System.Uri value, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> queue)
0x8778  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x877d  ldarg.0
0x877e  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x8783  call     T0x2B00000F
0x8788  brfalse.s loc_879A
0x878a  ldarg.0
0x878b  callvirt instance class [System]System.Uri Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_Uri()
0x8790  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x8795  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::RemoveValueFromQueue(class [System]System.Uri value, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> queue)
0x879a  ldarg.0
0x879b  callvirt instance bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_AssignedToOrganization()
0x87a0  brfalse  loc_8877
0x87a5  ldarg.0
0x87a6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x87ab  ldc.i4.s 0x28
0x87ad  ldstr    aSandboxworkerm_89// "SandboxWorkerManager.ProcessDeletedWork"...
0x87b2  ldc.i4.1
0x87b3  newarr   [mscorlib]System.Object
0x87b8  dup
0x87b9  ldc.i4.0
0x87ba  ldarg.0
0x87bb  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x87c0  stelem.ref
0x87c1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87c6  ldarg.0
0x87c7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x87cc  ldarg.0
0x87cd  ldfld    bool Microsoft.Crm.Sandbox.SandboxWorkerProcess::IsDrawbridgeProcess
0x87d2  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>::.ctor(var<u1>, !!T0)
0x87d7  stloc.2
0x87d8  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList> Microsoft.Crm.Sandbox.SandboxWorkerManager::_organizationMap
0x87dd  ldloc.2
0x87de  ldloca.s 3
0x87e0  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, bool>, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::TryGetValue(var<u1>, !!T0)
0x87e5  pop
0x87e6  ldloc.3
0x87e7  brfalse.s loc_8814
0x87e9  ldnull
0x87ea  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87ef  ldc.i4.3
0x87f0  ldc.i4.s 0x26
0x87f2  ldc.i4.0
0x87f3  ldc.i4.1
0x87f4  ldstr    aSandboxworkerm_90// "SandboxWorkerManager.ProcessDeletedWork"...
0x87f9  ldc.i4.1
0x87fa  newarr   [mscorlib]System.Object
0x87ff  dup
0x8800  ldc.i4.0
0x8801  ldarg.0
0x8802  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x8807  stelem.ref
0x8808  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x880d  ldloc.3
0x880e  ldarg.0
0x880f  callvirt instance void Microsoft.Crm.Sandbox.OrganizationWorkerList::RemoveWorker(class Microsoft.Crm.Sandbox.SandboxWorkerProcess workerProcess)
0x8814  ldarg.0
0x8815  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_OrganizationId()
0x881a  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::GetCounter(valuetype [mscorlib]System.Guid)
0x881f  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::WorkerProcessExit()
0x8824  ret
0x8825  ldloc.1
0x8826  brfalse.s loc_8853
0x8828  ldnull
0x8829  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x882e  ldc.i4.s 0x26
0x8830  ldstr    aSandboxworkerm_91// "SandboxWorkerManager.ProcessDeletedWork"...
0x8835  ldc.i4.2
0x8836  newarr   [mscorlib]System.Object
0x883b  dup
0x883c  ldc.i4.0
0x883d  ldarg.0
0x883e  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x8843  stelem.ref
0x8844  dup
0x8845  ldc.i4.1
0x8846  ldloc.1
0x8847  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x884c  stelem.ref
0x884d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8852  ret
0x8853  ldnull
0x8854  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8859  ldc.i4.3
0x885a  ldc.i4.s 0x26
0x885c  ldc.i4.0
0x885d  ldc.i4.1
0x885e  ldstr    aSandboxworkerm_92// "SandboxWorkerManager.ProcessDeletedWork"...
0x8863  ldc.i4.1
0x8864  newarr   [mscorlib]System.Object
0x8869  dup
0x886a  ldc.i4.0
0x886b  ldarg.0
0x886c  callvirt instance string Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_FullId()
0x8871  stelem.ref
0x8872  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::Trace(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [System]System.Diagnostics.TraceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, bool, string, object[])
0x8877  ret
```
