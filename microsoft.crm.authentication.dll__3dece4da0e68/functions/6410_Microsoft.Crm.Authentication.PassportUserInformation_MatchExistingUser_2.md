# Microsoft.Crm.Authentication.PassportUserInformation::MatchExistingUser_2

- ea: `0x6410`
- end: `0x6486`
- name: `Microsoft.Crm.Authentication.PassportUserInformation::MatchExistingUser_2`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3120`
- `0x6400`

## callees

- `0x55f0`
- `0x5b50`
- `0x62e0`
- `0x6410`

## string_xrefs

- `0x646e`: `	PassportUserInformation.MatchExistingUser for user {0} : AddUserToConfigDB Completed`

## pseudocode

```c

```

## disassembly

```asm
0x6410  ldarg.0
0x6411  ldstr    aUserauth// "userAuth"
0x6416  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x641b  ldarg.0
0x641c  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix(string userAuth)
0x6421  stloc.0
0x6422  ldloc.0
0x6423  ldstr    asc_1A39C// "@"
0x6428  ldc.i4.5
0x6429  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x642e  stloc.1
0x642f  ldloc.1
0x6430  ldc.i4.m1
0x6431  ble.s    loc_643B
0x6433  ldloc.0
0x6434  ldloc.1
0x6435  callvirt instance string [mscorlib]System.String::Remove(int32)
0x643a  stloc.0
0x643b  ldloc.0
0x643c  call     string Microsoft.Crm.Authentication.PassportUserInformation::GetUserToken(string userPrincipalName)
0x6441  stloc.2
0x6442  ldloc.2
0x6443  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6448  brtrue.s loc_6484
0x644a  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::.ctor()
0x644f  ldloc.2
0x6450  ldc.i4.1
0x6451  ldarg.1
0x6452  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ConfigDBSecurity.SystemUserService::RetrieveByPuid(string, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x6457  stloc.3
0x6458  ldloc.3
0x6459  brfalse.s loc_6484
0x645b  ldloc.3
0x645c  ldlen
0x645d  brfalse.s loc_6484
0x645f  ldarg.0
0x6460  ldloc.2
0x6461  ldarg.1
0x6462  call     void Microsoft.Crm.Authentication.CrmPrincipal::AddAuthenticationCredentialToConfigDB(string authInfo, string originalAuthInfo, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x6467  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x646c  ldc.i4.s 0x16
0x646e  ldstr    aPassportuserin// "\tPassportUserInformation.MatchExisting"...
0x6473  ldc.i4.1
0x6474  newarr   [mscorlib]System.Object
0x6479  dup
0x647a  ldc.i4.0
0x647b  ldarg.0
0x647c  stelem.ref
0x647d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6482  ldc.i4.1
0x6483  ret
0x6484  ldc.i4.0
0x6485  ret
```
