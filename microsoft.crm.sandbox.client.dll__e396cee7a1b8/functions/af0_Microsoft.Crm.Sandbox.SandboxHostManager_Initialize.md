# Microsoft.Crm.Sandbox.SandboxHostManager::Initialize

- ea: `0xaf0`
- end: `0xc2c`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::Initialize`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1230`

## callees

- `0xaf0`
- `0xed0`

## string_xrefs

- `0xb15`: `SandboxHostManager.Initialize: already initialized`

## pseudocode

```c

```

## disassembly

```asm
0xaf0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xaf5  ldc.i4.s 0x23
0xaf7  ldstr    aSandboxhostman_11// "SandboxHostManager.Initialize: enter"
0xafc  ldc.i4.0
0xafd  newarr   [mscorlib]System.Object
0xb02  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb07  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_initialized
0xb0c  brfalse.s loc_B26
0xb0e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb13  ldc.i4.s 0x23
0xb15  ldstr    aSandboxhostman_12// "SandboxHostManager.Initialize: already "...
0xb1a  ldc.i4.0
0xb1b  newarr   [mscorlib]System.Object
0xb20  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb25  ret
0xb26  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb2b  ldc.i4.s 0x23
0xb2d  ldstr    aSandboxhostman_13// "SandboxHostManager.Initialize: first ti"...
0xb32  ldc.i4.0
0xb33  newarr   [mscorlib]System.Object
0xb38  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb3d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceProvider::Initialize()
0xb42  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceCounter::InitializeCounters()
0xb47  call     void Microsoft.Crm.Sandbox.SandboxHostManager::InitializeInternal()
0xb4c  ldc.i4.s 0x1A
0xb4e  ldnull
0xb4f  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xb55  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xb5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xb5f  ldc.i4.s 0x2B
0xb61  ldnull
0xb62  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xb68  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xb6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xb72  ldc.i4.s 0x2D
0xb74  ldnull
0xb75  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xb7b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xb80  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xb85  ldc.i4.s 0x1B
0xb87  ldnull
0xb88  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xb8e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xb93  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xb98  ldc.i4.s 0x1D
0xb9a  ldnull
0xb9b  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xba1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xba6  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbab  ldc.i4.s 0x20
0xbad  ldnull
0xbae  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbb4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbb9  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbbe  ldc.i4.s 0x1E
0xbc0  ldnull
0xbc1  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbc7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbcc  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbd1  ldc.i4.s 0x17
0xbd3  ldnull
0xbd4  ldftn    void Microsoft.Crm.Sandbox.SandboxHostManager::HandleNotification(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs args)
0xbda  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0xbdf  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0xbe4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.DBNotificationsProvider::.ctor()
0xbe9  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::StartNotificationsThread(class [Microsoft.Crm.Core]Microsoft.Crm.INotificationsProvider)
0xbee  call     class [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Instance()
0xbf3  callvirt instance class [Autofac]Autofac.IContainer [Microsoft.Xrm.Kernel.Runtime]Microsoft.Xrm.Kernel.Runtime.KernelState::get_Container()
0xbf8  call     T0x2B000001
0xbfd  ldnull
0xbfe  ldftn    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin Microsoft.Crm.Sandbox.SandboxHostManager::RetrieveReadyPlugin(bool useDrawbridgeIsolation, class [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest request)
0xc04  newobj   instance void class [mscorlib]System.Func`3<bool, class [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin>::.ctor(object, native int)
0xc09  callvirt instance void [Microsoft.Xrm.RemotePlugin.CrmProvider]Microsoft.Xrm.RemotePlugin.CrmProvider.IsolationTypeLoadBalancer::SetPluginFactory(class [mscorlib]System.Func`3<bool, class [Microsoft.Xrm.RemotePlugin.Common]Microsoft.Xrm.RemotePlugin.Common.RemotePluginRequest, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin>)
0xc0e  ldc.i4.1
0xc0f  stsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_initialized
0xc14  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc19  ldc.i4.s 0x23
0xc1b  ldstr    aSandboxhostman_14// "SandboxHostManager.Initialize: exit"
0xc20  ldc.i4.0
0xc21  newarr   [mscorlib]System.Object
0xc26  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc2b  ret
```
