# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionCookies

- ea: `0xe570`
- end: `0xe622`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionCookies`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xe710`

## callees

- `0x2d50`
- `0x2e20`
- `0xe570`
- `0xe660`
- `0xe6e0`
- `0xe720`
- `0xe740`

## pseudocode

```c

```

## disassembly

```asm
0xe570  ldarg.0
0xe571  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe576  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Domain()
0xe57b  stloc.0
0xe57c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.AppUtilSettingsProvider::get_Instance()
0xe581  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider::IsPathBasedURLsEnabled()
0xe586  brtrue.s loc_E5AD
0xe588  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe58d  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xe592  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xe597  ldc.i4.2
0xe598  beq.s    loc_E59D
0xe59a  ldloc.0
0xe59b  br.s     loc_E5A7
0xe59d  call     class Microsoft.Crm.Authentication.CrmPostAuthenticationSettings Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Instance()
0xe5a2  callvirt instance string Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Domain()
0xe5a7  call     string Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::GetIFDDomain(valuetype [mscorlib]System.Guid orgId, string domain)
0xe5ac  stloc.0
0xe5ad  ldarg.0
0xe5ae  ldarg.0
0xe5af  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe5b4  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Name()
0xe5b9  ldarg.0
0xe5ba  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe5bf  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Path()
0xe5c4  ldloc.0
0xe5c5  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionTokenCookie(string name, string path, string domain)
0xe5ca  ldarg.0
0xe5cb  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_ContextSessionSecurityToken()
0xe5d0  brfalse.s loc_E5DE
0xe5d2  ldarg.0
0xe5d3  ldarg.0
0xe5d4  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_ContextSessionSecurityToken()
0xe5d9  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::RemoveSessionTokenFromCache(class [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken token)
0xe5de  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.AppUtilSettingsProvider::get_Instance()
0xe5e3  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider::IsPathBasedURLsEnabled()
0xe5e8  brtrue.s loc_E5F4
0xe5ea  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xe5ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.MapOrgUtility::ClearOrganizationContextValues(class [System.Web]System.Web.HttpContext)
0xe5f4  ldarg.0
0xe5f5  ldarg.0
0xe5f6  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe5fb  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Path()
0xe600  ldloc.0
0xe601  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteOwinSessionTokenCookie(string path, string domain)
0xe606  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xe60b  ldc.i4.s 0x16
0xe60d  ldstr    aAuthCrmsession// "AUTH: CrmSessionAuthenticationManager {"...
0xe612  ldc.i4.1
0xe613  newarr   [mscorlib]System.Object
0xe618  dup
0xe619  ldc.i4.0
0xe61a  ldarg.0
0xe61b  stelem.ref
0xe61c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe621  ret
```
