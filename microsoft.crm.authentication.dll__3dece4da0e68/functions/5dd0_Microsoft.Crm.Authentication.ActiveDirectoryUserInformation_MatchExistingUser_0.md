# Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::MatchExistingUser_0

- ea: `0x5dd0`
- end: `0x5e48`
- name: `Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::MatchExistingUser_0`
- size: `120`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3120`
- `0xca00`
- `0xcd40`
- `0xea80`

## callees

- `0x55e0`
- `0x5c70`
- `0x5dd0`

## string_xrefs

- `0x5e30`: `	ActiveDirectoryUserInformation.MatchExistingUser for user {0} : AddUserToConfigDB Completed`

## pseudocode

```c

```

## disassembly

```asm
0x5dd0  ldarg.0
0x5dd1  ldstr    aPrincipal// "principal"
0x5dd6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5ddb  ldarg.1
0x5ddc  ldstr    aUserauth// "userAuth"
0x5de1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x5de6  ldnull
0x5de7  stloc.0
0x5de8  ldarg.0
0x5de9  call     string [Microsoft.Crm.Core]IdentityExtensions::GetActiveDirectorySecurityIdentifier(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x5dee  stloc.1
0x5def  ldloc.1
0x5df0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5df5  brtrue.s loc_5DFE
0x5df7  ldloc.1
0x5df8  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(string)
0x5dfd  stloc.0
0x5dfe  ldloc.0
0x5dff  ldnull
0x5e00  call     bool [mscorlib]System.Security.Principal.SecurityIdentifier::op_Inequality(class [mscorlib]System.Security.Principal.SecurityIdentifier, class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x5e05  brfalse.s loc_5E46
0x5e07  ldloc.0
0x5e08  call     string Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::GetUserToken(class [mscorlib]System.Security.Principal.SecurityIdentifier sid)
0x5e0d  stloc.2
0x5e0e  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::.ctor()
0x5e13  ldloc.2
0x5e14  ldc.i4.1
0x5e15  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveByPuid(string, bool)
0x5e1a  stloc.3
0x5e1b  ldloc.3
0x5e1c  brfalse.s loc_5E46
0x5e1e  ldloc.3
0x5e1f  ldlen
0x5e20  brfalse.s loc_5E46
0x5e22  ldarg.1
0x5e23  ldloc.2
0x5e24  call     void Microsoft.Crm.Authentication.CrmPrincipal::AddAuthenticationCredentialToConfigDB(string authInfo, string originalAuthInfo)
0x5e29  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5e2e  ldc.i4.s 0x16
0x5e30  ldstr    aActivedirector// "\tActiveDirectoryUserInformation.MatchE"...
0x5e35  ldc.i4.1
0x5e36  newarr   [mscorlib]System.Object
0x5e3b  dup
0x5e3c  ldc.i4.0
0x5e3d  ldarg.1
0x5e3e  stelem.ref
0x5e3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5e44  ldc.i4.1
0x5e45  ret
0x5e46  ldc.i4.0
0x5e47  ret
```
