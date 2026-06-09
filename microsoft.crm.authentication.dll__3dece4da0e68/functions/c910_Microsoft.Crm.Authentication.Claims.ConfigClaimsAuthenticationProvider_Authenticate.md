# Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider::Authenticate

- ea: `0xc910`
- end: `0xc9ff`
- name: `Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider::Authenticate`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2020`
- `0x45e0`
- `0x4620`
- `0x5820`
- `0x5940`
- `0x78e0`
- `0xc910`
- `0xca00`

## string_xrefs

- `0xc920`: `ConfigClaimsAuthenticationProvider.Authenticate(): null application.User`
- `0xc97d`: `ConfigClaimsAuthenticationProvider.Authenticate: user with Auth Token '{0}' is disabled.`
- `0xc9e1`: `ConfigClaimsAuthenticationProvider.Authenticate(): null currentUser or currentUser.Principal`
- `0xc9f0`: `ConfigClaimsAuthenticationProvider.Authenticate()`

## pseudocode

```c

```

## disassembly

```asm
0xc910  ldarg.0
0xc911  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::UpdateAuthenticateAttemptCounter()
0xc916  ldarg.1
0xc917  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal [System.Web]System.Web.HttpApplication::get_User()
0xc91c  brtrue.s loc_C92F
0xc91e  ldarg.0
0xc91f  ldarg.1
0xc920  ldstr    aConfigclaimsau// "ConfigClaimsAuthenticationProvider.Auth"...
0xc925  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess(class [System.Web]System.Web.HttpApplication application, string context)
0xc92a  br       loc_C9EB
0xc92f  call     class Microsoft.Crm.Authentication.UserIdentityContext Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0xc934  stloc.0
0xc935  ldloc.0
0xc936  brfalse  loc_C9DF
0xc93b  ldloc.0
0xc93c  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xc941  brfalse  loc_C9DF
0xc946  ldloc.0
0xc947  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xc94c  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xc951  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0xc956  brfalse  loc_C9DF
0xc95b  ldloc.0
0xc95c  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xc961  call     string [Microsoft.Crm.Core]IdentityExtensions::GetUserPrincipalName(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xc966  stloc.1
0xc967  ldarg.0
0xc968  ldloc.0
0xc969  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xc96e  ldloc.1
0xc96f  call     instance bool Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider::CheckUserDisabled(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal, string userAuthToken)
0xc974  brfalse.s loc_C99B
0xc976  ldarg.0
0xc977  ldarg.1
0xc978  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc97d  ldstr    aConfigclaimsau_0// "ConfigClaimsAuthenticationProvider.Auth"...
0xc982  ldc.i4.1
0xc983  newarr   [mscorlib]System.Object
0xc988  dup
0xc989  ldc.i4.0
0xc98a  ldloc.1
0xc98b  stelem.ref
0xc98c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc991  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess(class [System.Web]System.Web.HttpApplication application, string context)
0xc996  ldc.i4.1
0xc997  stloc.s  4
0xc999  leave.s  loc_C9FC
0xc99b  ldloc.0
0xc99c  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xc9a1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xc9a6  stloc.2
0xc9a7  ldloc.0
0xc9a8  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0xc9ad  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xc9b2  stloc.3
0xc9b3  ldloc.2
0xc9b4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc9b9  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc9be  brfalse.s loc_C9DA
0xc9c0  ldloc.3
0xc9c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xc9c6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xc9cb  brfalse.s loc_C9DA
0xc9cd  ldloc.2
0xc9ce  ldloc.3
0xc9cf  ldc.i4.0
0xc9d0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc9d5  call     void Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::UpdateAccessTime(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid organizationId, valuetype Microsoft.Crm.Authentication.UserAuthenticationAccessType accessType, valuetype [mscorlib]System.DateTime accessTime)
0xc9da  ldc.i4.1
0xc9db  stloc.s  4
0xc9dd  leave.s  loc_C9FC
0xc9df  ldarg.0
0xc9e0  ldarg.1
0xc9e1  ldstr    aConfigclaimsau_1// "ConfigClaimsAuthenticationProvider.Auth"...
0xc9e6  call     instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::DenyAccess(class [System.Web]System.Web.HttpApplication application, string context)
0xc9eb  ldc.i4.0
0xc9ec  stloc.s  4
0xc9ee  leave.s  loc_C9FC
0xc9f0  ldstr    aConfigclaimsau_2// "ConfigClaimsAuthenticationProvider.Auth"...
0xc9f5  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xc9fa  rethrow
0xc9fc  ldloc.s  4
0xc9fe  ret
```
