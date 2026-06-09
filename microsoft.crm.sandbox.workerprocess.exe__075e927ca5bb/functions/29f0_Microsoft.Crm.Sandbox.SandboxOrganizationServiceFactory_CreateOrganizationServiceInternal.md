# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationServiceInternal

- ea: `0x29f0`
- end: `0x2ab1`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationServiceInternal`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x29d0`

## callees

- `0x2440`
- `0x29f0`
- `0x2b60`
- `0x2b80`

## string_xrefs

- `0x29f7`: `SandboxOrganizationServiceFactory.CreateOrganizationServiceInternal`

## pseudocode

```c

```

## disassembly

```asm
0x29f0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29f5  ldc.i4.s 0x21
0x29f7  ldstr    aSandboxorganiz_17// "SandboxOrganizationServiceFactory.Creat"...
0x29fc  ldc.i4.0
0x29fd  newarr   [mscorlib]System.Object
0x2a02  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a07  ldarg.0
0x2a08  ldfld    bool Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_blocked
0x2a0d  brfalse.s loc_2A1A
0x2a0f  ldstr    aBlocked// "blocked"
0x2a14  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxFault::GetFaultException(string)
0x2a19  throw
0x2a1a  ldarg.0
0x2a1b  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::get_Context()
0x2a20  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext)
0x2a25  stloc.0
0x2a26  ldloc.0
0x2a27  ldarg.1
0x2a28  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::set_UserId(valuetype [mscorlib]System.Guid)
0x2a2d  ldarg.0
0x2a2e  ldfld    string Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_assemblyName
0x2a33  ldarg.0
0x2a34  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_callInfo
0x2a39  ldarg.0
0x2a3a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::get_Context()
0x2a3f  ldloc.0
0x2a40  ldarg.0
0x2a41  call     instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::get_WorkerCounter()
0x2a46  ldarg.0
0x2a47  ldfld    int32 Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::leaseTime
0x2a4c  newobj   instance void Microsoft.Crm.Sandbox.SandboxOrganizationService::.ctor(string assemblyName, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo callInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext sdkContext, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter workerCounter, int32 leaseTime)
0x2a51  stloc.1
0x2a52  ldarg.0
0x2a53  ldfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_xrmServicesLock
0x2a58  stloc.2
0x2a59  ldc.i4.0
0x2a5a  stloc.3
0x2a5b  ldloc.2
0x2a5c  ldloca.s 3
0x2a5e  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2a63  ldarg.0
0x2a64  ldfld    bool Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_blocked
0x2a69  brfalse.s loc_2A76
0x2a6b  ldstr    aBlocked// "blocked"
0x2a70  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxFault::GetFaultException(string)
0x2a75  throw
0x2a76  ldarg.0
0x2a77  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService> Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_xrmServices
0x2a7c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService>::get_Count()
0x2a81  ldc.i4.s 0x64
0x2a83  ble.s    loc_2A97
0x2a85  ldarg.0
0x2a86  ldc.i4.1
0x2a87  stfld    bool Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_blocked
0x2a8c  ldstr    aExceeded// "exceeded"
0x2a91  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxFault::GetFaultException(string)
0x2a96  throw
0x2a97  ldarg.0
0x2a98  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService> Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_xrmServices
0x2a9d  ldloc.1
0x2a9e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService>::Add(var<u1>)
0x2aa3  leave.s  loc_2AAF
0x2aa5  ldloc.3
0x2aa6  brfalse.s loc_2AAE
0x2aa8  ldloc.2
0x2aa9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2aae  endfinally
0x2aaf  ldloc.1
0x2ab0  ret
```
