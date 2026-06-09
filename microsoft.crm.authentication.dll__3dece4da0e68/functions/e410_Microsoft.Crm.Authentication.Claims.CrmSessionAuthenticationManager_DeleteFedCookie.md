# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteFedCookie

- ea: `0xe410`
- end: `0xe463`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteFedCookie`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xe500`

## callees

- `0x2d50`
- `0x2e20`
- `0xe410`
- `0xe6e0`
- `0xe720`

## pseudocode

```c

```

## disassembly

```asm
0xe410  ldarg.0
0xe411  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe416  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Domain()
0xe41b  stloc.0
0xe41c  ldarg.0
0xe41d  call     instance class [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler [System.IdentityModel.Services]System.IdentityModel.Services.SessionAuthenticationModule::get_CookieHandler()
0xe422  callvirt instance string [System.IdentityModel.Services]System.IdentityModel.Services.CookieHandler::get_Path()
0xe427  stloc.1
0xe428  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.AppUtilSettingsProvider::get_Instance()
0xe42d  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider::IsPathBasedURLsEnabled()
0xe432  brtrue.s loc_E459
0xe434  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe439  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xe43e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xe443  ldc.i4.2
0xe444  beq.s    loc_E449
0xe446  ldloc.0
0xe447  br.s     loc_E453
0xe449  call     class Microsoft.Crm.Authentication.CrmPostAuthenticationSettings Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Instance()
0xe44e  callvirt instance string Microsoft.Crm.Authentication.CrmPostAuthenticationSettings::get_Domain()
0xe453  call     string Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::GetIFDDomain(valuetype [mscorlib]System.Guid orgId, string domain)
0xe458  stloc.0
0xe459  ldarg.0
0xe45a  ldarg.1
0xe45b  ldloc.1
0xe45c  ldloc.0
0xe45d  call     instance void Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::DeleteSessionTokenCookie(string name, string path, string domain)
0xe462  ret
```
