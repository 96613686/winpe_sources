# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::CalculateSessionTokenValidToForNewSession

- ea: `0xe0c0`
- end: `0xe1af`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::CalculateSessionTokenValidToForNewSession`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0xe200`

## callees

- `0xf10`
- `0x1250`
- `0x1380`
- `0xe0c0`

## pseudocode

```c

```

## disassembly

```asm
0xe0c0  ldarg.0
0xe0c1  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xe0c6  stloc.0
0xe0c7  ldarg.1
0xe0c8  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsFeatureCustomSessionDurationEnabled(valuetype [mscorlib]System.Guid orgId)
0xe0cd  brfalse.s loc_E0F9
0xe0cf  ldarg.1
0xe0d0  call     int32 Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetSessionDurationInMinsForOrganization(valuetype [mscorlib]System.Guid orgId)
0xe0d5  stloc.1
0xe0d6  ldarg.0
0xe0d7  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0xe0dc  stloc.3
0xe0dd  ldloca.s 3
0xe0df  ldloc.1
0xe0e0  conv.r8
0xe0e1  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xe0e6  stloc.2
0xe0e7  ldloc.2
0xe0e8  ldarg.0
0xe0e9  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xe0ee  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe0f3  brfalse.s loc_E170
0xe0f5  ldloc.2
0xe0f6  stloc.0
0xe0f7  br.s     loc_E170
0xe0f9  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xe0fe  ldstr    aEvostsauthenti// "EvoSTSAuthenticationEnabled"
0xe103  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider::GetSiteSetting(string)
0xe108  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0xe10d  stloc.s  4
0xe10f  ldloca.s 4
0xe111  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0xe116  brtrue.s loc_E11B
0xe118  ldc.i4.0
0xe119  br.s     loc_E122
0xe11b  ldloca.s 4
0xe11d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0xe122  brfalse.s loc_E170
0xe124  ldarg.0
0xe125  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0xe12a  stloc.3
0xe12b  ldloca.s 3
0xe12d  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xe132  ldstr    aMbiSslTimetoli// "MBI_SSL_TimeToLive"
0xe137  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider::GetSiteSetting(string)
0xe13c  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0xe141  stloc.s  6
0xe143  ldloca.s 6
0xe145  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0xe14a  brtrue.s loc_E14F
0xe14c  ldc.i4.0
0xe14d  br.s     loc_E156
0xe14f  ldloca.s 6
0xe151  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0xe156  conv.r8
0xe157  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0xe15c  stloc.s  5
0xe15e  ldloc.s  5
0xe160  ldarg.0
0xe161  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xe166  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe16b  brfalse.s loc_E170
0xe16d  ldloc.s  5
0xe16f  stloc.0
0xe170  ldarg.1
0xe171  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe176  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe17b  brfalse.s loc_E1AD
0xe17d  ldarg.2
0xe17e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xe183  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe188  brfalse.s loc_E1AD
0xe18a  ldarg.2
0xe18b  ldarg.1
0xe18c  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::IsSupportUser(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xe191  brfalse.s loc_E1AD
0xe193  ldarg.0
0xe194  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0xe199  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetSupportUserExpiration(valuetype [mscorlib]System.DateTime validFrom)
0xe19e  stloc.s  7
0xe1a0  ldloc.s  7
0xe1a2  ldloc.0
0xe1a3  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe1a8  brfalse.s loc_E1AD
0xe1aa  ldloc.s  7
0xe1ac  stloc.0
0xe1ad  ldloc.0
0xe1ae  ret
```
