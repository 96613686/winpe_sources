# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::AdjustSessionTokenLifetime

- ea: `0xe200`
- end: `0xe357`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::AdjustSessionTokenLifetime`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x15130`

## callees

- `0xdc0`
- `0x1320`
- `0x1380`
- `0x78e0`
- `0xc6b0`
- `0xe0c0`
- `0xe1b0`
- `0xe200`

## string_xrefs

- `0xe345`: `CrmSessionAuthenticationManager.AdjustSessionTokenLifetime() error adjusting session token`

## pseudocode

```c

```

## disassembly

```asm
0xe200  ldarg.0
0xe201  brfalse.s loc_E207
0xe203  ldarg.3
0xe204  ldind.ref
0xe205  brtrue.s loc_E20F
0xe207  ldc.i4.0
0xe208  stloc.s  5
0xe20a  leave    loc_E354
0xe20f  ldarg.1
0xe210  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xe215  stloc.0
0xe216  ldarg.1
0xe217  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xe21c  stloc.1
0xe21d  ldarg.2
0xe21e  brfalse.s loc_E256
0xe220  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xe225  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xe22a  ldc.i4.2
0xe22b  beq.s    loc_E256
0xe22d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe232  brfalse.s loc_E256
0xe234  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe239  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xe23e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetRequestedOrganizationFromReplyContext(class [System.Web]System.Web.HttpRequest request)
0xe243  stloc.s  6
0xe245  ldloc.s  6
0xe247  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe24c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe251  brfalse.s loc_E256
0xe253  ldloc.s  6
0xe255  stloc.0
0xe256  ldarg.2
0xe257  brtrue.s loc_E263
0xe259  ldarg.3
0xe25a  ldind.ref
0xe25b  ldloc.0
0xe25c  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::CalculateSessionTokenValidToForCurrentSession(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken sessionToken, valuetype [mscorlib]System.Guid organizationId)
0xe261  br.s     loc_E26C
0xe263  ldarg.3
0xe264  ldind.ref
0xe265  ldloc.0
0xe266  ldloc.1
0xe267  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::CalculateSessionTokenValidToForNewSession(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken sessionToken, valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid userId)
0xe26c  stloc.2
0xe26d  ldloc.2
0xe26e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xe273  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe278  brfalse.s loc_E282
0xe27a  ldc.i4.0
0xe27b  stloc.s  5
0xe27d  leave    loc_E354
0xe282  ldloc.2
0xe283  ldarg.3
0xe284  ldind.ref
0xe285  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xe28a  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe28f  ldloc.0
0xe290  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsFeatureCustomSessionDurationEnabled(valuetype [mscorlib]System.Guid orgId)
0xe295  brfalse.s loc_E2AB
0xe297  ldarg.1
0xe298  call     valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.Crm.Core]IdentityExtensions::GetCustomSessionTokenValidTo(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xe29d  stloc.s  7
0xe29f  ldloca.s 7
0xe2a1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0xe2a6  ldc.i4.0
0xe2a7  ceq
0xe2a9  br.s     loc_E2AC
0xe2ab  ldc.i4.0
0xe2ac  stloc.3
0xe2ad  brtrue.s loc_E2BA
0xe2af  ldloc.3
0xe2b0  brtrue.s loc_E2BA
0xe2b2  ldc.i4.0
0xe2b3  stloc.s  5
0xe2b5  leave    loc_E354
0xe2ba  ldarg.3
0xe2bb  ldind.ref
0xe2bc  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0xe2c1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.ClaimsIdentity> [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identities()
0xe2c6  call     T0x2B000022
0xe2cb  stloc.s  4
0xe2cd  ldloc.s  4
0xe2cf  brfalse.s loc_E2E2
0xe2d1  ldloc.s  4
0xe2d3  callvirt instance object [mscorlib]System.Security.Claims.ClaimsIdentity::get_BootstrapContext()
0xe2d8  brfalse.s loc_E2E2
0xe2da  ldloc.s  4
0xe2dc  ldnull
0xe2dd  callvirt instance void [mscorlib]System.Security.Claims.ClaimsIdentity::set_BootstrapContext(object)
0xe2e2  ldloc.0
0xe2e3  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsFeatureCustomSessionDurationEnabled(valuetype [mscorlib]System.Guid orgId)
0xe2e8  brfalse.s loc_E31B
0xe2ea  ldloc.0
0xe2eb  call     int32 Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetExpirationReminderTimeForOrganization(valuetype [mscorlib]System.Guid orgId)
0xe2f0  stloc.s  8
0xe2f2  ldloc.s  4
0xe2f4  brfalse.s loc_E300
0xe2f6  ldloc.s  4
0xe2f8  ldloc.2
0xe2f9  ldloc.s  8
0xe2fb  call     void Microsoft.Crm.Authentication.Claims.ClaimsUtility::SetCustomSessionDurationClaimValues(class [mscorlib]System.Security.Claims.ClaimsIdentity claimsIdentity, valuetype [mscorlib]System.DateTime customSessionTokenValidTo, int32 customSessionTokenReminderInMins)
0xe300  ldarg.1
0xe301  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xe306  isinst   [mscorlib]System.Security.Claims.ClaimsIdentity
0xe30b  stloc.s  9
0xe30d  ldloc.s  9
0xe30f  brfalse.s loc_E31B
0xe311  ldloc.s  9
0xe313  ldloc.2
0xe314  ldloc.s  8
0xe316  call     void Microsoft.Crm.Authentication.Claims.ClaimsUtility::SetCustomSessionDurationClaimValues(class [mscorlib]System.Security.Claims.ClaimsIdentity claimsIdentity, valuetype [mscorlib]System.DateTime customSessionTokenValidTo, int32 customSessionTokenReminderInMins)
0xe31b  ldarg.3
0xe31c  ldarg.0
0xe31d  ldarg.3
0xe31e  ldind.ref
0xe31f  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0xe324  ldarg.3
0xe325  ldind.ref
0xe326  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_Context()
0xe32b  ldarg.3
0xe32c  ldind.ref
0xe32d  callvirt instance string [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken::get_EndpointId()
0xe332  ldarg.3
0xe333  ldind.ref
0xe334  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0xe339  ldloc.2
0xe33a  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::CreateSessionSecurityToken(class [mscorlib]System.Security.Claims.ClaimsPrincipal, string, string, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe33f  stind.ref
0xe340  ldc.i4.1
0xe341  stloc.s  5
0xe343  leave.s  loc_E354
0xe345  ldstr    aCrmsessionauth_0// "CrmSessionAuthenticationManager.AdjustS"...
0xe34a  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xe34f  ldc.i4.0
0xe350  stloc.s  5
0xe352  leave.s  loc_E354
0xe354  ldloc.s  5
0xe356  ret
```
