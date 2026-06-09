# Microsoft.Crm.Sandbox.SandboxHost::Ping

- ea: `0x3e00`
- end: `0x408a`
- name: `Microsoft.Crm.Sandbox.SandboxHost::Ping`
- size: `650`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x3210`
- `0x3940`
- `0x3d00`
- `0x3e00`
- `0x49d0`
- `0x4e20`
- `0x6300`
- `0x6310`
- `0x6340`

## string_xrefs

- `0x3f5c`: `CrmScaleGroupProvisioningService`
- `0x3fe0`: `SandboxHost.Ping: hostSidSddlForm: {0}`
- `0x3ffd`: `_serviceAccountSidSddlForm`
- `0x400e`: `SandboxHost.Ping: _serviceAccountSidSddlForm: {0}`
- `0x4031`: `hostSidSddlForm`

## pseudocode

```c

```

## disassembly

```asm
0x3e00  ldstr    aSandboxhostPin// "SandboxHost.Ping"
0x3e05  ldarg.1
0x3e06  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_OrgTraceCategory()
0x3e0b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3e10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3e15  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3e1a  ldarg.1
0x3e1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x3e20  ldarg.1
0x3e21  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ActivityId()
0x3e26  stloc.1
0x3e27  ldloca.s 1
0x3e29  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x3e2e  ldc.i4.0
0x3e2f  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x3e34  stloc.0
0x3e35  ldarg.s  6
0x3e37  ldnull
0x3e38  stind.ref
0x3e39  ldarg.s  7
0x3e3b  ldnull
0x3e3c  stind.ref
0x3e3d  ldstr    aIsandboxhostPi// "ISandboxHost.Ping"
0x3e42  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string)
0x3e47  stloc.2
0x3e48  call     void Microsoft.Crm.Sandbox.SandboxHost::AuthenticateCaller()
0x3e4d  ldarg.1
0x3e4e  ldstr    aCallinfo// "callInfo"
0x3e53  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3e58  ldsflda  int32 Microsoft.Crm.Sandbox.SandboxHost::_pingCount
0x3e5d  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0x3e62  ldc.i4.1
0x3e63  sub
0x3e64  stloc.3
0x3e65  ldloc.3
0x3e66  ldc.i4.3
0x3e67  bge.s    loc_3E9D
0x3e69  ldarg.1
0x3e6a  ldstr    aIsandboxhostPi_0// "ISandboxHost.Ping: "
0x3e6f  ldloc.3
0x3e70  box      [mscorlib]System.Int32
0x3e75  call     string [mscorlib]System.String::Concat(object, object)
0x3e7a  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::Trace(string)
0x3e7f  ldloc.2
0x3e80  ldstr    aIsandboxhostPi_0// "ISandboxHost.Ping: "
0x3e85  ldloc.3
0x3e86  box      [mscorlib]System.Int32
0x3e8b  call     string [mscorlib]System.String::Concat(object, object)
0x3e90  ldarg.1
0x3e91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x3e96  ldarg.1
0x3e97  ldc.i4.0
0x3e98  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Enter(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, int32)
0x3e9d  ldarg.1
0x3e9e  call     void Microsoft.Crm.Sandbox.SandboxClientTracker::ClientPing(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo info)
0x3ea3  ldarg.2
0x3ea4  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxHostConfiguration Microsoft.Crm.Sandbox.SandboxHost::_hostConfiguration
0x3ea9  ldarg.3
0x3eaa  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::_workerConfiguration
0x3eaf  ldarg.s  4
0x3eb1  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.Sandbox.SandboxHost::_sandboxAdditionalInfo
0x3eb6  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxHost::_exceptionConverter
0x3ebb  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration Microsoft.Crm.Sandbox.SandboxHost::_workerConfiguration
0x3ec0  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter::Update(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerConfiguration)
0x3ec5  call     bool Microsoft.Crm.Sandbox.SandboxWorkerManager::get_DrawbridgeEnabled()
0x3eca  brtrue.s loc_3EDF
0x3ecc  ldarg.1
0x3ecd  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x3ed2  brfalse.s loc_3EDF
0x3ed4  ldarg.1
0x3ed5  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x3eda  call     void Microsoft.Crm.Sandbox.SandboxWorkerManager::set_DrawbridgeEnabled(bool value)
0x3edf  ldloc.3
0x3ee0  brtrue.s loc_3EE7
0x3ee2  call     void Microsoft.Crm.Sandbox.SandboxAssemblyManager::UpdateTimer()
0x3ee7  ldarg.1
0x3ee8  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x3eed  call     bool Microsoft.Crm.Sandbox.SandboxWorkerManager::Started(bool useDrawbridge)
0x3ef2  brfalse.s loc_3EFC
0x3ef4  ldc.i4.3
0x3ef5  stsfld   valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxHost::_sandboxStatus
0x3efa  br.s     loc_3F02
0x3efc  ldc.i4.2
0x3efd  stsfld   valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxHost::_sandboxStatus
0x3f02  ldsfld   bool Microsoft.Crm.Sandbox.SandboxHost::_shutdownFlag
0x3f07  brfalse.s loc_3F0F
0x3f09  ldc.i4.5
0x3f0a  stsfld   valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxHost::_sandboxStatus
0x3f0f  ldloc.3
0x3f10  ldc.i4.3
0x3f11  bge.s    loc_3F19
0x3f13  ldloc.2
0x3f14  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodExit()
0x3f19  ldsfld   object Microsoft.Crm.Sandbox.SandboxHost::_queueLock
0x3f1e  stloc.s  4
0x3f20  ldc.i4.0
0x3f21  stloc.s  5
0x3f23  ldloc.s  4
0x3f25  ldloca.s 5
0x3f27  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x3f2c  ldarg.s  5
0x3f2e  brfalse.s loc_3F56
0x3f30  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxHost::_remoteSettings
0x3f35  brfalse.s loc_3F45
0x3f37  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxHost::_remoteSettings
0x3f3c  ldarg.s  5
0x3f3e  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::Updated(class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings)
0x3f43  brfalse.s loc_3F56
0x3f45  ldarg.s  5
0x3f47  stsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxHost::_remoteSettings
0x3f4c  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings Microsoft.Crm.Sandbox.SandboxHost::_remoteSettings
0x3f51  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTraceRemoteSettings::ResetTrace()
0x3f56  ldarg.1
0x3f57  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ProcessName()
0x3f5c  ldstr    aCrmscalegroupp// "CrmScaleGroupProvisioningService"
0x3f61  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3f66  brfalse.s loc_3FA0
0x3f68  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>> Microsoft.Crm.Sandbox.SandboxHost::_workerExecutionRecordQueueDictionary
0x3f6d  ldarg.1
0x3f6e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ScaleGroupId()
0x3f73  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>>::ContainsKey(var<u1>)
0x3f78  brfalse.s loc_3FA0
0x3f7a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>> Microsoft.Crm.Sandbox.SandboxHost::_workerExecutionRecordQueueDictionary
0x3f7f  ldarg.1
0x3f80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ScaleGroupId()
0x3f85  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>>::get_Item(void)
0x3f8a  stloc.s  6
0x3f8c  ldloc.s  6
0x3f8e  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::get_Count()
0x3f93  ldc.i4.0
0x3f94  ble.s    loc_3FA0
0x3f96  ldarg.s  6
0x3f98  ldloc.s  6
0x3f9a  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord>::Dequeue()
0x3f9f  stind.ref
0x3fa0  leave.s  loc_3FAE
0x3fa2  ldloc.s  5
0x3fa4  brfalse.s loc_3FAD
0x3fa6  ldloc.s  4
0x3fa8  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x3fad  endfinally
0x3fae  call     bool Microsoft.Crm.Sandbox.SandboxHost::get_IsNetworkServiceAccount()
0x3fb3  brfalse.s loc_3FF8
0x3fb5  ldarg.1
0x3fb6  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_MachineName()
0x3fbb  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x3fc0  call     string [mscorlib]System.Environment::get_MachineName()
0x3fc5  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x3fca  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3fcf  brfalse.s loc_3FF8
0x3fd1  ldarg.s  7
0x3fd3  call     string Microsoft.Crm.Sandbox.SandboxHost::get_ComputerAccountSidSddlForm()
0x3fd8  stind.ref
0x3fd9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3fde  ldc.i4.s 0x21
0x3fe0  ldstr    aSandboxhostPin_0// "SandboxHost.Ping: hostSidSddlForm: {0}"
0x3fe5  ldc.i4.1
0x3fe6  newarr   [mscorlib]System.Object
0x3feb  dup
0x3fec  ldc.i4.0
0x3fed  ldarg.s  7
0x3fef  ldind.ref
0x3ff0  stelem.ref
0x3ff1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3ff6  br.s     loc_402E
0x3ff8  ldsfld   string Microsoft.Crm.Sandbox.SandboxHost::_serviceAccountSidSddlForm
0x3ffd  ldstr    aServiceaccount// "_serviceAccountSidSddlForm"
0x4002  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4007  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x400c  ldc.i4.s 0x21
0x400e  ldstr    aSandboxhostPin_1// "SandboxHost.Ping: _serviceAccountSidSdd"...
0x4013  ldc.i4.1
0x4014  newarr   [mscorlib]System.Object
0x4019  dup
0x401a  ldc.i4.0
0x401b  ldsfld   string Microsoft.Crm.Sandbox.SandboxHost::_serviceAccountSidSddlForm
0x4020  stelem.ref
0x4021  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4026  ldarg.s  7
0x4028  ldsfld   string Microsoft.Crm.Sandbox.SandboxHost::_serviceAccountSidSddlForm
0x402d  stind.ref
0x402e  ldarg.s  7
0x4030  ldind.ref
0x4031  ldstr    aHostsidsddlfor// "hostSidSddlForm"
0x4036  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x403b  ldsfld   valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxHost::_sandboxStatus
0x4040  stloc.s  7
0x4042  leave.s  loc_4087
0x4044  stloc.s  8
0x4046  ldloc.2
0x4047  ldloc.s  8
0x4049  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadExit(class [mscorlib]System.Exception)
0x404e  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxExceptionConverter Microsoft.Crm.Sandbox.SandboxHost::_exceptionConverter
0x4053  ldloc.s  8
0x4055  ldc.i4.1
0x4056  ldloca.s 9
0x4058  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.ExceptionConverter::TryConvertToFaultException(class [mscorlib]System.Exception, bool, class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>&)
0x405d  brfalse.s loc_4062
0x405f  ldloc.s  9
0x4061  throw
0x4062  ldloc.s  8
0x4064  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4069  ldc.i4.s 0x21
0x406b  ldstr    aUnexpectedExce// "UNEXPECTED: exception not converted"
0x4070  ldc.i4.0
0x4071  newarr   [mscorlib]System.Object
0x4076  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x407b  rethrow
0x407d  ldloc.0
0x407e  brfalse.s loc_4086
0x4080  ldloc.0
0x4081  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4086  endfinally
0x4087  ldloc.s  7
0x4089  ret
```
