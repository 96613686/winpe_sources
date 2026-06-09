# Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::CalculateSessionTokenValidToForCurrentSession

- ea: `0xe1b0`
- end: `0xe1f4`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionAuthenticationManager::CalculateSessionTokenValidToForCurrentSession`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe200`

## callees

- `0x1250`
- `0x1380`
- `0xe1b0`

## pseudocode

```c

```

## disassembly

```asm
0xe1b0  ldarg.0
0xe1b1  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xe1b6  stloc.0
0xe1b7  ldarg.1
0xe1b8  call     bool Microsoft.Crm.Authentication.CrmAuthorizationUtility::IsFeatureCustomSessionDurationEnabled(valuetype [mscorlib]System.Guid orgId)
0xe1bd  brfalse.s loc_E1F2
0xe1bf  ldarg.0
0xe1c0  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xe1c5  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Utilities]Microsoft.Crm.DateTimeWrapper::get_UtcNow()
0xe1ca  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe1cf  stloc.2
0xe1d0  ldloca.s 2
0xe1d2  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0xe1d7  ldarg.1
0xe1d8  call     int32 Microsoft.Crm.Authentication.CrmAuthorizationUtility::GetSessionDurationInMinsForOrganization(valuetype [mscorlib]System.Guid orgId)
0xe1dd  stloc.1
0xe1de  ldloc.1
0xe1df  conv.r8
0xe1e0  ble.un.s loc_E1F2
0xe1e2  call     valuetype [mscorlib]System.DateTime [Microsoft.Crm.Utilities]Microsoft.Crm.DateTimeWrapper::get_UtcNow()
0xe1e7  stloc.3
0xe1e8  ldloca.s 3
0xe1ea  ldloc.1
0xe1eb  conv.r8
0xe1ec  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xe1f1  stloc.0
0xe1f2  ldloc.0
0xe1f3  ret
```
