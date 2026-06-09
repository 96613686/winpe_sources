# Microsoft.Crm.Sandbox.SandboxCallbackService::GenericCallBack

- ea: `0x1f70`
- end: `0x2010`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::GenericCallBack`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1f70`
- `0x2010`
- `0x2030`
- `0x22d0`

## string_xrefs

- `0x1f72`: `SandboxCallbackService.GenericCallBack`
- `0x1fca`: `SandboxCallbackServices.GenericCallBack: _sdkContext.UserId: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1f70  ldnull
0x1f71  stloc.0
0x1f72  ldstr    aSandboxcallbac// "SandboxCallbackService.GenericCallBack"
0x1f77  ldarg.0
0x1f78  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x1f7d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x1f82  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0x1f87  stloc.1
0x1f88  ldloc.1
0x1f89  ldarg.0
0x1f8a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x1f8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1f94  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid)
0x1f99  ldarg.0
0x1f9a  call     instance class Microsoft.Crm.Sandbox.SandboxSdkClient Microsoft.Crm.Sandbox.SandboxCallbackService::Initialize()
0x1f9f  stloc.0
0x1fa0  ldloc.1
0x1fa1  ldloc.0
0x1fa2  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Destination()
0x1fa7  ldarg.0
0x1fa8  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x1fad  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x1fb2  ldarg.0
0x1fb3  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxCallbackService::workerCounter
0x1fb8  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Call(string, int32, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter)
0x1fbd  ldarg.0
0x1fbe  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x1fc3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x1fc8  ldc.i4.s 0x21
0x1fca  ldstr    aSandboxcallbac_0// "SandboxCallbackServices.GenericCallBack"...
0x1fcf  ldc.i4.1
0x1fd0  newarr   [mscorlib]System.Object
0x1fd5  dup
0x1fd6  ldc.i4.0
0x1fd7  ldarg.0
0x1fd8  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxCallbackService::sdkContext
0x1fdd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_UserId()
0x1fe2  box      [mscorlib]System.Guid
0x1fe7  stelem.ref
0x1fe8  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fed  ldarg.1
0x1fee  ldloc.0
0x1fef  callvirt instance var<u1> class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxSdkClient, mvar<u1>>::Invoke(void)
0x1ff4  ldloc.1
0x1ff5  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodReturn()
0x1ffa  stloc.2
0x1ffb  leave.s  loc_200E
0x1ffd  stloc.3
0x1ffe  ldloc.1
0x1fff  ldloc.3
0x2000  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadReturn(class [mscorlib]System.Exception)
0x2005  ldarg.0
0x2006  ldloc.3
0x2007  ldloc.0
0x2008  call     instance class [mscorlib]System.Exception Microsoft.Crm.Sandbox.SandboxCallbackService::ProcessException(class [mscorlib]System.Exception e, class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x200d  throw
0x200e  ldloc.2
0x200f  ret
```
