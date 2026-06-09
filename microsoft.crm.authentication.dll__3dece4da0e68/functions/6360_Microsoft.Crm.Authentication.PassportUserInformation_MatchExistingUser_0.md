# Microsoft.Crm.Authentication.PassportUserInformation::MatchExistingUser_0

- ea: `0x6360`
- end: `0x63f7`
- name: `Microsoft.Crm.Authentication.PassportUserInformation::MatchExistingUser_0`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6320`

## callees

- `0x1580`
- `0x15a0`
- `0x5640`
- `0x5b50`
- `0x62e0`
- `0x6360`

## string_xrefs

- `0x63ce`: `	PassportUserInformation.MatchExistingUser for user {0} : AddUserToConfigDB Completed`

## pseudocode

```c

```

## disassembly

```asm
0x6360  ldloca.s 0
0x6362  initobj  Microsoft.Crm.Authentication.CrmUserInfo
0x6368  ldarg.1
0x6369  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x636e  brtrue.s loc_637D
0x6370  ldarg.0
0x6371  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6376  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x637b  brfalse.s loc_637F
0x637d  ldloc.0
0x637e  ret
0x637f  ldarg.1
0x6380  call     string Microsoft.Crm.Authentication.UserAuthenticationInformation::RemoveTokenPrefix(string userAuth)
0x6385  stloc.1
0x6386  ldloc.1
0x6387  ldstr    asc_1A39C// "@"
0x638c  ldc.i4.5
0x638d  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x6392  stloc.2
0x6393  ldloc.2
0x6394  ldc.i4.m1
0x6395  ble.s    loc_639F
0x6397  ldloc.1
0x6398  ldloc.2
0x6399  callvirt instance string [mscorlib]System.String::Remove(int32)
0x639e  stloc.1
0x639f  ldloc.1
0x63a0  call     string Microsoft.Crm.Authentication.PassportUserInformation::GetUserToken(string userPrincipalName)
0x63a5  stloc.3
0x63a6  ldloc.3
0x63a7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x63ac  brtrue.s loc_63F5
0x63ae  ldarg.2
0x63af  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x63b4  ldarg.0
0x63b5  ldloc.3
0x63b6  ldloca.s 4
0x63b8  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::TryGetCrmUserId(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid&)
0x63bd  brfalse.s loc_63F5
0x63bf  ldarg.0
0x63c0  ldloc.s  4
0x63c2  ldarg.1
0x63c3  ldc.i4.1
0x63c4  ldloc.3
0x63c5  ldarg.2
0x63c6  call     void Microsoft.Crm.Authentication.CrmPrincipal::AddPrincipalToConfigDB(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid crmId, string authInfo, bool duplicate, string originalAuthInfo, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x63cb  ldarg.0
0x63cc  ldc.i4.s 0x16
0x63ce  ldstr    aPassportuserin// "\tPassportUserInformation.MatchExisting"...
0x63d3  ldc.i4.1
0x63d4  newarr   [mscorlib]System.Object
0x63d9  dup
0x63da  ldc.i4.0
0x63db  ldloc.3
0x63dc  stelem.ref
0x63dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63e2  ldloca.s 0
0x63e4  ldarg.0
0x63e5  call     instance void Microsoft.Crm.Authentication.CrmUserInfo::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x63ea  ldloca.s 0
0x63ec  ldloc.s  4
0x63ee  call     instance void Microsoft.Crm.Authentication.CrmUserInfo::set_UserId(valuetype [mscorlib]System.Guid value)
0x63f3  ldloc.0
0x63f4  ret
0x63f5  ldloc.0
0x63f6  ret
```
