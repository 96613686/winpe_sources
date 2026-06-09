# Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::.ctor

- ea: `0x5500`
- end: `0x5583`
- name: `Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::.ctor`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4000`
- `0x4360`
- `0x4b40`

## callees

- `0x5500`

## pseudocode

```c

```

## disassembly

```asm
0x5500  ldarg.0
0x5501  call     instance void [mscorlib]System.Object::.ctor()
0x5506  ldarg.0
0x5507  ldarg.1
0x5508  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_context
0x550d  ldarg.0
0x550e  ldarg.2
0x550f  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_sdkContext
0x5514  ldarg.0
0x5515  ldarg.3
0x5516  stfld    bool Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_forReports
0x551b  call     bool [System.Web]System.Web.Hosting.HostingEnvironment::get_IsHosted()
0x5520  brfalse.s loc_5582
0x5522  ldsfld   string [mscorlib]System.String::Empty
0x5527  ldsfld   string [mscorlib]System.String::Empty
0x552c  ldnull
0x552d  newobj   instance void [System.Web]System.Web.Hosting.SimpleWorkerRequest::.ctor(string, string, class [mscorlib]System.IO.TextWriter)
0x5532  newobj   instance void [System.Web]System.Web.HttpContext::.ctor(class [System.Web]System.Web.HttpWorkerRequest)
0x5537  call     void [System.Web]System.Web.HttpContext::set_Current(class [System.Web]System.Web.HttpContext)
0x553c  call     class [mscorlib]System.Security.Principal.WindowsIdentity [mscorlib]System.Security.Principal.WindowsIdentity::GetCurrent()
0x5541  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0x5546  stloc.0
0x5547  ldloc.0
0x5548  ldarg.1
0x5549  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x554e  call     void [Microsoft.Crm.Core]IdentityExtensions::SetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x5553  ldloc.0
0x5554  ldarg.0
0x5555  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_sdkContext
0x555a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_InitiatingUserId()
0x555f  call     bool [Microsoft.Crm.Core]IdentityExtensions::DoRecognizeUser(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x5564  brfalse.s loc_5577
0x5566  ldloc.0
0x5567  ldarg.0
0x5568  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_sdkContext
0x556d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_InitiatingUserId()
0x5572  call     void [Microsoft.Crm.Core]IdentityExtensions::SetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x5577  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x557c  ldloc.0
0x557d  callvirt instance void [System.Web]System.Web.HttpContext::set_User(class [mscorlib]System.Security.Principal.IPrincipal)
0x5582  ret
```
