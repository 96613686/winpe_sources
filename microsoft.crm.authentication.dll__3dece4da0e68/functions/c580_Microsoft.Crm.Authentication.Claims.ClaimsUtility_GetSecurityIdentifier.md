# Microsoft.Crm.Authentication.Claims.ClaimsUtility::GetSecurityIdentifier

- ea: `0xc580`
- end: `0xc638`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsUtility::GetSecurityIdentifier`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5d30`

## callees

- `0xa00`
- `0x7780`
- `0xc580`

## string_xrefs

- `0xc5e3`: `	ClaimsUtility.GetSecurityIdentifier failed for user {0}, SecurityAccessDeniedException: {1}.`
- `0xc60a`: `	ClaimsUtility.GetSecurityIdentifier failed for user {0}, FaultException<ExceptionDetail>: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xc580  ldarg.0
0xc581  ldstr    aPrincipal// "principal"
0xc586  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xc58b  ldarg.0
0xc58c  call     string [Microsoft.Crm.Core]IdentityExtensions::GetUserPrincipalName(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xc591  stloc.0
0xc592  ldarg.0
0xc593  call     string [Microsoft.Crm.Core]IdentityExtensions::GetActiveDirectorySecurityIdentifier(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0xc598  stloc.1
0xc599  ldloc.1
0xc59a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc59f  brtrue.s loc_C5A3
0xc5a1  ldloc.1
0xc5a2  ret
0xc5a3  ldloc.0
0xc5a4  ldstr    aUserprincipaln// "userPrincipalName"
0xc5a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0xc5ae  ldnull
0xc5af  stloc.2
0xc5b0  ldloc.2
0xc5b1  ldnull
0xc5b2  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Equality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0xc5b7  brfalse.s loc_C5C2
0xc5b9  ldloc.0
0xc5ba  ldloca.s 2
0xc5bc  call     bool Microsoft.Crm.Authentication.ADHelper::TryGetSidFromAccount(string accountName, [out] class [mscorlib]System.Security.Principal.SecurityIdentifier& securityIdentifier)
0xc5c1  pop
0xc5c2  ldloc.2
0xc5c3  ldnull
0xc5c4  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Inequality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0xc5c9  brfalse.s loc_C5D4
0xc5cb  ldloc.2
0xc5cc  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0xc5d1  stloc.3
0xc5d2  leave.s  loc_C636
0xc5d4  ldsfld   string [mscorlib]System.String::Empty
0xc5d9  stloc.3
0xc5da  leave.s  loc_C636
0xc5dc  stloc.s  4
0xc5de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc5e3  ldstr    aClaimsutilityG// "\tClaimsUtility.GetSecurityIdentifier f"...
0xc5e8  ldc.i4.2
0xc5e9  newarr   [mscorlib]System.Object
0xc5ee  dup
0xc5ef  ldc.i4.0
0xc5f0  ldloc.0
0xc5f1  stelem.ref
0xc5f2  dup
0xc5f3  ldc.i4.1
0xc5f4  ldloc.s  4
0xc5f6  stelem.ref
0xc5f7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc5fc  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xc601  leave.s  loc_C634
0xc603  stloc.s  5
0xc605  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc60a  ldstr    aClaimsutilityG_0// "\tClaimsUtility.GetSecurityIdentifier f"...
0xc60f  ldc.i4.2
0xc610  newarr   [mscorlib]System.Object
0xc615  dup
0xc616  ldc.i4.0
0xc617  ldloc.0
0xc618  stelem.ref
0xc619  dup
0xc61a  ldc.i4.1
0xc61b  ldloc.s  5
0xc61d  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [System.ServiceModel]System.ServiceModel.ExceptionDetail>::get_Detail()
0xc622  callvirt instance string [System.ServiceModel]System.ServiceModel.ExceptionDetail::get_Message()
0xc627  stelem.ref
0xc628  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc62d  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::LogAccessDenied(string context)
0xc632  leave.s  loc_C634
0xc634  ldnull
0xc635  ret
0xc636  ldloc.3
0xc637  ret
```
