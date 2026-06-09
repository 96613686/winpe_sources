# Microsoft.Crm.Sandbox.SandboxHostManager::UpdateHostNames

- ea: `0x7e0`
- end: `0xae1`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::UpdateHostNames`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0xed0`

## callees

- `0x620`
- `0x640`
- `0x660`
- `0x7e0`

## string_xrefs

- `0x7f2`: `SandboxHostManager.UpdateHostNames: newHostList.Count: {0}`
- `0x858`: `SandboxHostManager.UpdateHostNames: Existing host name: {0}`
- `0x892`: `SandboxHostManager.UpdateHostNames: Deleting host name: {0}`
- `0x923`: `SandboxHostManager.UpdateHostNames: {0}: removed from load balancer for drawbridge`
- `0x93f`: `SandboxHostManager.UpdateHostNames: {0}: removed from load balancer for native`
- `0x95b`: `SandboxHostManager.UpdateHostNames: {0}: removedFromNativeReady: {1}`
- `0x981`: `SandboxHostManager.UpdateHostNames: {0}: removedFromDrawbridgeReady: {1}`
- `0x9a7`: `SandboxHostManager.UpdateHostNames: {0}: removedFromNativePending: {1}`
- `0x9cd`: `SandboxHostManager.UpdateHostNames: {0}: removedFromDrawbridgePending: {1}`
- `0xa32`: `SandboxHostManager.UpdateHostNames: Adding host name: {0}`
- `0xa83`: `SandboxHostManager.UpdateHostNames: Updating host names`
- `0xad0`: `SandboxHostManager.UpdateHostNames: exit`

## pseudocode

```c

```

## disassembly

