# Microsoft.Crm.Authentication.WindowsIdentityAuthorizationManager::CheckAccessCore

- ea: `0x6730`
- end: `0x67d2`
- name: `Microsoft.Crm.Authentication.WindowsIdentityAuthorizationManager::CheckAccessCore`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x6730`
- `0x67e0`
- `0x7780`
- `0x78e0`

## string_xrefs

- `0x6738`: `WindowsIdentityAuthorizationManager.CheckAccessCore(): operationContext.IncomingMessageHeaders == null`
- `0x6751`: `WindowsIdentityAuthorizationManager.CheckAccessCore(): operationContext.ServiceSecurityContext == null`
- `0x6794`: `WindowsIdentityAuthorizationManager user '{0}' was not authenticated, base access check failed`
- `0x67c4`: `WindowsIdentityAuthorizationManager.CheckAccessCore()`

## pseudocode

```c

```

## disassembly

```asm
0x6730  ldarg.1
0x6731  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x6736  brtrue.s loc_6749
0x6738  ldstr    aWindowsidentit// "WindowsIdentityAuthorizationManager.Che"...
0x673d  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x6742  ldc.i4.0
0x6743  stloc.0
0x6744  leave    loc_67D0
0x6749  ldarg.1
0x674a  callvirt instance class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.OperationContext::get_ServiceSecurityContext()
0x674f  brtrue.s loc_675F
0x6751  ldstr    aWindowsidentit_0// "WindowsIdentityAuthorizationManager.Che"...
0x6756  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x675b  ldc.i4.0
0x675c  stloc.0
0x675d  leave.s  loc_67D0
0x675f  ldarg.0
0x6760  ldarg.1
0x6761  call     instance bool [System.ServiceModel]System.ServiceModel.ServiceAuthorizationManager::CheckAccessCore(class [System.ServiceModel]System.ServiceModel.OperationContext)
0x6766  brfalse.s loc_678F
0x6768  ldarg.0
0x6769  ldarg.1
0x676a  call     instance bool Microsoft.Crm.Authentication.WindowsIdentityAuthorizationManager::Authenticate(class [System.ServiceModel]System.ServiceModel.OperationContext operationContext)
0x676f  brtrue.s loc_6775
0x6771  ldc.i4.0
0x6772  stloc.0
0x6773  leave.s  loc_67D0
0x6775  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x677a  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x677f  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x6784  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x6789  brfalse.s loc_678F
0x678b  ldc.i4.1
0x678c  stloc.0
0x678d  leave.s  loc_67D0
0x678f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6794  ldstr    aWindowsidentit_1// "WindowsIdentityAuthorizationManager use"...
0x6799  ldc.i4.1
0x679a  newarr   [mscorlib]System.Object
0x679f  dup
0x67a0  ldc.i4.0
0x67a1  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x67a6  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpContext::get_User()
0x67ab  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x67b0  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x67b5  stelem.ref
0x67b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x67bb  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0x67c0  ldc.i4.0
0x67c1  stloc.0
0x67c2  leave.s  loc_67D0
0x67c4  ldstr    aWindowsidentit_2// "WindowsIdentityAuthorizationManager.Che"...
0x67c9  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x67ce  rethrow
0x67d0  ldloc.0
0x67d1  ret
```
