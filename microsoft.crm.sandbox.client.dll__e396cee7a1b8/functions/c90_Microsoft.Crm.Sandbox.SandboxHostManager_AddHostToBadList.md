# Microsoft.Crm.Sandbox.SandboxHostManager::AddHostToBadList

- ea: `0xc90`
- end: `0xdbb`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::AddHostToBadList`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x23d0`

## callees

- `0xc90`

## string_xrefs

- `0xcca`: `SandboxHostManager.AddHostToBadList: {0}: Removed host for isolation: {1} from loadbalancer`
- `0xd09`: `SandboxHostManager.AddHostToBadList: {0}: removedFromDrawbridgeReady: {1}`
- `0xd2d`: `SandboxHostManager.AddHostToBadList: {0}: removedFromDrawbridgePending: {1}`
- `0xd6c`: `SandboxHostManager.AddHostToBadList: {0}: removedFromNativeReady: {1}`
- `0xd90`: `SandboxHostManager.AddHostToBadList: {0}: removedFromNativePending: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xc90  ldarg.0
0xc91  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc96  brtrue   loc_DBA
0xc9b  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0xca0  ldc.i4.2
0xca1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0xca6  stloc.0
0xca7  call     class [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Instance()
0xcac  callvirt instance class [Autofac]Autofac.IContainer [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Container()
0xcb1  call     T0x2B000001
0xcb6  ldarg.1
0xcb7  callvirt instance class [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.IsolationTypeLoadBalancer::GetLoadBalancer(bool)
0xcbc  ldarg.0
0xcbd  callvirt instance bool [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer::RemoveRemoteHost(string)
0xcc2  pop
0xcc3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xcc8  ldc.i4.s 0x23
0xcca  ldstr    aSandboxhostman_17// "SandboxHostManager.AddHostToBadList: {0"...
0xccf  ldc.i4.2
0xcd0  newarr   [mscorlib]System.Object
0xcd5  dup
0xcd6  ldc.i4.0
0xcd7  ldarg.0
0xcd8  stelem.ref
0xcd9  dup
0xcda  ldc.i4.1
0xcdb  ldarg.1
0xcdc  box      [mscorlib]System.Boolean
0xce1  stelem.ref
0xce2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xce7  ldarg.1
0xce8  brfalse.s loc_D4C
0xcea  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgeReadyClients
0xcef  ldarg.0
0xcf0  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0xcf5  stloc.1
0xcf6  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_drawbridgePendingClients
0xcfb  ldarg.0
0xcfc  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0xd01  stloc.2
0xd02  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd07  ldc.i4.s 0x23
0xd09  ldstr    aSandboxhostman_18// "SandboxHostManager.AddHostToBadList: {0"...
0xd0e  ldc.i4.2
0xd0f  newarr   [mscorlib]System.Object
0xd14  dup
0xd15  ldc.i4.0
0xd16  ldarg.0
0xd17  stelem.ref
0xd18  dup
0xd19  ldc.i4.1
0xd1a  ldloc.1
0xd1b  box      [mscorlib]System.Boolean
0xd20  stelem.ref
0xd21  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd26  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd2b  ldc.i4.s 0x23
0xd2d  ldstr    aSandboxhostman_19// "SandboxHostManager.AddHostToBadList: {0"...
0xd32  ldc.i4.2
0xd33  newarr   [mscorlib]System.Object
0xd38  dup
0xd39  ldc.i4.0
0xd3a  ldarg.0
0xd3b  stelem.ref
0xd3c  dup
0xd3d  ldc.i4.1
0xd3e  ldloc.2
0xd3f  box      [mscorlib]System.Boolean
0xd44  stelem.ref
0xd45  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd4a  leave.s  loc_DBA
0xd4c  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativeReadyClients
0xd51  ldarg.0
0xd52  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0xd57  stloc.3
0xd58  ldsfld   class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> Microsoft.Crm.Sandbox.SandboxHostManager::_nativePendingClients
0xd5d  ldarg.0
0xd5e  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0xd63  stloc.s  4
0xd65  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd6a  ldc.i4.s 0x23
0xd6c  ldstr    aSandboxhostman_20// "SandboxHostManager.AddHostToBadList: {0"...
0xd71  ldc.i4.2
0xd72  newarr   [mscorlib]System.Object
0xd77  dup
0xd78  ldc.i4.0
0xd79  ldarg.0
0xd7a  stelem.ref
0xd7b  dup
0xd7c  ldc.i4.1
0xd7d  ldloc.3
0xd7e  box      [mscorlib]System.Boolean
0xd83  stelem.ref
0xd84  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd89  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd8e  ldc.i4.s 0x23
0xd90  ldstr    aSandboxhostman_21// "SandboxHostManager.AddHostToBadList: {0"...
0xd95  ldc.i4.2
0xd96  newarr   [mscorlib]System.Object
0xd9b  dup
0xd9c  ldc.i4.0
0xd9d  ldarg.0
0xd9e  stelem.ref
0xd9f  dup
0xda0  ldc.i4.1
0xda1  ldloc.s  4
0xda3  box      [mscorlib]System.Boolean
0xda8  stelem.ref
0xda9  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdae  leave.s  loc_DBA
0xdb0  ldloc.0
0xdb1  brfalse.s loc_DB9
0xdb3  ldloc.0
0xdb4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb9  endfinally
0xdba  ret
```
