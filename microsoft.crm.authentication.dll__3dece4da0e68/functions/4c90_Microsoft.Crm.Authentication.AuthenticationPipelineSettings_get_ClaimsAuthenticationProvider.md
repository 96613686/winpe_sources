# Microsoft.Crm.Authentication.AuthenticationPipelineSettings::get_ClaimsAuthenticationProvider

- ea: `0x4c90`
- end: `0x4d20`
- name: `Microsoft.Crm.Authentication.AuthenticationPipelineSettings::get_ClaimsAuthenticationProvider`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4c90`
- `0x52b0`

## string_xrefs

- `0x4ca6`: `UseConfigClaimsPrefix`
- `0x4ceb`: `Microsoft.Crm.Authentication.Claims.ConfigClaimsAuthenticationProvider, Microsoft.Crm.Authentication, Version={0}, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0x4d0a`: `Microsoft.Crm.Authentication.Claims.ClaimsAuthenticationProvider, Microsoft.Crm.Platform.Server, Version={0}, Culture=neutral, PublicKeyToken=31bf3856ad364e35`

## pseudocode

```c

```

## disassembly

```asm
0x4c90  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4c95  brtrue   loc_4D1E
0x4c9a  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_ClaimsEnabled()
0x4c9f  brfalse.s loc_4D1E
0x4ca1  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x4ca6  ldstr    aUseconfigclaim// "UseConfigClaimsPrefix"
0x4cab  ldc.i4.0
0x4cac  callvirt T0x2B000001
0x4cb1  stloc.0
0x4cb2  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_OnlinePortalRequest()
0x4cb7  brtrue.s loc_4CE0
0x4cb9  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_IsDiscoveryRequest()
0x4cbe  brtrue.s loc_4CE0
0x4cc0  ldloc.0
0x4cc1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cc6  brtrue.s loc_4CFF
0x4cc8  call     class [System.Web]System.Web.HttpRequestBase [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmHttpContext::get_Request()
0x4ccd  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequestBase::get_Url()
0x4cd2  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x4cd7  ldloc.0
0x4cd8  ldc.i4.5
0x4cd9  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4cde  brfalse.s loc_4CFF
0x4ce0  ldarg.0
0x4ce1  ldfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationPipelineSettings::_claimsProvider
0x4ce6  dup
0x4ce7  brtrue.s loc_4CFE
0x4ce9  pop
0x4cea  ldarg.0
0x4ceb  ldstr    aMicrosoftCrmAu_0// "Microsoft.Crm.Authentication.Claims.Con"...
0x4cf0  ldnull
0x4cf1  call     class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateProvider(string typeName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x4cf6  dup
0x4cf7  stloc.1
0x4cf8  stfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationPipelineSettings::_claimsProvider
0x4cfd  ldloc.1
0x4cfe  ret
0x4cff  ldarg.0
0x4d00  ldfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationPipelineSettings::_orgClaimsProvider
0x4d05  dup
0x4d06  brtrue.s loc_4D1D
0x4d08  pop
0x4d09  ldarg.0
0x4d0a  ldstr    aMicrosoftCrmAu_1// "Microsoft.Crm.Authentication.Claims.Cla"...
0x4d0f  ldnull
0x4d10  call     class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.BaseAuthenticationSettings::CreateProvider(string typeName, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> configuration)
0x4d15  dup
0x4d16  stloc.1
0x4d17  stfld    class Microsoft.Crm.Authentication.IAuthenticationProvider Microsoft.Crm.Authentication.AuthenticationPipelineSettings::_orgClaimsProvider
0x4d1c  ldloc.1
0x4d1d  ret
0x4d1e  ldnull
0x4d1f  ret
```
