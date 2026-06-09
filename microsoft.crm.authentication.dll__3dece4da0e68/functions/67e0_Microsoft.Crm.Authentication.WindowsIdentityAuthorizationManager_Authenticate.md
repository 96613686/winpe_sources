# Microsoft.Crm.Authentication.WindowsIdentityAuthorizationManager::Authenticate

- ea: `0x67e0`
- end: `0x68d4`
- name: `Microsoft.Crm.Authentication.WindowsIdentityAuthorizationManager::Authenticate`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x6730`

## callees

- `0x1f20`
- `0x6710`
- `0x67e0`
- `0x7780`

## string_xrefs

- `0x68c8`: `WindowsIdentityAuthorizationManager.Authenticate(): ClaimsAuthorizationManager.CheckAccess() returned false`

## pseudocode

```c

```

## disassembly

```asm
0x67e0  call     class [System]System.Uri Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::get_CurrentOperationRequestUri()
0x67e5  stloc.0
0x67e6  ldarg.1
0x67e7  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.ServiceModel]System.ServiceModel.OperationContext::get_ClaimsPrincipal()
0x67ec  stloc.1
0x67ed  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x67f2  brtrue.s loc_680E
0x67f4  ldsfld   string [mscorlib]System.String::Empty
0x67f9  ldsfld   string [mscorlib]System.String::Empty
0x67fe  ldnull
0x67ff  newobj   instance void [System.Web]System.Web.Hosting.SimpleWorkerRequest::.ctor(string, string, class [mscorlib]System.IO.TextWriter)
0x6804  newobj   instance void [System.Web]System.Web.HttpContext::.ctor(class [System.Web]System.Web.HttpWorkerRequest)
0x6809  call     void [System.Web]System.Web.HttpContext::set_Current(class [System.Web]System.Web.HttpContext)
0x680e  ldloc.1
0x680f  brtrue.s loc_6841
0x6811  ldarg.1
0x6812  callvirt instance class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.OperationContext::get_ServiceSecurityContext()
0x6817  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_PrimaryIdentity()
0x681c  brfalse.s loc_6841
0x681e  ldarg.1
0x681f  callvirt instance class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.OperationContext::get_ServiceSecurityContext()
0x6824  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_PrimaryIdentity()
0x6829  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x682e  brfalse.s loc_6841
0x6830  ldarg.1
0x6831  callvirt instance class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.OperationContext::get_ServiceSecurityContext()
0x6836  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_PrimaryIdentity()
0x683b  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0x6840  stloc.1
0x6841  ldloc.1
0x6842  brtrue.s loc_6860
0x6844  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6849  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x684e  brfalse.s loc_6860
0x6850  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x6855  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x685a  isinst   [mscorlib]System.Security.Claims.ClaimsPrincipal
0x685f  stloc.1
0x6860  ldloc.1
0x6861  brfalse.s loc_688B
0x6863  ldloc.1
0x6864  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x6869  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity
0x686e  brtrue.s loc_688B
0x6870  ldloc.1
0x6871  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0x6876  isinst   [mscorlib]System.Security.Principal.WindowsIdentity
0x687b  stloc.3
0x687c  ldloc.3
0x687d  brfalse.s loc_688B
0x687f  ldloc.3
0x6880  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity [Microsoft.Crm.Core]Microsoft.Crm.Core.Security.Identity.UserIdentity::Get(class [mscorlib]System.Security.Claims.ClaimsIdentity)
0x6885  newobj   instance void [mscorlib]System.Security.Claims.ClaimsPrincipal::.ctor(class [mscorlib]System.Security.Principal.IIdentity)
0x688a  stloc.1
0x688b  ldloc.1
0x688c  ldloc.0
0x688d  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x6892  ldstr    aWcfauthenticat// "WcfAuthentication"
0x6897  newobj   instance void [System.IdentityModel]System.Security.Claims.AuthorizationContext::.ctor(class [mscorlib]System.Security.Claims.ClaimsPrincipal, string, string)
0x689c  stloc.2
0x689d  ldarg.0
0x689e  call     instance class [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager Microsoft.Crm.Authentication.WindowsIdentityAuthorizationManager::get_ClaimsAuthorizationManager()
0x68a3  ldloc.2
0x68a4  callvirt instance bool [System.IdentityModel]System.Security.Claims.ClaimsAuthorizationManager::CheckAccess(class [System.IdentityModel]System.Security.Claims.AuthorizationContext)
0x68a9  brfalse.s loc_68C8
0x68ab  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x68b0  ldloc.2
0x68b1  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel]System.Security.Claims.AuthorizationContext::get_Principal()
0x68b6  callvirt instance void [System.Web]System.Web.HttpContext::set_User(class [mscorlib]System.Security.Principal.IPrincipal)
0x68bb  ldloc.2
0x68bc  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel]System.Security.Claims.AuthorizationContext::get_Principal()
0x68c1  call     void [mscorlib]System.Threading.Thread::set_CurrentPrincipal(class [mscorlib]System.Security.Principal.IPrincipal)
0x68c6  ldc.i4.1
0x68c7  ret
0x68c8  ldstr    aWindowsidentit_3// "WindowsIdentityAuthorizationManager.Aut"...
0x68cd  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x68d2  ldc.i4.0
0x68d3  ret
```
