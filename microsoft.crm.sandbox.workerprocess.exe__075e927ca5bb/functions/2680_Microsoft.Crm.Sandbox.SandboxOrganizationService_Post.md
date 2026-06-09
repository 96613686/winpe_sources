# Microsoft.Crm.Sandbox.SandboxOrganizationService::Post

- ea: `0x2680`
- end: `0x277c`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationService::Post`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x2010`
- `0x2030`
- `0x22d0`
- `0x2680`

## string_xrefs

- `0x2688`: `SandboxOrganizationServices.Post`
- `0x26c9`: `SandboxOrganizationServices.Post.client_Initialize()`
- `0x2708`: `SandboxOrganizationServices.Post.wcfCall`

## pseudocode

```c

```

## disassembly

```asm
0x2680  ldarg.s  4
0x2682  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings
0x2687  stloc.0
0x2688  ldstr    aSandboxorganiz_7// "SandboxOrganizationServices.Post"
0x268d  ldloc.0
0x268e  ldc.i4.0
0x268f  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings, bool)
0x2694  stloc.1
0x2695  ldnull
0x2696  stloc.2
0x2697  ldstr    aIsandboxsdklis_0// "ISandboxSdkListener.Post"
0x269c  ldarg.0
0x269d  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x26a2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x26a7  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0x26ac  stloc.3
0x26ad  ldloc.3
0x26ae  ldarg.0
0x26af  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x26b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x26b9  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid)
0x26be  ldc.i4.1
0x26bf  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x26c4  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x26c9  ldstr    aSandboxorganiz_8// "SandboxOrganizationServices.Post.client"...
0x26ce  ldc.i4.3
0x26cf  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x26d4  stloc.s  5
0x26d6  ldarg.0
0x26d7  call     instance class Microsoft.Crm.Sandbox.SandboxSdkClient Microsoft.Crm.Sandbox.SandboxCallbackService::Initialize()
0x26dc  stloc.2
0x26dd  leave.s  loc_26EB
0x26df  ldloc.s  5
0x26e1  brfalse.s loc_26EA
0x26e3  ldloc.s  5
0x26e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26ea  endfinally
0x26eb  ldloc.3
0x26ec  ldloc.2
0x26ed  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Destination()
0x26f2  ldarg.0
0x26f3  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x26f8  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x26fd  ldarg.0
0x26fe  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxCallbackService::workerCounter
0x2703  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Call(string, int32, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter)
0x2708  ldstr    aSandboxorganiz_9// "SandboxOrganizationServices.Post.wcfCal"...
0x270d  ldc.i4.3
0x270e  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x2713  stloc.s  5
0x2715  ldloc.2
0x2716  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Proxy()
0x271b  ldarg.0
0x271c  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallbackService::callInfo
0x2721  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x2726  ldarg.0
0x2727  ldfld    string Microsoft.Crm.Sandbox.SandboxCallbackService::assemblyName
0x272c  ldarg.1
0x272d  ldarg.2
0x272e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x2733  ldarg.3
0x2734  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener::Post(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext)
0x2739  stloc.s  4
0x273b  leave.s  loc_2749
0x273d  ldloc.s  5
0x273f  brfalse.s loc_2748
0x2741  ldloc.s  5
0x2743  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2748  endfinally
0x2749  ldloc.3
0x274a  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodReturn()
0x274f  ldloc.s  4
0x2751  stloc.s  6
0x2753  leave.s  loc_2779
0x2755  stloc.s  7
0x2757  ldloc.3
0x2758  ldloc.s  7
0x275a  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadReturn(class [mscorlib]System.Exception)
0x275f  ldarg.0
0x2760  ldloc.s  7
0x2762  ldloc.2
0x2763  call     instance class [mscorlib]System.Exception Microsoft.Crm.Sandbox.SandboxCallbackService::ProcessException(class [mscorlib]System.Exception e, class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x2768  throw
0x2769  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x276e  endfinally
0x276f  ldloc.1
0x2770  brfalse.s loc_2778
0x2772  ldloc.1
0x2773  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2778  endfinally
0x2779  ldloc.s  6
0x277b  ret
```
