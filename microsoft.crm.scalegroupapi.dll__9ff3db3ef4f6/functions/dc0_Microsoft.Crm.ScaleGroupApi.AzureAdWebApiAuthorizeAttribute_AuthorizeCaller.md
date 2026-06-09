# Microsoft.Crm.ScaleGroupApi.AzureAdWebApiAuthorizeAttribute::AuthorizeCaller

- ea: `0xdc0`
- end: `0xe4c`
- name: `Microsoft.Crm.ScaleGroupApi.AzureAdWebApiAuthorizeAttribute::AuthorizeCaller`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xdb0`

## callees

- `0x490`
- `0x500`
- `0xdc0`

## string_xrefs

- `0xe0a`: `http://schemas.microsoft.com/identity/claims/tenantid`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  call     class [System]System.Collections.Specialized.NameValueCollection [System.Configuration]System.Configuration.ConfigurationManager::get_AppSettings()
0xdc5  ldstr    aDebugskipauthe// "DebugSkipAuthentication"
0xdca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xdcf  ldsfld   string [mscorlib]System.Boolean::TrueString
0xdd4  ldc.i4.5
0xdd5  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdda  brfalse.s loc_DDE
0xddc  ldc.i4.1
0xddd  ret
0xdde  ldarg.0
0xddf  brfalse.s loc_DF6
0xde1  ldarg.0
0xde2  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xde7  brfalse.s loc_DF6
0xde9  ldarg.0
0xdea  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Claims.ClaimsPrincipal::get_Identity()
0xdef  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0xdf4  brtrue.s loc_DF8
0xdf6  ldc.i4.0
0xdf7  ret
0xdf8  ldarg.0
0xdf9  ldstr    aAppid// "appid"
0xdfe  callvirt instance class [mscorlib]System.Security.Claims.Claim [mscorlib]System.Security.Claims.ClaimsPrincipal::FindFirst(string)
0xe03  stloc.0
0xe04  ldloc.0
0xe05  brtrue.s loc_E09
0xe07  ldc.i4.0
0xe08  ret
0xe09  ldarg.0
0xe0a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/identity/c"...
0xe0f  callvirt instance class [mscorlib]System.Security.Claims.Claim [mscorlib]System.Security.Claims.ClaimsPrincipal::FindFirst(string)
0xe14  stloc.1
0xe15  ldloc.1
0xe16  brtrue.s loc_E1A
0xe18  ldc.i4.0
0xe19  ret
0xe1a  call     class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::RetrieveInfo()
0xe1f  ldloc.1
0xe20  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0xe25  ldstr    asc_652E// ":"
0xe2a  ldloc.0
0xe2b  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0xe30  call     string [mscorlib]System.String::Concat(string, string, string)
0xe35  stloc.2
0xe36  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_AllowedTenantAndClientIds()
0xe3b  ldloc.2
0xe3c  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xe41  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0xe46  brfalse.s loc_E4A
0xe48  ldc.i4.1
0xe49  ret
0xe4a  ldc.i4.0
0xe4b  ret
```
