# Microsoft.Crm.Sandbox.SandboxCallbackService::InitializeInternal

- ea: `0x2240`
- end: `0x22c2`
- name: `Microsoft.Crm.Sandbox.SandboxCallbackService::InitializeInternal`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2010`

## callees

- `0x2240`
- `0x22d0`

## string_xrefs

- `0x224d`: `SandboxCallbackService.InitializeInternal: {0}`
- `0x22a7`: `SandboxOrganizationService.InitializeInternal: obtained new client: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2240  ldarg.0
0x2241  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x2246  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x224b  ldc.i4.s 0x21
0x224d  ldstr    aSandboxcallbac_8// "SandboxCallbackService.InitializeIntern"...
0x2252  ldc.i4.1
0x2253  newarr   [mscorlib]System.Object
0x2258  dup
0x2259  ldc.i4.0
0x225a  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x225f  callvirt instance string [mscorlib]System.AppDomain::get_FriendlyName()
0x2264  stelem.ref
0x2265  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x226a  ldarg.0
0x226b  ldfld    bool Microsoft.Crm.Sandbox.SandboxCallbackService::blocked
0x2270  brfalse.s loc_227D
0x2272  ldstr    aBlocked// "blocked"
0x2277  call     class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxFault::GetFaultException(string)
0x227c  throw
0x227d  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::get_Instance()
0x2282  ldarg.0
0x2283  ldfld    string Microsoft.Crm.Sandbox.SandboxCallbackService::listenerUri
0x2288  ldarg.0
0x2289  ldftn    instance class Microsoft.Crm.Sandbox.SandboxSdkClient Microsoft.Crm.Sandbox.SandboxCallbackService::GetDefaultSandboxClientInstance()
0x228f  newobj   instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1/GetDefaultSandboxSdkClientInstance<class Microsoft.Crm.Sandbox.SandboxSdkClient>::.ctor(object, native int)
0x2294  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::GetSandboxClient(!!T0, string)
0x2299  stloc.0
0x229a  ldarg.0
0x229b  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxCallbackService::get_Context()
0x22a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x22a5  ldc.i4.s 0x21
0x22a7  ldstr    aSandboxorganiz// "SandboxOrganizationService.InitializeIn"...
0x22ac  ldc.i4.1
0x22ad  newarr   [mscorlib]System.Object
0x22b2  dup
0x22b3  ldc.i4.0
0x22b4  ldarg.0
0x22b5  ldfld    string Microsoft.Crm.Sandbox.SandboxCallbackService::listenerUri
0x22ba  stelem.ref
0x22bb  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22c0  ldloc.0
0x22c1  ret
```
