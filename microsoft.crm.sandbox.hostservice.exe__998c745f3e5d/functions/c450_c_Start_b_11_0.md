# <>c::<Start>b__11_0

- ea: `0xc450`
- end: `0xc7e1`
- name: `<>c::<Start>b__11_0`
- size: `913`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x48e0`
- `0x7df0`
- `0x85e0`
- `0xc450`

## string_xrefs

- `0xc669`: `SandboxWorkerManager.Start() is adding {0} background jobs to the _drawbridgeProcessQueue to create drawbridge processes`
- `0xc7cb`: `SandboxWorkerManager.Start() has finished processing the _drawbridgeProcessQueue to create drawbridge processes`

## pseudocode

```c

```

## disassembly

```asm
0xc450  ldsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_started
0xc455  brfalse.s loc_C45D
0xc457  ldsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_started
0xc45c  ret
0xc45d  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xc462  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xc467  ldc.i4.2
0xc468  bne.un.s loc_C48D
0xc46a  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsApiOrAsyncAndSandbox()
0xc46f  brtrue.s loc_C485
0xc471  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox()
0xc476  brtrue.s loc_C485
0xc478  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xc47d  ldc.i4.0
0xc47e  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xc483  br.s     loc_C486
0xc485  ldc.i4.5
0xc486  stsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_countCleanWorkerProcesses
0xc48b  br.s     loc_C499
0xc48d  ldc.i4.0
0xc48e  ldc.i4.1
0xc48f  call     T0x2B000004
0xc494  stsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_countCleanWorkerProcesses
0xc499  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsApiOrAsyncAndSandbox()
0xc49e  brtrue.s loc_C4B5
0xc4a0  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox()
0xc4a5  brtrue.s loc_C4B5
0xc4a7  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xc4ac  ldc.i4.s 0x15
0xc4ae  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xc4b3  br.s     loc_C4B6
0xc4b5  ldc.i4.5
0xc4b6  stsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0xc4bb  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0xc4c0  ldc.i4.1
0xc4c1  ble.s    loc_C518
0xc4c3  newobj   instance void [Microsoft.VisualBasic]Microsoft.VisualBasic.Devices.ComputerInfo::.ctor()
0xc4c8  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::get_HostConfiguration()
0xc4cd  ldc.i4.s 0x16
0xc4cf  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item(valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostProperty)
0xc4d4  conv.r8
0xc4d5  ldc.r8   100.0
0xc4de  div
0xc4df  stloc.s  5
0xc4e1  callvirt instance unsigned int64 [Microsoft.VisualBasic]Microsoft.VisualBasic.Devices.ComputerInfo::get_TotalPhysicalMemory()
0xc4e6  conv.r.un
0xc4e7  conv.r8
0xc4e8  ldloc.s  5
0xc4ea  mul
0xc4eb  ldc.r8   1048576.0
0xc4f4  div
0xc4f5  ldc.r8   100.0
0xc4fe  div
0xc4ff  call     float64 [mscorlib]System.Math::Round(float64)
0xc504  conv.i4
0xc505  stloc.s  6
0xc507  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0xc50c  ldloc.s  6
0xc50e  call     int32 [mscorlib]System.Math::Min(int32, int32)
0xc513  stsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0xc518  ldc.i4.s 0x16
0xc51a  ldc.i4.0
0xc51b  call     T0x2B000001
0xc520  stloc.0
0xc521  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xc526  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xc52b  ldc.i4.1
0xc52c  bne.un.s loc_C537
0xc52e  ldloc.0
0xc52f  ldc.i4.0
0xc530  ble.s    loc_C537
0xc532  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::GrantAccessToCrashFileFolder()
0xc537  ldstr    aConcurrentwork// "ConcurrentWorkerProcessInitializationCo"...
0xc53c  call     int32 [mscorlib]System.Environment::get_ProcessorCount()
0xc541  box      [mscorlib]System.Int32
0xc546  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xc54b  unbox.any [mscorlib]System.Int32
0xc550  stloc.1
0xc551  newobj   instance void [System]System.Diagnostics.Stopwatch::.ctor()
0xc556  stsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanWorkerProcessTimer
0xc55b  ldsfld   class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanWorkerProcessTimer
0xc560  callvirt instance void [System]System.Diagnostics.Stopwatch::Start()
0xc565  ldstr    aSandboxworkers// "SandboxWorkerStartPort"
0xc56a  ldc.i4   0x1F40
0xc56f  box      [mscorlib]System.Int32
0xc574  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xc579  unbox.any [mscorlib]System.Int32
0xc57e  stloc.2
0xc57f  ldstr    aSandboxworkerm_100// "SandboxWorkerMaxNumberOfWP"
0xc584  ldc.i4   0xBB8
0xc589  box      [mscorlib]System.Int32
0xc58e  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0xc593  unbox.any [mscorlib]System.Int32
0xc598  stloc.3
0xc599  ldloc.2
0xc59a  stloc.s  7
0xc59c  br.s     loc_C5B0
0xc59e  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32> Microsoft.Crm.Sandbox.SandboxWorkerManager::_portsQueue
0xc5a3  ldloc.s  7
0xc5a5  callvirt instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<int32>::Enqueue(var<u1>)
0xc5aa  ldloc.s  7
0xc5ac  ldc.i4.1
0xc5ad  add
0xc5ae  stloc.s  7
0xc5b0  ldloc.s  7
0xc5b2  ldloc.2
0xc5b3  ldloc.3
0xc5b4  add
0xc5b5  blt.s    loc_C59E
0xc5b7  ldc.i4.0
0xc5b8  stloc.s  8
0xc5ba  br       loc_C64D
0xc5bf  ldnull
0xc5c0  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerManager::AddWorker(object param)
0xc5c6  newobj   instance void [mscorlib]System.Threading.ParameterizedThreadStart::.ctor(object, native int)
0xc5cb  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ParameterizedThreadStart)
0xc5d0  stloc.s  9
0xc5d2  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Thread> Microsoft.Crm.Sandbox.SandboxWorkerManager::_addWorkerThreads
0xc5d7  ldloc.s  9
0xc5d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Thread>::Add(var<u1>)
0xc5de  ldloc.s  9
0xc5e0  ldstr    aDrawbridgeAddw// "Drawbridge AddWorker: "
0xc5e5  ldloc.s  8
0xc5e7  box      [mscorlib]System.Int32
0xc5ec  call     string [mscorlib]System.String::Concat(object, object)
0xc5f1  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0xc5f6  ldloc.s  9
0xc5f8  ldc.i4.1
0xc5f9  box      [mscorlib]System.Boolean
0xc5fe  callvirt instance void [mscorlib]System.Threading.Thread::Start(object)
0xc603  ldnull
0xc604  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerManager::AddWorker(object param)
0xc60a  newobj   instance void [mscorlib]System.Threading.ParameterizedThreadStart::.ctor(object, native int)
0xc60f  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ParameterizedThreadStart)
0xc614  stloc.s  9
0xc616  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Thread> Microsoft.Crm.Sandbox.SandboxWorkerManager::_addWorkerThreads
0xc61b  ldloc.s  9
0xc61d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Thread>::Add(var<u1>)
0xc622  ldloc.s  9
0xc624  ldstr    aNativeAddworke// "Native AddWorker: "
0xc629  ldloc.s  8
0xc62b  box      [mscorlib]System.Int32
0xc630  call     string [mscorlib]System.String::Concat(object, object)
0xc635  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0xc63a  ldloc.s  9
0xc63c  ldc.i4.0
0xc63d  box      [mscorlib]System.Boolean
0xc642  callvirt instance void [mscorlib]System.Threading.Thread::Start(object)
0xc647  ldloc.s  8
0xc649  ldc.i4.1
0xc64a  add
0xc64b  stloc.s  8
0xc64d  ldloc.s  8
0xc64f  ldloc.1
0xc650  blt      loc_C5BF
0xc655  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xc65a  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xc65f  ldc.i4.2
0xc660  bne.un.s loc_C6E1
0xc662  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc667  ldc.i4.s 0x26
0xc669  ldstr    aSandboxworkerm_101// "SandboxWorkerManager.Start() is adding "...
0xc66e  ldc.i4.1
0xc66f  newarr   [mscorlib]System.Object
0xc674  dup
0xc675  ldc.i4.0
0xc676  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0xc67b  box      [mscorlib]System.Int32
0xc680  stelem.ref
0xc681  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc686  ldc.i4.0
0xc687  stloc.s  0xA
0xc689  br.s     loc_C697
0xc68b  ldc.i4.1
0xc68c  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundCreateNewWorkerProcess(bool useDrawbridgeIsolation)
0xc691  ldloc.s  0xA
0xc693  ldc.i4.1
0xc694  add
0xc695  stloc.s  0xA
0xc697  ldloc.s  0xA
0xc699  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0xc69e  blt.s    loc_C68B
0xc6a0  ldc.i4.0
0xc6a1  stloc.s  0xB
0xc6a3  br.s     loc_C6D8
0xc6a5  ldnull
0xc6a6  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerManager::SequentialGuidListener()
0xc6ac  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0xc6b1  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0xc6b6  dup
0xc6b7  ldstr    aDrawbridgeSequ// "Drawbridge SequentialGuid: "
0xc6bc  ldloc.s  0xB
0xc6be  box      [mscorlib]System.Int32
0xc6c3  call     string [mscorlib]System.String::Concat(object, object)
0xc6c8  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0xc6cd  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0xc6d2  ldloc.s  0xB
0xc6d4  ldc.i4.1
0xc6d5  add
0xc6d6  stloc.s  0xB
0xc6d8  ldloc.s  0xB
0xc6da  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::SequentialGuidListenersCount
0xc6df  blt.s    loc_C6A5
0xc6e1  ldnull
0xc6e2  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundThread()
0xc6e8  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0xc6ed  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0xc6f2  dup
0xc6f3  ldstr    aSandboxworkerm_102// "SandboxWorkerManager"
0xc6f8  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0xc6fd  dup
0xc6fe  ldc.i4.1
0xc6ff  callvirt instance void [mscorlib]System.Threading.Thread::set_Priority(valuetype [mscorlib]System.Threading.ThreadPriority)
0xc704  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0xc709  ldnull
0xc70a  ldftn    void Microsoft.Crm.Sandbox.SandboxWorkerManager::ScanWorkersThread()
0xc710  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0xc715  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0xc71a  dup
0xc71b  ldstr    aWorkerprocessh// "WorkerProcessHealth"
0xc720  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0xc725  dup
0xc726  ldc.i4.1
0xc727  callvirt instance void [mscorlib]System.Threading.Thread::set_Priority(valuetype [mscorlib]System.Threading.ThreadPriority)
0xc72c  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0xc731  ldc.i4.1
0xc732  stsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_started
0xc737  ldc.i4.1
0xc738  stsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_nativeStarted
0xc73d  ldc.i4.0
0xc73e  stloc.s  4
0xc740  br.s     loc_C7BA
0xc742  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_drawbridgeProcessQueue
0xc747  callvirt instance int32 class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::get_Count()
0xc74c  ldc.i4.0
0xc74d  ceq
0xc74f  stloc.s  4
0xc751  ldc.i4   0x3E8
0xc756  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xc75b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc760  ldc.i4.s 0x26
0xc762  ldstr    aSandboxworkerm_103// "SandboxWorkerManager.Start() is process"...
0xc767  ldc.i4.4
0xc768  newarr   [mscorlib]System.Object
0xc76d  dup
0xc76e  ldc.i4.0
0xc76f  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanDrawbridgeProcessQueue
0xc774  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0xc779  box      [mscorlib]System.Int32
0xc77e  stelem.ref
0xc77f  dup
0xc780  ldc.i4.1
0xc781  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0xc786  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0xc78b  box      [mscorlib]System.Int32
0xc790  stelem.ref
0xc791  dup
0xc792  ldc.i4.2
0xc793  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_drawbridgeProcessQueue
0xc798  callvirt instance int32 class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::get_Count()
0xc79d  box      [mscorlib]System.Int32
0xc7a2  stelem.ref
0xc7a3  dup
0xc7a4  ldc.i4.3
0xc7a5  ldsfld   class [System]System.Collections.Concurrent.BlockingCollection`1<bool> Microsoft.Crm.Sandbox.SandboxWorkerManager::_nativeProcessQueue
0xc7aa  callvirt instance int32 class [System]System.Collections.Concurrent.BlockingCollection`1<bool>::get_Count()
0xc7af  box      [mscorlib]System.Int32
0xc7b4  stelem.ref
0xc7b5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc7ba  ldloc.s  4
0xc7bc  brfalse.s loc_C742
0xc7be  ldc.i4.1
0xc7bf  stsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_drawbridgeStarted
0xc7c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc7c9  ldc.i4.s 0x26
0xc7cb  ldstr    aSandboxworkerm_104// "SandboxWorkerManager.Start() has finish"...
0xc7d0  ldc.i4.0
0xc7d1  newarr   [mscorlib]System.Object
0xc7d6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc7db  ldsfld   bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_started
0xc7e0  ret
```
