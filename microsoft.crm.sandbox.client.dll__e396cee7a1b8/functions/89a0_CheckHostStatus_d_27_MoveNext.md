# <CheckHostStatus>d__27::MoveNext

- ea: `0x89a0`
- end: `0x8d1b`
- name: `<CheckHostStatus>d__27::MoveNext`
- size: `891`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x510`
- `0x520`
- `0x530`
- `0x560`
- `0x600`
- `0x640`
- `0x660`
- `0x1470`
- `0x1700`
- `0x8940`
- `0x89a0`

## string_xrefs

- `0x89f9`: `SandboxHostManager.CheckHostStatus: found on ready clients list: {0}`
- `0x8c6c`: `SandboxHostManager.CheckHostStatus: adding to ready list: {0}`
- `0x8cb9`: `SandboxHostManager.CheckHostStatus: {0}: removedFromPending: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x89a0  ldarg.0
0x89a1  ldfld    int32 <CheckHostStatus>d__27::<>1__state
0x89a6  stloc.0
0x89a7  newobj   instance void <>c__DisplayClass27_0::.ctor()
0x89ac  stloc.2
0x89ad  ldarg.0
0x89ae  ldfld    class Microsoft.Crm.Sandbox.SandboxHostInfo <CheckHostStatus>d__27::info
0x89b3  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_MachineName()
0x89b8  stloc.3
0x89b9  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x89be  ldstr    aSandboxhostman_52// "SandboxHostManager.CheckHostStatus: che"...
0x89c3  ldc.i4.1
0x89c4  newarr   [mscorlib]System.Object
0x89c9  dup
0x89ca  ldc.i4.0
0x89cb  ldloc.3
0x89cc  stelem.ref
0x89cd  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x89d2  ldloc.2
0x89d3  ldnull
0x89d4  stfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x89d9  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0x89de  ldc.i4.0
0x89df  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x89e4  stloc.s  5
0x89e6  ldarg.0
0x89e7  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::readyClients
0x89ec  ldloc.3
0x89ed  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::ContainsKey(var<u1>)
0x89f2  brfalse.s loc_8A46
0x89f4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x89f9  ldstr    aSandboxhostman_53// "SandboxHostManager.CheckHostStatus: fou"...
0x89fe  ldc.i4.1
0x89ff  newarr   [mscorlib]System.Object
0x8a04  dup
0x8a05  ldc.i4.0
0x8a06  ldloc.3
0x8a07  stelem.ref
0x8a08  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8a0d  ldloc.2
0x8a0e  ldarg.0
0x8a0f  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::readyClients
0x8a14  ldloc.3
0x8a15  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Item(void)
0x8a1a  stfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8a1f  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox()
0x8a24  brtrue.s loc_8A39
0x8a26  ldloc.2
0x8a27  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8a2c  callvirt instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteMachineName()
0x8a31  ldloc.3
0x8a32  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8a37  br.s     loc_8A3A
0x8a39  ldc.i4.1
0x8a3a  ldstr    aClientNameShou// "Client name should be same as machine n"...
0x8a3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8a44  br.s     loc_8AA4
0x8a46  ldarg.0
0x8a47  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::pendingClients
0x8a4c  ldloc.3
0x8a4d  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::ContainsKey(var<u1>)
0x8a52  brfalse.s loc_8AA4
0x8a54  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8a59  ldstr    aSandboxhostman_54// "SandboxHostManager.CheckHostStatus: fou"...
0x8a5e  ldc.i4.1
0x8a5f  newarr   [mscorlib]System.Object
0x8a64  dup
0x8a65  ldc.i4.0
0x8a66  ldloc.3
0x8a67  stelem.ref
0x8a68  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8a6d  ldloc.2
0x8a6e  ldarg.0
0x8a6f  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::pendingClients
0x8a74  ldloc.3
0x8a75  callvirt instance var<u1> class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::get_Item(void)
0x8a7a  stfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8a7f  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox()
0x8a84  brtrue.s loc_8A99
0x8a86  ldloc.2
0x8a87  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8a8c  callvirt instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteMachineName()
0x8a91  ldloc.3
0x8a92  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8a97  br.s     loc_8A9A
0x8a99  ldc.i4.1
0x8a9a  ldstr    aClientNameShou// "Client name should be same as machine n"...
0x8a9f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8aa4  leave.s  loc_8AB6
0x8aa6  ldloc.0
0x8aa7  ldc.i4.0
0x8aa8  bge.s    loc_8AB5
0x8aaa  ldloc.s  5
0x8aac  brfalse.s loc_8AB5
0x8aae  ldloc.s  5
0x8ab0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ab5  endfinally
0x8ab6  ldloc.2
0x8ab7  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8abc  brtrue   loc_8B6C
0x8ac1  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8ac6  ldstr    aSandboxhostman_55// "SandboxHostManager.CheckHostStatus: new"...
0x8acb  ldc.i4.1
0x8acc  newarr   [mscorlib]System.Object
0x8ad1  dup
0x8ad2  ldc.i4.0
0x8ad3  ldloc.3
0x8ad4  stelem.ref
0x8ad5  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8ada  ldloc.2
0x8adb  newobj   instance void Microsoft.Crm.Sandbox.SandboxClient::.ctor()
0x8ae0  stfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8ae5  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox()
0x8aea  brfalse.s loc_8B01
0x8aec  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8af1  ldstr    aSandboxhostman_56// "SandboxHostManager.CheckHostStatus: sin"...
0x8af6  ldc.i4.0
0x8af7  newarr   [mscorlib]System.Object
0x8afc  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8b01  ldloc.2
0x8b02  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8b07  ldloc.3
0x8b08  callvirt instance void Microsoft.Crm.Sandbox.SandboxClient::set_RemoteMachineName(string value)
0x8b0d  ldloc.2
0x8b0e  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8b13  ldarg.0
0x8b14  ldfld    class Microsoft.Crm.Sandbox.SandboxHostInfo <CheckHostStatus>d__27::info
0x8b19  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_FullMachineName()
0x8b1e  callvirt instance void Microsoft.Crm.Sandbox.SandboxClient::set_RemoteFullMachineName(string value)
0x8b23  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8b28  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class SandboxHostPingSingleHostActivity>::get_Instance()
0x8b2d  ldloc.2
0x8b2e  ldftn    instance void <>c__DisplayClass27_0::<CheckHostStatus>b__0()
0x8b34  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x8b39  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x8b3e  leave.s  loc_8B6C
0x8b40  stloc.s  6
0x8b42  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8b47  ldstr    aSandboxhostman_57// "SandboxHostManager.CheckHostStatus: EXC"...
0x8b4c  ldc.i4.2
0x8b4d  newarr   [mscorlib]System.Object
0x8b52  dup
0x8b53  ldc.i4.0
0x8b54  ldloc.3
0x8b55  stelem.ref
0x8b56  dup
0x8b57  ldc.i4.1
0x8b58  ldloc.s  6
0x8b5a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8b5f  stelem.ref
0x8b60  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8b65  ldc.i4.0
0x8b66  stloc.1
0x8b67  leave    loc_8D06
0x8b6c  ldloc.2
0x8b6d  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8b72  ldstr    aPingclient// "pingClient"
0x8b77  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8b7c  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_IsSingleBox()
0x8b81  brtrue.s loc_8B96
0x8b83  ldloc.2
0x8b84  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8b89  callvirt instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteMachineName()
0x8b8e  ldloc.3
0x8b8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8b94  br.s     loc_8B97
0x8b96  ldc.i4.1
0x8b97  ldstr    aClientNameShou// "Client name should be same as machine n"...
0x8b9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8ba1  ldloc.2
0x8ba2  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8ba7  ldarg.0
0x8ba8  ldfld    class Microsoft.Crm.Sandbox.SandboxHostInfo <CheckHostStatus>d__27::info
0x8bad  ldarg.0
0x8bae  ldfld    bool <CheckHostStatus>d__27::useDrawbridgeEnabled
0x8bb3  call     void Microsoft.Crm.Sandbox.SandboxHostManager::PingSingleClient(class Microsoft.Crm.Sandbox.SandboxClient pingClient, class Microsoft.Crm.Sandbox.SandboxHostInfo info, bool useDrawbridgeEnabled)
0x8bb8  call     class [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Instance()
0x8bbd  ldstr    aKernelNotIniti// "Kernel not initialized"
0x8bc2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8bc7  call     class [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Instance()
0x8bcc  callvirt instance class [Autofac]Autofac.IContainer [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Container()
0x8bd1  ldstr    aKernelContaine// "Kernel Container not initialized"
0x8bd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8bdb  call     class [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Instance()
0x8be0  callvirt instance class [Autofac]Autofac.IContainer [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Container()
0x8be5  call     T0x2B000001
0x8bea  dup
0x8beb  ldstr    aLoadBalancerNo// "Load balancer not registered at Kernel."
0x8bf0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8bf5  ldarg.0
0x8bf6  ldfld    bool <CheckHostStatus>d__27::useDrawbridgeEnabled
0x8bfb  callvirt instance class [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.IsolationTypeLoadBalancer::GetLoadBalancer(bool)
0x8c00  stloc.s  4
0x8c02  ldloc.2
0x8c03  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8c08  callvirt instance valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxClient::get_HostStatus()
0x8c0d  ldc.i4.3
0x8c0e  beq.s    loc_8C5A
0x8c10  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8c15  ldstr    aSandboxhostman_58// "SandboxHostManager.CheckHostStatus: pin"...
0x8c1a  ldc.i4.1
0x8c1b  newarr   [mscorlib]System.Object
0x8c20  dup
0x8c21  ldc.i4.0
0x8c22  ldarg.0
0x8c23  ldfld    class Microsoft.Crm.Sandbox.SandboxHostInfo <CheckHostStatus>d__27::info
0x8c28  callvirt instance string Microsoft.Crm.Sandbox.SandboxHostInfo::get_MachineName()
0x8c2d  stelem.ref
0x8c2e  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8c33  ldloc.s  4
0x8c35  ldloc.3
0x8c36  callvirt instance bool [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer::RemoveRemoteHost(string)
0x8c3b  pop
0x8c3c  ldarg.0
0x8c3d  ldfld    class Microsoft.Crm.Sandbox.SandboxHostInfo <CheckHostStatus>d__27::info
0x8c42  ldarg.0
0x8c43  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::readyClients
0x8c48  ldarg.0
0x8c49  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::pendingClients
0x8c4e  call     void Microsoft.Crm.Sandbox.SandboxHostManager::ProcessBadList(class Microsoft.Crm.Sandbox.SandboxHostInfo badHost, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> readyClients, class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> pendingClients)
0x8c53  ldc.i4.0
0x8c54  stloc.1
0x8c55  leave    loc_8D06
0x8c5a  ldsfld   class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxHostManager::_listsLock
0x8c5f  ldc.i4.2
0x8c60  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x8c65  stloc.s  5
0x8c67  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8c6c  ldstr    aSandboxhostman_59// "SandboxHostManager.CheckHostStatus: add"...
0x8c71  ldc.i4.1
0x8c72  newarr   [mscorlib]System.Object
0x8c77  dup
0x8c78  ldc.i4.0
0x8c79  ldloc.3
0x8c7a  stelem.ref
0x8c7b  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8c80  ldarg.0
0x8c81  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::readyClients
0x8c86  ldloc.3
0x8c87  ldloc.2
0x8c88  ldfld    class Microsoft.Crm.Sandbox.SandboxClient <>c__DisplayClass27_0::pingClient
0x8c8d  callvirt instance void class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::set_Item(var<u1>, !!T0)
0x8c92  ldloc.s  4
0x8c94  ldloc.3
0x8c95  ldloc.2
0x8c96  ldftn    instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin <>c__DisplayClass27_0::<CheckHostStatus>b__1(class [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest request)
0x8c9c  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin>::.ctor(object, native int)
0x8ca1  callvirt instance void [Microsoft.Xrm.RemotePlugin.Client]Microsoft.Xrm.RemotePlugin.Client.IRemoteHostLoadBalancer::AddRemoteHost(string, class [mscorlib]System.Func`2<class [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin>)
0x8ca6  ldarg.0
0x8ca7  ldfld    class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient> <CheckHostStatus>d__27::pendingClients
0x8cac  ldloc.3
0x8cad  callvirt instance bool class [System]System.Collections.Generic.SortedList`2<string, class Microsoft.Crm.Sandbox.SandboxClient>::Remove(var<u1>)
0x8cb2  stloc.s  7
0x8cb4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Sandbox.SandboxHostManager::Logger
0x8cb9  ldstr    aSandboxhostman_60// "SandboxHostManager.CheckHostStatus: {0}"...
0x8cbe  ldc.i4.2
0x8cbf  newarr   [mscorlib]System.Object
0x8cc4  dup
0x8cc5  ldc.i4.0
0x8cc6  ldloc.3
0x8cc7  stelem.ref
0x8cc8  dup
0x8cc9  ldc.i4.1
0x8cca  ldloc.s  7
0x8ccc  box      [mscorlib]System.Boolean
0x8cd1  stelem.ref
0x8cd2  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogTrace(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x8cd7  leave.s  loc_8CE9
0x8cd9  ldloc.0
0x8cda  ldc.i4.0
0x8cdb  bge.s    loc_8CE8
0x8cdd  ldloc.s  5
0x8cdf  brfalse.s loc_8CE8
0x8ce1  ldloc.s  5
0x8ce3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8ce8  endfinally
0x8ce9  ldc.i4.1
0x8cea  stloc.1
0x8ceb  leave.s  loc_8D06
0x8ced  stloc.s  8
0x8cef  ldarg.0
0x8cf0  ldc.i4.s 0xFE
0x8cf2  stfld    int32 <CheckHostStatus>d__27::<>1__state
0x8cf7  ldarg.0
0x8cf8  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <CheckHostStatus>d__27::<>t__builder
0x8cfd  ldloc.s  8
0x8cff  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetException(class [mscorlib]System.Exception)
0x8d04  leave.s  loc_8D1A
0x8d06  ldarg.0
0x8d07  ldc.i4.s 0xFE
0x8d09  stfld    int32 <CheckHostStatus>d__27::<>1__state
0x8d0e  ldarg.0
0x8d0f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool> <CheckHostStatus>d__27::<>t__builder
0x8d14  ldloc.1
0x8d15  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<bool>::SetResult(var<u1>)
0x8d1a  ret
```
