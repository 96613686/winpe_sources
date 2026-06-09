# <PingHostsInternal>d__24::MoveNext

- ea: `0x85d0`
- end: `0x8918`
- name: `<PingHostsInternal>d__24::MoveNext`
- size: `840`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x7d0`
- `0x16c0`
- `0x1790`
- `0x85d0`

## string_xrefs

- `0x8613`: `_nativeReadyClients`
- `0x8622`: `_drawbridgeReadyClients`
- `0x869d`: `SandboxHostManager.PingHostsInternal: in: _nativeReadyClients clients: {0}`
- `0x86c6`: `SandboxHostManager.PingHostsInternal: in: _drawbridgeReadyClients clients: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x85d0  ldarg.0
0x85d1  ldfld    int32 <PingHostsInternal>d__24::<>1__state
0x85d6  stloc.0
0x85d7  ldloc.0
0x85d8  brfalse  loc_87B4
0x85dd  ldloc.0
0x85de  ldc.i4.1
0x85df  beq      loc_8818
0x85e4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x85e9  ldc.i4.s 0x23
0x85eb  ldstr    aSandboxhostman_45// "SandboxHostManager.PingHostsInternal: E"...
0x85f0  ldc.i4.0
0x85f1  newarr   [mscorlib]System.Object
0x85f6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x85fb  ldarg.0
0x85fc  ldfld    object <PingHostsInternal>d__24::stateObject
0x8601  ldnull
0x8602  ceq
0x8604  ldstr    aStateobjectNot// "stateObject not null"
0x8609  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x860e  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0x8613  ldstr    aNativereadycli// "_nativeReadyClients"
0x8618  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x861d  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0x8622  ldstr    aDrawbridgeread// "_drawbridgeReadyClients"
0x8627  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x862c  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativePendingClients
0x8631  ldstr    aNativependingc// "_nativePendingClients"
0x8636  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x863b  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgePendingClients
0x8640  ldstr    aDrawbridgepend// "_drawbridgePendingClients"
0x8645  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x864a  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0x864f  ldc.i4.0
0x8650  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x8655  stloc.3
0x8656  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo> Microsoft.Crm.Sandbox.SandboxHostManager::_hostNames
0x865b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x8660  stloc.1
0x8661  leave.s  loc_8671
0x8663  ldloc.0
0x8664  ldc.i4.0
0x8665  bge.s    loc_8670
0x8667  ldloc.3
0x8668  brfalse.s loc_8670
0x866a  ldloc.3
0x866b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8670  endfinally
0x8671  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8676  ldc.i4.s 0x23
0x8678  ldstr    aSandboxhostman_46// "SandboxHostManager.PingHostsInternal: c"...
0x867d  ldc.i4.1
0x867e  newarr   [mscorlib]System.Object
0x8683  dup
0x8684  ldc.i4.0
0x8685  ldloc.1
0x8686  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::get_Count()
0x868b  box      [mscorlib]System.Int32
0x8690  stelem.ref
0x8691  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8696  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x869b  ldc.i4.s 0x23
0x869d  ldstr    aSandboxhostman_47// "SandboxHostManager.PingHostsInternal: i"...
0x86a2  ldc.i4.1
0x86a3  newarr   [mscorlib]System.Object
0x86a8  dup
0x86a9  ldc.i4.0
0x86aa  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0x86af  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x86b4  box      [mscorlib]System.Int32
0x86b9  stelem.ref
0x86ba  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x86bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x86c4  ldc.i4.s 0x23
0x86c6  ldstr    aSandboxhostman_48// "SandboxHostManager.PingHostsInternal: i"...
0x86cb  ldc.i4.1
0x86cc  newarr   [mscorlib]System.Object
0x86d1  dup
0x86d2  ldc.i4.0
0x86d3  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0x86d8  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x86dd  box      [mscorlib]System.Int32
0x86e2  stelem.ref
0x86e3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x86e8  ldarg.0
0x86e9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor()
0x86ee  stfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<nativeHostsToPing>5__2
0x86f3  ldarg.0
0x86f4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::.ctor()
0x86f9  stfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<drawbridgeHostsToPing>5__3
0x86fe  ldloc.1
0x86ff  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::GetEnumerator()
0x8704  stloc.s  4
0x8706  br.s     loc_8758
0x8708  ldloca.s 4
0x870a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxHostInfo>::get_Current()
0x870f  stloc.s  5
0x8711  ldarg.0
0x8712  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<nativeHostsToPing>5__2
0x8717  ldloc.s  5
0x8719  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0x871e  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativePendingClients
0x8723  ldc.i4.0
0x8724  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.Crm.Sandbox.SandboxHostManager::CheckHostStatus(class Microsoft.Crm.Sandbox.SandboxHostInfo info, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> readyClients, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> pendingClients, bool useDrawbridgeEnabled)
0x8729  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::Add(var<u1>)
0x872e  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x8733  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x8738  ldc.i4.2
0x8739  bne.un.s loc_8758
0x873b  ldarg.0
0x873c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<drawbridgeHostsToPing>5__3
0x8741  ldloc.s  5
0x8743  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0x8748  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgePendingClients
0x874d  ldc.i4.1
0x874e  call     class [mscorlib]System.Threading.Tasks.Task`1<bool> Microsoft.Crm.Sandbox.SandboxHostManager::CheckHostStatus(class Microsoft.Crm.Sandbox.SandboxHostInfo info, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> readyClients, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> pendingClients, bool useDrawbridgeEnabled)
0x8753  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>>::Add(var<u1>)
0x8758  ldloca.s 4
0x875a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxHostInfo>::MoveNext()
0x875f  brtrue.s loc_8708
0x8761  leave.s  loc_8775
0x8763  ldloc.0
0x8764  ldc.i4.0
0x8765  bge.s    loc_8774
0x8767  ldloca.s 4
0x8769  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxHostInfo>
0x876f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8774  endfinally
0x8775  ldarg.0
0x8776  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<nativeHostsToPing>5__2
0x877b  call     T0x2B000021
0x8780  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool[]>::GetAwaiter()
0x8785  stloc.s  6
0x8787  ldloca.s 6
0x8789  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]>::get_IsCompleted()
0x878e  brtrue.s loc_87D1
0x8790  ldarg.0
0x8791  ldc.i4.0
0x8792  dup
0x8793  stloc.0
0x8794  stfld    int32 <PingHostsInternal>d__24::<>1__state
0x8799  ldarg.0
0x879a  ldloc.s  6
0x879c  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]> <PingHostsInternal>d__24::<>u__1
0x87a1  ldarg.0
0x87a2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PingHostsInternal>d__24::<>t__builder
0x87a7  ldloca.s 6
0x87a9  ldarg.0
0x87aa  call     T0x2B000022
0x87af  leave    loc_8917
0x87b4  ldarg.0
0x87b5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]> <PingHostsInternal>d__24::<>u__1
0x87ba  stloc.s  6
0x87bc  ldarg.0
0x87bd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]> <PingHostsInternal>d__24::<>u__1
0x87c2  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]>
0x87c8  ldarg.0
0x87c9  ldc.i4.m1
0x87ca  dup
0x87cb  stloc.0
0x87cc  stfld    int32 <PingHostsInternal>d__24::<>1__state
0x87d1  ldloca.s 6
0x87d3  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]>::GetResult()
0x87d8  pop
0x87d9  ldarg.0
0x87da  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<drawbridgeHostsToPing>5__3
0x87df  call     T0x2B000021
0x87e4  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<bool[]>::GetAwaiter()
0x87e9  stloc.s  6
0x87eb  ldloca.s 6
0x87ed  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]>::get_IsCompleted()
0x87f2  brtrue.s loc_8835
0x87f4  ldarg.0
0x87f5  ldc.i4.1
0x87f6  dup
0x87f7  stloc.0
0x87f8  stfld    int32 <PingHostsInternal>d__24::<>1__state
0x87fd  ldarg.0
0x87fe  ldloc.s  6
0x8800  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]> <PingHostsInternal>d__24::<>u__1
0x8805  ldarg.0
0x8806  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PingHostsInternal>d__24::<>t__builder
0x880b  ldloca.s 6
0x880d  ldarg.0
0x880e  call     T0x2B000022
0x8813  leave    loc_8917
0x8818  ldarg.0
0x8819  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]> <PingHostsInternal>d__24::<>u__1
0x881e  stloc.s  6
0x8820  ldarg.0
0x8821  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]> <PingHostsInternal>d__24::<>u__1
0x8826  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]>
0x882c  ldarg.0
0x882d  ldc.i4.m1
0x882e  dup
0x882f  stloc.0
0x8830  stfld    int32 <PingHostsInternal>d__24::<>1__state
0x8835  ldloca.s 6
0x8837  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<bool[]>::GetResult()
0x883c  pop
0x883d  ldc.i4.0
0x883e  stloc.2
0x883f  ldarg.0
0x8840  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<nativeHostsToPing>5__2
0x8845  ldloca.s 2
0x8847  call     void Microsoft.Crm.Sandbox.SandboxHostManager::UpdateBadCount(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> nativeHostsToPing, int32& nativeBadCount)
0x884c  ldarg.0
0x884d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> <PingHostsInternal>d__24::<drawbridgeHostsToPing>5__3
0x8852  ldloca.s 2
0x8854  call     void Microsoft.Crm.Sandbox.SandboxHostManager::UpdateBadCount(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.Tasks.Task`1<bool>> nativeHostsToPing, int32& nativeBadCount)
0x8859  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x885e  ldc.i4.s 0x23
0x8860  ldstr    aSandboxhostman_49// "SandboxHostManager.PingHostsInternal: o"...
0x8865  ldc.i4.1
0x8866  newarr   [mscorlib]System.Object
0x886b  dup
0x886c  ldc.i4.0
0x886d  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativePendingClients
0x8872  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x8877  box      [mscorlib]System.Int32
0x887c  stelem.ref
0x887d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8882  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8887  ldc.i4.s 0x23
0x8889  ldstr    aSandboxhostman_50// "SandboxHostManager.PingHostsInternal: o"...
0x888e  ldc.i4.1
0x888f  newarr   [mscorlib]System.Object
0x8894  dup
0x8895  ldc.i4.0
0x8896  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgePendingClients
0x889b  callvirt instance int32 class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Count()
0x88a0  box      [mscorlib]System.Int32
0x88a5  stelem.ref
0x88a6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x88ab  call     int32 Microsoft.Crm.Sandbox.SandboxHostManager::get_SandboxHostsCount()
0x88b0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::SetTotalNumberOfSandboxHosts(int32)
0x88b5  ldloc.2
0x88b6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::SetNumberOfBadSandboxHosts(int32)
0x88bb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCounter::PublishClientCounters()
0x88c0  ldnull
0x88c1  ldftn    void Microsoft.Crm.Sandbox.SandboxStatisticsHelper::WriteWorkerExecutionRecords(object notUsed)
0x88c7  newobj   instance void [mscorlib]System.Threading.WaitCallback::.ctor(object, native int)
0x88cc  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback)
0x88d1  pop
0x88d2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x88d7  ldc.i4.s 0x23
0x88d9  ldstr    aSandboxhostman_51// "SandboxHostManager.PingHostsInternal: E"...
0x88de  ldc.i4.0
0x88df  newarr   [mscorlib]System.Object
0x88e4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x88e9  leave.s  loc_8904
0x88eb  stloc.s  7
0x88ed  ldarg.0
0x88ee  ldc.i4.s 0xFE
0x88f0  stfld    int32 <PingHostsInternal>d__24::<>1__state
0x88f5  ldarg.0
0x88f6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PingHostsInternal>d__24::<>t__builder
0x88fb  ldloc.s  7
0x88fd  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x8902  leave.s  loc_8917
0x8904  ldarg.0
0x8905  ldc.i4.s 0xFE
0x8907  stfld    int32 <PingHostsInternal>d__24::<>1__state
0x890c  ldarg.0
0x890d  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <PingHostsInternal>d__24::<>t__builder
0x8912  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x8917  ret
```
