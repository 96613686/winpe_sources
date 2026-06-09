# Microsoft.Crm.Sandbox.SandboxHostManager::InitializeInternal

- ea: `0xed0`
- end: `0x1094`
- name: `Microsoft.Crm.Sandbox.SandboxHostManager::InitializeInternal`
- size: `452`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xaf0`
- `0xdc0`

## callees

- `0x7e0`
- `0xe40`
- `0xea0`
- `0xed0`
- `0x10a0`
- `0x38e0`
- `0x4e60`

## pseudocode

```c

```

## disassembly

```asm
0xed0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xed5  ldc.i4.s 0x23
0xed7  ldstr    aSandboxhostman_23// "SandboxHostManager.InitializeInternal: "...
0xedc  ldc.i4.0
0xedd  newarr   [mscorlib]System.Object
0xee2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xee7  call     void Microsoft.Crm.Sandbox.SandboxHostManager::GetDeploymentProperties()
0xeec  call     void Microsoft.Crm.Sandbox.SandboxHostManager::GetTraceDeploymentProperties()
0xef1  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::.ctor()
0xef6  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveEnabledServersInPod()
0xefb  dup
0xefc  ldstr    aServers// "servers"
0xf01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf06  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::.ctor()
0xf0b  stloc.0
0xf0c  stloc.2
0xf0d  ldc.i4.0
0xf0e  stloc.3
0xf0f  br.s     loc_F7C
0xf11  ldloc.2
0xf12  ldloc.3
0xf13  ldelem.ref
0xf14  stloc.s  4
0xf16  ldloc.s  4
0xf18  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Roles()
0xf1d  ldc.i4   0x1000000
0xf22  and
0xf23  ldc.i4   0x1000000
0xf28  bne.un.s loc_F78
0xf2a  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xf2f  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xf34  ldc.i4.2
0xf35  bne.un.s loc_F4F
0xf37  ldloc.s  4
0xf39  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_DatacenterId()
0xf3e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0xf43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0xf48  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf4d  brtrue.s loc_F78
0xf4f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf54  ldc.i4.s 0x23
0xf56  ldstr    aSandboxhostman_24// "SandboxHostManager.InitializeInternal: "...
0xf5b  ldc.i4.1
0xf5c  newarr   [mscorlib]System.Object
0xf61  dup
0xf62  ldc.i4.0
0xf63  ldloc.s  4
0xf65  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0xf6a  stelem.ref
0xf6b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf70  ldloc.0
0xf71  ldloc.s  4
0xf73  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::Add(var<u1>)
0xf78  ldloc.3
0xf79  ldc.i4.1
0xf7a  add
0xf7b  stloc.3
0xf7c  ldloc.3
0xf7d  ldloc.2
0xf7e  ldlen
0xf7f  conv.i4
0xf80  blt.s    loc_F11
0xf82  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf87  ldc.i4.s 0x23
0xf89  ldstr    aSandboxhostman_25// "SandboxHostManager.InitializeInternal: "...
0xf8e  ldc.i4.1
0xf8f  newarr   [mscorlib]System.Object
0xf94  dup
0xf95  ldc.i4.0
0xf96  ldloc.0
0xf97  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::get_Count()
0xf9c  box      [mscorlib]System.Int32
0xfa1  stelem.ref
0xfa2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfa7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::.ctor()
0xfac  stloc.1
0xfad  ldloc.0
0xfae  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::GetEnumerator()
0xfb3  stloc.s  5
0xfb5  br.s     loc_FFE
0xfb7  ldloca.s 5
0xfb9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::get_Current()
0xfbe  stloc.s  6
0xfc0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xfc5  ldc.i4.s 0x23
0xfc7  ldstr    aSandboxhostman_26// "SandboxHostManager.InitializeInternal: "...
0xfcc  ldc.i4.1
0xfcd  newarr   [mscorlib]System.Object
0xfd2  dup
0xfd3  ldc.i4.0
0xfd4  ldloc.s  6
0xfd6  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_FullName()
0xfdb  stelem.ref
0xfdc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfe1  ldloc.s  6
0xfe3  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0xfe8  ldloc.s  6
0xfea  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_FullName()
0xfef  newobj   instance void class [mscorlib]System.Tuple`2<string, string>::.ctor(var<u1>, !!T0)
0xff4  stloc.s  7
0xff6  ldloc.1
0xff7  ldloc.s  7
0xff9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>>::Add(var<u1>)
0xffe  ldloca.s 5
0x1000  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::MoveNext()
0x1005  brtrue.s loc_FB7
0x1007  leave.s  loc_1017
0x1009  ldloca.s 5
0x100b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>
0x1011  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1016  endfinally
0x1017  ldloc.1
0x1018  call     void Microsoft.Crm.Sandbox.SandboxHostManager::UpdateHostNames(class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, string>> newHostList)
0x101d  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_started
0x1022  brtrue.s loc_107C
0x1024  ldloc.0
0x1025  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::get_Count()
0x102a  ldc.i4.0
0x102b  ble.s    loc_107C
0x102d  ldc.i4.1
0x102e  stsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_started
0x1033  call     void Microsoft.Crm.Sandbox.SandboxHostManager::Start()
0x1038  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x103d  ldc.i4.s 0x23
0x103f  ldstr    aSandboxhostman_27// "SandboxHostManager.InitializeInternal: "...
0x1044  ldc.i4.3
0x1045  newarr   [mscorlib]System.Object
0x104a  dup
0x104b  ldc.i4.0
0x104c  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHostManager::_started
0x1051  box      [mscorlib]System.Boolean
0x1056  stelem.ref
0x1057  dup
0x1058  ldc.i4.1
0x1059  ldloc.0
0x105a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData>::get_Count()
0x105f  box      [mscorlib]System.Int32
0x1064  stelem.ref
0x1065  dup
0x1066  ldc.i4.2
0x1067  call     bool Microsoft.Crm.Sandbox.SandboxSdkListener::get_ListenerStarted()
0x106c  box      [mscorlib]System.Boolean
0x1071  stelem.ref
0x1072  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1077  call     void Microsoft.Crm.Sandbox.SandboxSdkListener::StartListenerStarterThread()
0x107c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1081  ldc.i4.s 0x23
0x1083  ldstr    aSandboxhostman_28// "SandboxHostManager.InitializeInternal: "...
0x1088  ldc.i4.0
0x1089  newarr   [mscorlib]System.Object
0x108e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1093  ret
```
