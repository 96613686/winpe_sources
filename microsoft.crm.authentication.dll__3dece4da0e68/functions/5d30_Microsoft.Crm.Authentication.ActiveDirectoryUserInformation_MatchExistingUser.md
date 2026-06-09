# Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::MatchExistingUser

- ea: `0x5d30`
- end: `0x5dcb`
- name: `Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::MatchExistingUser`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3950`

## callees

- `0x1580`
- `0x15a0`
- `0x5610`
- `0x5b50`
- `0x5c70`
- `0x5d30`
- `0xc580`

## string_xrefs

- `0x5da2`: `	ActiveDirectoryUserInformation.MatchExistingUser for user {0} : AddUserToConfigDB Completed`

## pseudocode

```c

```

## disassembly

```asm
0x5d30  ldloca.s 0
0x5d32  initobj  Microsoft.Crm.Authentication.CrmUserInfo
0x5d38  ldarg.0
0x5d39  brfalse.s loc_5D50
0x5d3b  ldarg.2
0x5d3c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5d41  brtrue.s loc_5D50
0x5d43  ldarg.1
0x5d44  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5d49  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5d4e  brfalse.s loc_5D52
0x5d50  ldloc.0
0x5d51  ret
0x5d52  ldarg.2
0x5d53  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix(string userAuth)
0x5d58  stloc.1
0x5d59  ldnull
0x5d5a  stloc.2
0x5d5b  ldarg.0
0x5d5c  call     string Microsoft.Crm.Authentication.Claims.ClaimsUtility::GetSecurityIdentifier(class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x5d61  stloc.3
0x5d62  ldloc.3
0x5d63  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5d68  brtrue.s loc_5D71
0x5d6a  ldloc.3
0x5d6b  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(string)
0x5d70  stloc.2
0x5d71  ldloc.2
0x5d72  ldnull
0x5d73  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Inequality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x5d78  brfalse.s loc_5DC9
0x5d7a  ldloc.2
0x5d7b  call     string Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::GetUserToken(class [mscorlib]System.Security.Principal.SecurityIdentifier sid)
0x5d80  stloc.s  4
0x5d82  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x5d87  ldarg.1
0x5d88  ldloc.s  4
0x5d8a  ldloca.s 5
0x5d8c  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::TryGetCrmUserId(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid&)
0x5d91  brfalse.s loc_5DC9
0x5d93  ldarg.1
0x5d94  ldloc.s  5
0x5d96  ldarg.2
0x5d97  ldc.i4.1
0x5d98  ldloc.s  4
0x5d9a  call     void Microsoft.Crm.Authentication.CrmPrincipal::AddPrincipalToConfigDB(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmId, string authInfo, bool duplicate, string originalAuthInfo)
0x5d9f  ldarg.1
0x5da0  ldc.i4.s 0x16
0x5da2  ldstr    aActivedirector// "\tActiveDirectoryUserInformation.MatchE"...
0x5da7  ldc.i4.1
0x5da8  newarr   [mscorlib]System.Object
0x5dad  dup
0x5dae  ldc.i4.0
0x5daf  ldloc.1
0x5db0  stelem.ref
0x5db1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5db6  ldloca.s 0
0x5db8  ldarg.1
0x5db9  call     instance void Microsoft.Crm.Authentication.CrmUserInfo::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x5dbe  ldloca.s 0
0x5dc0  ldloc.s  5
0x5dc2  call     instance void Microsoft.Crm.Authentication.CrmUserInfo::set_UserId(valuetype [mscorlib]System.Guid value)
0x5dc7  ldloc.0
0x5dc8  ret
0x5dc9  ldloc.0
0x5dca  ret
```