```asm
0x7e0  ldarg.0
0x7e1  ldstr    aNewhostlist// "newHostList"
0x7e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7eb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7f0  ldc.i4.s 0x23
0x7f2  ldstr    aSandboxhostman// "SandboxHostManager.UpdateHostNames: new"...
0x7f7  ldc.i4.1
0x7f8  newarr   [mscorlib]System.Object
0x7fd  dup
0x7fe  ldc.i4.0
0x7ff  ldarg.0
0x800  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::get_Count()
0x805  box      [mscorlib]System.Int32
0x80a  stelem.ref
0x80b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x810  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::.ctor()
0x815  stloc.0
0x816  ldc.i4.0
0x817  stloc.1
0x818  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo> Microsoft.Crm.Sandbox.SandboxHostManager::_hostNames
0x81d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::GetEnumerator()
0x822  stloc.2
0x823  br       loc_9FA
0x828  ldloca.s 2
0x82a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxHostInfo>::get_Current()
0x82f  stloc.3
0x830  ldloc.3
0x831  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_MachineName()
0x836  stloc.s  4
0x838  ldloc.3
0x839  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_FullMachineName()
0x83e  stloc.s  5
0x840  ldarg.0
0x841  ldloc.s  4
0x843  ldloc.s  5
0x845  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x84a  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::Contains(var<u1>)
0x84f  brfalse.s loc_889
0x851  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x856  ldc.i4.s 0x23
0x858  ldstr    aSandboxhostman_0// "SandboxHostManager.UpdateHostNames: Exi"...
0x85d  ldc.i4.1
0x85e  newarr   [mscorlib]System.Object
0x863  dup
0x864  ldc.i4.0
0x865  ldloc.s  4
0x867  stelem.ref
0x868  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x86d  ldloc.0
0x86e  ldloc.3
0x86f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::Add(var<u1>)
0x874  ldarg.0
0x875  ldloc.s  4
0x877  ldloc.s  5
0x879  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0x87e  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::Remove(var<u1>)
0x883  pop
0x884  br       loc_9FA
0x889  ldc.i4.1
0x88a  stloc.1
0x88b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x890  ldc.i4.s 0x23
0x892  ldstr    aSandboxhostman_1// "SandboxHostManager.UpdateHostNames: Del"...
0x897  ldc.i4.1
0x898  newarr   [mscorlib]System.Object
0x89d  dup
0x89e  ldc.i4.0
0x89f  ldloc.s  4
0x8a1  stelem.ref
0x8a2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8a7  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0x8ac  ldc.i4.2
0x8ad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x8b2  stloc.s  6
0x8b4  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0x8b9  ldloc.s  4
0x8bb  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0x8c0  stloc.s  7
0x8c2  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0x8c7  ldloc.s  4
0x8c9  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0x8ce  stloc.s  8
0x8d0  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativePendingClients
0x8d5  ldloc.s  4
0x8d7  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0x8dc  stloc.s  9
0x8de  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgePendingClients
0x8e3  ldloc.s  4
0x8e5  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0x8ea  stloc.s  0xA
0x8ec  call     class [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Instance()
0x8f1  callvirt instance class [Autofac]Autofac.IContainer [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Container()
0x8f6  call     T0x2B000001
0x8fb  dup
0x8fc  ldc.i4.1
0x8fd  callvirt instance class [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.IsolationTypeLoadBalancer::GetLoadBalancer(bool)
0x902  stloc.s  0xB
0x904  ldc.i4.0
0x905  callvirt instance class [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.IsolationTypeLoadBalancer::GetLoadBalancer(bool)
0x90a  ldloc.s  0xB
0x90c  ldloc.s  4
0x90e  callvirt instance bool [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer::RemoveRemoteHost(string)
0x913  pop
0x914  ldloc.s  4
0x916  callvirt instance bool [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer::RemoveRemoteHost(string)
0x91b  pop
0x91c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x921  ldc.i4.s 0x23
0x923  ldstr    aSandboxhostman_2// "SandboxHostManager.UpdateHostNames: {0}"...
0x928  ldc.i4.1
0x929  newarr   [mscorlib]System.Object
0x92e  dup
0x92f  ldc.i4.0
0x930  ldloc.s  4
0x932  stelem.ref
0x933  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x938  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x93d  ldc.i4.s 0x23
0x93f  ldstr    aSandboxhostman_3// "SandboxHostManager.UpdateHostNames: {0}"...
0x944  ldc.i4.1
0x945  newarr   [mscorlib]System.Object
0x94a  dup
0x94b  ldc.i4.0
0x94c  ldloc.s  4
0x94e  stelem.ref
0x94f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x954  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x959  ldc.i4.s 0x23
0x95b  ldstr    aSandboxhostman_4// "SandboxHostManager.UpdateHostNames: {0}"...
0x960  ldc.i4.2
0x961  newarr   [mscorlib]System.Object
0x966  dup
0x967  ldc.i4.0
0x968  ldloc.s  4
0x96a  stelem.ref
0x96b  dup
0x96c  ldc.i4.1
0x96d  ldloc.s  7
0x96f  box      [mscorlib]System.Boolean
0x974  stelem.ref
0x975  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x97a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x97f  ldc.i4.s 0x23
0x981  ldstr    aSandboxhostman_5// "SandboxHostManager.UpdateHostNames: {0}"...
0x986  ldc.i4.2
0x987  newarr   [mscorlib]System.Object
0x98c  dup
0x98d  ldc.i4.0
0x98e  ldloc.s  4
0x990  stelem.ref
0x991  dup
0x992  ldc.i4.1
0x993  ldloc.s  8
0x995  box      [mscorlib]System.Boolean
0x99a  stelem.ref
0x99b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9a5  ldc.i4.s 0x23
0x9a7  ldstr    aSandboxhostman_6// "SandboxHostManager.UpdateHostNames: {0}"...
0x9ac  ldc.i4.2
0x9ad  newarr   [mscorlib]System.Object
0x9b2  dup
0x9b3  ldc.i4.0
0x9b4  ldloc.s  4
0x9b6  stelem.ref
0x9b7  dup
0x9b8  ldc.i4.1
0x9b9  ldloc.s  9
0x9bb  box      [mscorlib]System.Boolean
0x9c0  stelem.ref
0x9c1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9c6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9cb  ldc.i4.s 0x23
0x9cd  ldstr    aSandboxhostman_7// "SandboxHostManager.UpdateHostNames: {0}"...
0x9d2  ldc.i4.2
0x9d3  newarr   [mscorlib]System.Object
0x9d8  dup
0x9d9  ldc.i4.0
0x9da  ldloc.s  4
0x9dc  stelem.ref
0x9dd  dup
0x9de  ldc.i4.1
0x9df  ldloc.s  0xA
0x9e1  box      [mscorlib]System.Boolean
0x9e6  stelem.ref
0x9e7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9ec  leave.s  loc_9FA
0x9ee  ldloc.s  6
0x9f0  brfalse.s loc_9F9
0x9f2  ldloc.s  6
0x9f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9f9  endfinally
0x9fa  ldloca.s 2
0x9fc  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxHostInfo>::MoveNext()
0xa01  brtrue   loc_828
0xa06  leave.s  loc_A16
0xa08  ldloca.s 2
0xa0a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Sandbox.SandboxHostInfo>
0xa10  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa15  endfinally
0xa16  ldarg.0
0xa17  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::GetEnumerator()
0xa1c  stloc.s  0xC
0xa1e  br.s     loc_A60
0xa20  ldloca.s 0xC
0xa22  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<string, string>>::get_Current()
0xa27  stloc.s  0xD
0xa29  ldc.i4.1
0xa2a  stloc.1
0xa2b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa30  ldc.i4.s 0x23
0xa32  ldstr    aSandboxhostman_8// "SandboxHostManager.UpdateHostNames: Add"...
0xa37  ldc.i4.1
0xa38  newarr   [mscorlib]System.Object
0xa3d  dup
0xa3e  ldc.i4.0
0xa3f  ldloc.s  0xD
0xa41  stelem.ref
0xa42  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa47  ldloc.0
0xa48  ldloc.s  0xD
0xa4a  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item1()
0xa4f  ldloc.s  0xD
0xa51  callvirt instance var<u1> class [mscorlib]System.Tuple`2<string, string>::get_Item2()
0xa56  newobj   instance void Microsoft.Crm.Sandbox.SandboxHostInfo::.ctor(string machineName, string fullMachineName)
0xa5b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::Add(var<u1>)
0xa60  ldloca.s 0xC
0xa62  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<string, string>>::MoveNext()
0xa67  brtrue.s loc_A20
0xa69  leave.s  loc_A79
0xa6b  ldloca.s 0xC
0xa6d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`2<string, string>>
0xa73  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa78  endfinally
0xa79  ldloc.1
0xa7a  brfalse.s loc_AC9
0xa7c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa81  ldc.i4.s 0x23
0xa83  ldstr    aSandboxhostman_9// "SandboxHostManager.UpdateHostNames: Upd"...
0xa88  ldc.i4.0
0xa89  newarr   [mscorlib]System.Object
0xa8e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa93  ldloc.0
0xa94  stsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo> Microsoft.Crm.Sandbox.SandboxHostManager::_hostNames
0xa99  newobj   instance void [mscorlib]System.Random::.ctor()
0xa9e  dup
0xa9f  ldc.i4.0
0xaa0  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo> Microsoft.Crm.Sandbox.SandboxHostManager::_hostNames
0xaa5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::get_Count()
0xaaa  callvirt instance int32 [mscorlib]System.Random::Next(int32, int32)
0xaaf  stsfld   int32 Microsoft.Crm.Sandbox.SandboxHostManager::_nextNativeClientIndex
0xab4  ldc.i4.0
0xab5  ldsfld   class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo> Microsoft.Crm.Sandbox.SandboxHostManager::_hostNames
0xaba  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxHostInfo>::get_Count()
0xabf  callvirt instance int32 [mscorlib]System.Random::Next(int32, int32)
0xac4  stsfld   int32 Microsoft.Crm.Sandbox.SandboxHostManager::_nextDrawbridgeClientIndex
0xac9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xace  ldc.i4.s 0x23
0xad0  ldstr    aSandboxhostman_10// "SandboxHostManager.UpdateHostNames: exi"...
0xad5  ldc.i4.0
0xad6  newarr   [mscorlib]System.Object
0xadb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xae0  ret
```
