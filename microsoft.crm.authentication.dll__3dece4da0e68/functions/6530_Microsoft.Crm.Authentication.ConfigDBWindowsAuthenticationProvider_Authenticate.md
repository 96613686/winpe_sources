# Microsoft.Crm.Authentication.ConfigDBWindowsAuthenticationProvider::Authenticate

- ea: `0x6530`
- end: `0x66a4`
- name: `Microsoft.Crm.Authentication.ConfigDBWindowsAuthenticationProvider::Authenticate`
- size: `372`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1570`
- `0x1590`
- `0x1bb0`
- `0x1fa0`
- `0x45e0`
- `0x4620`
- `0x56c0`
- `0x5820`
- `0x58f0`
- `0x5940`
- `0x5ca0`
- `0x6530`
- `0x78e0`

## string_xrefs

- `0x655a`: `ConfigDBWindowsAuthenticationProvider.Authenticate(), application != null && !application.Request.IsAuthenticated`
- `0x6594`: `ConfigDBWindowsAuthenticationProvider.Authenticate(), empty orgId returned from GetDefaultOrganization()`
- `0x65ba`: `ConfigDBWindowsAuthenticationProvider.Authenticate(), empty userId returned from GetCrmUserId()`
- `0x6673`: `ConfigDBWindowsAuthenticationProvider published User Identity Context [UserToken:{0}] [UserId:{1}].`
- `0x6695`: `ConfigDBWindowsAuthenticationProvider.Authenticate()`

## pseudocode

```c

```

## disassembly

```asm
0x6530  ldarg.0
0x6531  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::UpdateAuthenticateAttemptCounter()
0x6536  call     bool Microsoft.Crm.Authentication.UserIdentityContext::get_IsAvailable()
0x653b  brtrue.s loc_6548
0x653d  ldstr    aUserIdentityCo// "User Identity Context must be available"...
0x6542  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6547  throw
0x6548  ldarg.1
0x6549  brfalse.s loc_6564
0x654b  ldarg.1
0x654c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x6551  callvirt instance bool [System.Web]System.Web.HttpRequest::get_IsAuthenticated()
0x6556  brtrue.s loc_6564
0x6558  ldarg.0
0x6559  ldarg.1
0x655a  ldstr    aConfigdbwindow// "ConfigDBWindowsAuthenticationProvider.A"...
0x655f  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess(class [System.Web]System.Web.HttpApplication application, string context)
0x6564  call     class Microsoft.Crm.Authentication.UserIdentityContext Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x6569  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x656e  call     string [Microsoft.Crm.Core]IdentityExtensions::GetActiveDirectorySecurityIdentifier(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x6573  stloc.0
0x6574  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x6579  ldloc.0
0x657a  call     string Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::GetUserToken(string sid)
0x657f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetDefaultOrganization(string)
0x6584  stloc.1
0x6585  ldloc.1
0x6586  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x658b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6590  brfalse.s loc_659E
0x6592  ldarg.0
0x6593  ldarg.1
0x6594  ldstr    aConfigdbwindow_0// "ConfigDBWindowsAuthenticationProvider.A"...
0x6599  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess(class [System.Web]System.Web.HttpApplication application, string context)
0x659e  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x65a3  ldloc.1
0x65a4  ldloc.0
0x65a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetCrmUserId(valuetype [mscorlib]System.Guid, string)
0x65aa  stloc.2
0x65ab  ldloc.2
0x65ac  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x65b1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x65b6  brfalse.s loc_65C4
0x65b8  ldarg.0
0x65b9  ldarg.1
0x65ba  ldstr    aConfigdbwindow_1// "ConfigDBWindowsAuthenticationProvider.A"...
0x65bf  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess(class [System.Web]System.Web.HttpApplication application, string context)
0x65c4  call     class Microsoft.Crm.Authentication.UserIdentityContext Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x65c9  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x65ce  ldloc.1
0x65cf  call     void [Microsoft.Crm.Core]IdentityExtensions::SetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x65d4  call     class Microsoft.Crm.Authentication.UserIdentityContext Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x65d9  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x65de  ldloc.2
0x65df  call     void [Microsoft.Crm.Core]IdentityExtensions::SetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x65e4  ldarg.1
0x65e5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpApplication::get_Request()
0x65ea  ldloc.1
0x65eb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerId(class [System.Web]System.Web.HttpRequest request, valuetype [mscorlib]System.Guid organizationId)
0x65f0  stloc.3
0x65f1  ldloc.3
0x65f2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x65f7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x65fc  brfalse.s loc_666C
0x65fe  ldloc.3
0x65ff  ldloc.1
0x6600  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmPrincipal::DoRecognizeUser(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId)
0x6605  stloc.s  4
0x6607  ldloc.s  4
0x6609  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x660e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6613  brfalse.s loc_664D
0x6615  ldloc.3
0x6616  ldloc.1
0x6617  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::ValidateSpecialUser(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId)
0x661c  stloc.s  5
0x661e  ldloca.s 5
0x6620  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x6625  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x662a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x662f  brfalse.s loc_664D
0x6631  ldloca.s 5
0x6633  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_OrganizationId()
0x6638  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x663d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6642  brfalse.s loc_664D
0x6644  ldloca.s 5
0x6646  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x664b  stloc.s  4
0x664d  ldloc.s  4
0x664f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6654  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6659  brfalse.s loc_666C
0x665b  call     class Microsoft.Crm.Authentication.UserIdentityContext Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x6660  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x6665  ldloc.s  4
0x6667  call     void [Microsoft.Crm.Core]IdentityExtensions::SetCallerId(class [mscorlib]System.Security.Claims.ClaimsPrincipal, valuetype [mscorlib]System.Guid)
0x666c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6671  ldc.i4.s 0x16
0x6673  ldstr    aConfigdbwindow_2// "ConfigDBWindowsAuthenticationProvider p"...
0x6678  ldc.i4.2
0x6679  newarr   [mscorlib]System.Object
0x667e  dup
0x667f  ldc.i4.0
0x6680  ldloc.0
0x6681  stelem.ref
0x6682  dup
0x6683  ldc.i4.1
0x6684  ldloc.2
0x6685  box      [mscorlib]System.Guid
0x668a  stelem.ref
0x668b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6690  ldc.i4.1
0x6691  stloc.s  6
0x6693  leave.s  loc_66A1
0x6695  ldstr    aConfigdbwindow_3// "ConfigDBWindowsAuthenticationProvider.A"...
0x669a  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0x669f  rethrow
0x66a1  ldloc.s  6
0x66a3  ret
```
