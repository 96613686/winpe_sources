# Microsoft.Crm.Sandbox.SandboxCallbackService::.ctor

- ea: `0x1ec0`
- end: `0x1f63`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::.ctor`
- size: `163`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3e0`
- `0x810`
- `0xb50`
- `0x2440`
- `0x4930`

## callees

- `0x2330`
- `0x2bb0`
- `0x2d10`

## pseudocode

```c

```

## disassembly

```asm
0x1ec0  ldarg.0
0x1ec1  ldarg.s  6
0x1ec3  call     instance void Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::.ctor(int32 leaseTime)
0x1ec8  ldarg.2
0x1ec9  ldstr    aCallinfo// "callInfo"
0x1ece  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ed3  ldarg.2
0x1ed4  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x1ed9  ldstr    aCallinfoParent// "callInfo.ParentCallInfo"
0x1ede  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ee3  ldarg.3
0x1ee4  ldstr    aContext// "context"
0x1ee9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1eee  ldarg.s  4
0x1ef0  ldstr    aSdkcontext// "sdkContext"
0x1ef5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1efa  ldarg.s  5
0x1efc  ldstr    aWorkercounter// "workerCounter"
0x1f01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1f06  ldarg.1
0x1f07  ldstr    aAssemblyname// "assemblyName"
0x1f0c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1f11  ldarg.0
0x1f12  ldarg.3
0x1f13  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::_context
0x1f18  ldarg.0
0x1f19  ldarg.s  5
0x1f1b  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxCallbackService::workerCounter
0x1f20  ldarg.0
0x1f21  ldarg.1
0x1f22  stfld    string Microsoft.Crm.Sandbox.SandboxCallbackService::assemblyName
0x1f27  ldarg.0
0x1f28  ldarg.2
0x1f29  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallbackService::callInfo
0x1f2e  ldarg.0
0x1f2f  ldarg.s  4
0x1f31  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxCallbackService::sdkContext
0x1f36  ldarg.0
0x1f37  ldc.i4.0
0x1f38  stfld    bool Microsoft.Crm.Sandbox.SandboxCallbackService::blocked
0x1f3d  newobj   instance void Microsoft.Crm.Sandbox.SandboxSdkClient::.ctor()
0x1f42  stloc.0
0x1f43  ldloc.0
0x1f44  ldc.i4.1
0x1f45  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::set_DestinationOnly(bool)
0x1f4a  ldloc.0
0x1f4b  ldarg.2
0x1f4c  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x1f51  callvirt instance void Microsoft.Crm.Sandbox.SandboxSdkClient::Start(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo)
0x1f56  ldarg.0
0x1f57  ldloc.0
0x1f58  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_UriText()
0x1f5d  stfld    string Microsoft.Crm.Sandbox.SandboxCallbackService::listenerUri
0x1f62  ret
```
