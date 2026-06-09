# Microsoft.Crm.Sandbox.SandboxOrganizationService::RetrieveClaimAssertions

- ea: `0x2780`
- end: `0x287b`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationService::RetrieveClaimAssertions`
- size: `251`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x2010`
- `0x2030`
- `0x22d0`
- `0x2780`

## string_xrefs

- `0x2787`: `SandboxOrganizationServices.RetrieveClaimAssertions`
- `0x27c8`: `SandboxOrganizationServices.RetrieveClaimAssertions.client_Initialize()`
- `0x2807`: `SandboxOrganizationServices.RetrieveClaimAssertions.wcfCall`

## pseudocode

```c

```

## disassembly

```asm
0x2780  ldarg.3
0x2781  isinst   [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings
0x2786  stloc.0
0x2787  ldstr    aSandboxorganiz_10// "SandboxOrganizationServices.RetrieveCla"...
0x278c  ldloc.0
0x278d  ldc.i4.0
0x278e  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceContext::.ctor(string, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTraceSettings, bool)
0x2793  stloc.1
0x2794  ldnull
0x2795  stloc.2
0x2796  ldstr    aIsandboxsdklis_1// "ISandboxSdkListener.RetrieveClaimAssert"...
0x279b  ldarg.0
0x279c  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x27a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_CorrelationId()
0x27a6  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::.ctor(string, valuetype [mscorlib]System.Guid)
0x27ab  stloc.3
0x27ac  ldloc.3
0x27ad  ldarg.0
0x27ae  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x27b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x27b8  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::AdditionalData(valuetype [mscorlib]System.Guid)
0x27bd  ldc.i4.1
0x27be  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x27c3  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x27c8  ldstr    aSandboxorganiz_11// "SandboxOrganizationServices.RetrieveCla"...
0x27cd  ldc.i4.3
0x27ce  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x27d3  stloc.s  5
0x27d5  ldarg.0
0x27d6  call     instance class Microsoft.Crm.Sandbox.SandboxSdkClient Microsoft.Crm.Sandbox.SandboxCallbackService::Initialize()
0x27db  stloc.2
0x27dc  leave.s  loc_27EA
0x27de  ldloc.s  5
0x27e0  brfalse.s loc_27E9
0x27e2  ldloc.s  5
0x27e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x27e9  endfinally
0x27ea  ldloc.3
0x27eb  ldloc.2
0x27ec  callvirt instance string class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Destination()
0x27f1  ldarg.0
0x27f2  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x27f7  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_Depth()
0x27fc  ldarg.0
0x27fd  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter Microsoft.Crm.Sandbox.SandboxCallbackService::workerCounter
0x2802  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::Call(string, int32, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxRequestCounter)
0x2807  ldstr    aSandboxorganiz_12// "SandboxOrganizationServices.RetrieveCla"...
0x280c  ldc.i4.3
0x280d  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPerformanceContext::.ctor(string, valuetype [System]System.Diagnostics.TraceLevel)
0x2812  stloc.s  5
0x2814  ldloc.2
0x2815  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Proxy()
0x281a  ldarg.0
0x281b  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallbackService::callInfo
0x2820  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x2825  ldarg.0
0x2826  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxCallbackService::sdkContext
0x282b  ldarg.0
0x282c  ldfld    string Microsoft.Crm.Sandbox.SandboxCallbackService::assemblyName
0x2831  ldarg.1
0x2832  ldarg.2
0x2833  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener::RetrieveClaimAssertions(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext, string, class [System]System.Uri, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x2838  stloc.s  4
0x283a  leave.s  loc_2848
0x283c  ldloc.s  5
0x283e  brfalse.s loc_2847
0x2840  ldloc.s  5
0x2842  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2847  endfinally
0x2848  ldloc.3
0x2849  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::GoodReturn()
0x284e  ldloc.s  4
0x2850  stloc.s  6
0x2852  leave.s  loc_2878
0x2854  stloc.s  7
0x2856  ldloc.3
0x2857  ldloc.s  7
0x2859  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTracker::BadReturn(class [mscorlib]System.Exception)
0x285e  ldarg.0
0x285f  ldloc.s  7
0x2861  ldloc.2
0x2862  call     instance class [mscorlib]System.Exception Microsoft.Crm.Sandbox.SandboxCallbackService::ProcessException(class [mscorlib]System.Exception e, class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x2867  throw
0x2868  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x286d  endfinally
0x286e  ldloc.1
0x286f  brfalse.s loc_2877
0x2871  ldloc.1
0x2872  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2877  endfinally
0x2878  ldloc.s  6
0x287a  ret
```
