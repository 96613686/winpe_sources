# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteSessionTokenToCrmCookie

- ea: `0xe360`
- end: `0xe410`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::WriteSessionTokenToCrmCookie`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x15130`

## callees

- `0x2d50`
- `0x2e20`
- `0x78e0`
- `0xe060`
- `0xe360`
- `0xe6e0`

## string_xrefs

- `0xe3f6`: `CrmSessionAuthenticationManager.WriteSessionTokenToCrmCookie() error writing cookie buffer`
- `0xe402`: `CrmSessionAuthenticationManager.WriteSessionTokenToCrmCookie() error writing cookie buffer`

## pseudocode

```c

```

## disassembly

```asm
0xe360  ldarg.1
0xe361  ldstr    aHandler// "handler"
0xe366  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xe36b  ldarg.1
0xe36c  ldarg.2
0xe36d  callvirt instance unsigned int8[] [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityTokenHandler::WriteToken(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken)
0xe372  stloc.0
0xe373  ldarg.0
0xe374  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe379  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Domain()
0xe37e  stloc.1
0xe37f  ldarg.0
0xe380  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe385  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Path()
0xe38a  stloc.2
0xe38b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.AppUtilSettingsProvider::get_Instance()
0xe390  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider::IsPathBasedURLsEnabled()
0xe395  brtrue.s loc_E3BC
0xe397  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe39c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xe3a1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xe3a6  ldc.i4.2
0xe3a7  beq.s    loc_E3AC
0xe3a9  ldloc.1
0xe3aa  br.s     loc_E3B6
0xe3ac  call     class Microsoft.Crm.Authentication.CrmPostAuthenticationSettings Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Instance()
0xe3b1  callvirt instance string Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Domain()
0xe3b6  call     string Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::GetIFDDomain(valuetype [mscorlib]System.Guid orgId, string domain)
0xe3bb  stloc.1
0xe3bc  call     bool Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::get_DisableCrmCookieSsl()
0xe3c1  ldc.i4.0
0xe3c2  ceq
0xe3c4  stloc.3
0xe3c5  ldarg.0
0xe3c6  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe3cb  ldloc.0
0xe3cc  ldarg.0
0xe3cd  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe3d2  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Name()
0xe3d7  ldloc.2
0xe3d8  ldloc.1
0xe3d9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xe3de  ldloc.3
0xe3df  ldarg.0
0xe3e0  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe3e5  callvirt instance bool [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_HideFromClientScript()
0xe3ea  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe3ef  callvirt instance void [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::Write(unsigned int8[], string, string, string, valuetype [mscorlib]System.DateTime, bool, bool, class [System.Web]System.Web.HttpContext)
0xe3f4  leave.s  loc_E40E
0xe3f6  ldstr    aCrmsessionauth_1// "CrmSessionAuthenticationManager.WriteSe"...
0xe3fb  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xe400  leave.s  loc_E40E
0xe402  ldstr    aCrmsessionauth_1// "CrmSessionAuthenticationManager.WriteSe"...
0xe407  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogException(class [mscorlib]System.Exception exception, [opt] string context)
0xe40c  leave.s  loc_E40E
0xe40e  ldarg.2
0xe40f  ret
```
