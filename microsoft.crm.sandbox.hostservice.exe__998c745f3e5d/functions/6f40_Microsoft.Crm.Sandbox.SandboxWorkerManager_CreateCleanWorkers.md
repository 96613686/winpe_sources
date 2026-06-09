# Microsoft.Crm.Sandbox.SandboxWorkerManager::CreateCleanWorkers

- ea: `0x6f40`
- end: `0x70e4`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::CreateCleanWorkers`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xc9f0`

## callees

- `0x6f40`
- `0x7df0`

## string_xrefs

- `0x6fae`: `SandboxWorkerManager.CreateCleanWorkers: Creating {0} Clean Native Worker Processes in the background. CleanWorkerProcess: {1}, _cleanNativeProcessQueue.Count:{2}, _waitingStartupNativeProcess: {3}`
- `0x703a`: `SandboxWorkerManager.CreateCleanWorkers: Creating {0} Clean Drawbridge Worker Processes in the background. InitialWorkerCount: {1}, _processPool(drawbridge).Count:{2}, _waitingStartupDrawbridgeProcess: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x6f40  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x6f45  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x6f4a  ldc.i4.2
0x6f4b  bne.un.s loc_6F84
0x6f4d  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x6f52  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x6f57  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__20_0
0x6f5c  dup
0x6f5d  brtrue.s loc_6F76
0x6f5f  pop
0x6f60  ldsfld   class <>c <>c::<>9
0x6f65  ldftn    instance bool <>c::<CreateCleanWorkers>b__20_0(class Microsoft.Crm.Sandbox.SandboxWorkerProcess x)
0x6f6b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool>::.ctor(object, native int)
0x6f70  dup
0x6f71  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__20_0
0x6f76  call     T0x2B000008
0x6f7b  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x6f80  add
0x6f81  stloc.0
0x6f82  br.s     loc_6F8A
0x6f84  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0x6f89  stloc.0
0x6f8a  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x6f8f  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x6f94  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x6f99  add
0x6f9a  stloc.1
0x6f9b  ldloc.1
0x6f9c  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_countCleanWorkerProcesses
0x6fa1  bge      loc_7026
0x6fa6  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_countCleanWorkerProcesses
0x6fab  ldloc.1
0x6fac  sub
0x6fad  stloc.2
0x6fae  ldstr    aSandboxworkerm_38// "SandboxWorkerManager.CreateCleanWorkers"...
0x6fb3  ldc.i4.4
0x6fb4  newarr   [mscorlib]System.Object
0x6fb9  dup
0x6fba  ldc.i4.0
0x6fbb  ldloc.2
0x6fbc  box      [mscorlib]System.Int32
0x6fc1  stelem.ref
0x6fc2  dup
0x6fc3  ldc.i4.1
0x6fc4  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_countCleanWorkerProcesses
0x6fc9  box      [mscorlib]System.Int32
0x6fce  stelem.ref
0x6fcf  dup
0x6fd0  ldc.i4.2
0x6fd1  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri> Microsoft.Crm.Sandbox.SandboxWorkerManager::_cleanNativeProcessQueue
0x6fd6  callvirt instance int32 class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class [System]System.Uri>::get_Count()
0x6fdb  box      [mscorlib]System.Int32
0x6fe0  stelem.ref
0x6fe1  dup
0x6fe2  ldc.i4.3
0x6fe3  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupNativeProcess
0x6fe8  box      [mscorlib]System.Int32
0x6fed  stelem.ref
0x6fee  call     string [mscorlib]System.String::Format(string, object[])
0x6ff3  stloc.3
0x6ff4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6ff9  ldc.i4.s 0x21
0x6ffb  ldloc.3
0x6ffc  ldc.i4.0
0x6ffd  newarr   [mscorlib]System.Object
0x7002  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7007  ldc.i4.0
0x7008  stloc.s  4
0x700a  br.s     loc_7021
0x700c  volatile.
0x700e  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_shutdown
0x7013  brtrue.s loc_7026
0x7015  ldc.i4.0
0x7016  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundCreateNewWorkerProcess(bool useDrawbridgeIsolation)
0x701b  ldloc.s  4
0x701d  ldc.i4.1
0x701e  add
0x701f  stloc.s  4
0x7021  ldloc.s  4
0x7023  ldloc.2
0x7024  blt.s    loc_700C
0x7026  ldloc.0
0x7027  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0x702c  bge      loc_70E3
0x7031  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0x7036  ldloc.0
0x7037  sub
0x7038  stloc.s  5
0x703a  ldstr    aSandboxworkerm_39// "SandboxWorkerManager.CreateCleanWorkers"...
0x703f  ldc.i4.4
0x7040  newarr   [mscorlib]System.Object
0x7045  dup
0x7046  ldc.i4.0
0x7047  ldloc.s  5
0x7049  box      [mscorlib]System.Int32
0x704e  stelem.ref
0x704f  dup
0x7050  ldc.i4.1
0x7051  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_initialWorkerProcessCount
0x7056  box      [mscorlib]System.Int32
0x705b  stelem.ref
0x705c  dup
0x705d  ldc.i4.2
0x705e  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x7063  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::get_Values()
0x7068  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__20_1
0x706d  dup
0x706e  brtrue.s loc_7087
0x7070  pop
0x7071  ldsfld   class <>c <>c::<>9
0x7076  ldftn    instance bool <>c::<CreateCleanWorkers>b__20_1(class Microsoft.Crm.Sandbox.SandboxWorkerProcess x)
0x707c  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool>::.ctor(object, native int)
0x7081  dup
0x7082  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxWorkerProcess, bool> <>c::<>9__20_1
0x7087  call     T0x2B000008
0x708c  box      [mscorlib]System.Int32
0x7091  stelem.ref
0x7092  dup
0x7093  ldc.i4.3
0x7094  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_waitingStartupDrawbridgeProcess
0x7099  box      [mscorlib]System.Int32
0x709e  stelem.ref
0x709f  call     string [mscorlib]System.String::Format(string, object[])
0x70a4  stloc.s  6
0x70a6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x70ab  ldc.i4.s 0x21
0x70ad  ldloc.s  6
0x70af  ldc.i4.0
0x70b0  newarr   [mscorlib]System.Object
0x70b5  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x70ba  ldc.i4.0
0x70bb  stloc.s  7
0x70bd  br.s     loc_70D4
0x70bf  volatile.
0x70c1  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Sandbox.SandboxWorkerManager::_shutdown
0x70c6  brtrue.s loc_70E3
0x70c8  ldc.i4.1
0x70c9  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::BackgroundCreateNewWorkerProcess(bool useDrawbridgeIsolation)
0x70ce  ldloc.s  7
0x70d0  ldc.i4.1
0x70d1  add
0x70d2  stloc.s  7
0x70d4  ldloc.s  7
0x70d6  ldloc.s  5
0x70d8  bge.s    loc_70E3
0x70da  ldloc.s  7
0x70dc  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxWorkerManager::_countCleanWorkerProcesses
0x70e1  blt.s    loc_70BF
0x70e3  ret
```
