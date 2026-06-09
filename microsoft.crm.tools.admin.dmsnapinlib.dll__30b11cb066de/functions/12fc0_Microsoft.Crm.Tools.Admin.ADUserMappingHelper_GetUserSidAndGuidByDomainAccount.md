# Microsoft.Crm.Tools.Admin.ADUserMappingHelper::GetUserSidAndGuidByDomainAccount

- ea: `0x12fc0`
- end: `0x130c3`
- name: `Microsoft.Crm.Tools.Admin.ADUserMappingHelper::GetUserSidAndGuidByDomainAccount`
- size: `259`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x12620`
- `0x12e70`
- `0x130e0`

## callees

- `0x12fc0`

## string_xrefs

- `0x13016`: `User cannot be added to Active Directory as a foreign security principal: {0}`
- `0x130b2`: `Failed while trying to get user Sid and Guid from domain account`

## pseudocode

```c

```

## disassembly

```asm
0x12fc0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12fc5  stloc.0
0x12fc6  ldarg.0
0x12fc7  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x12fcc  ldc.i4.1
0x12fcd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetUserId(string, bool)
0x12fd2  stloc.0
0x12fd3  leave.s  loc_12FD8
0x12fd5  pop
0x12fd6  leave.s  loc_12FD8
0x12fd8  nop
0x12fd9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12fde  ldloc.0
0x12fdf  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12fe4  brfalse.s loc_13040
0x12fe6  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::.ctor()
0x12feb  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::GetSecurityGroups()
0x12ff0  stloc.3
0x12ff1  ldarg.0
0x12ff2  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x12ff7  ldloc.3
0x12ff8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x12ffd  ldc.i4.1
0x12ffe  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::AddPrincipalToGroupByName(string, valuetype [mscorlib]System.Guid, bool)
0x13003  stloc.0
0x13004  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13009  ldloc.0
0x1300a  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1300f  brfalse.s loc_13040
0x13011  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13016  ldstr    aUserCannotBeAd// "User cannot be added to Active Director"...
0x1301b  ldc.i4.1
0x1301c  newarr   [mscorlib]System.Object
0x13021  dup
0x13022  ldc.i4.0
0x13023  ldarg.0
0x13024  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x13029  stelem.ref
0x1302a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1302f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x13034  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchExceptionError::.ctor(class [mscorlib]System.Exception)
0x13039  stloc.s  4
0x1303b  leave    loc_130C0
0x13040  ldarg.0
0x13041  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x13046  call     unsigned int8[] [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetSidFromAccount(string)
0x1304b  stloc.1
0x1304c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::.ctor()
0x13051  stloc.2
0x13052  ldloc.2
0x13053  ldarg.0
0x13054  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADDomainAccount(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount)
0x13059  ldloc.2
0x1305a  ldarg.0
0x1305b  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x13060  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADCommonName(string)
0x13065  ldloc.2
0x13066  ldloc.0
0x13067  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_ADObjectGuid(valuetype [mscorlib]System.Guid)
0x1306c  ldloc.2
0x1306d  ldloc.1
0x1306e  ldc.i4.0
0x1306f  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(unsigned int8[], int32)
0x13074  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User::set_UserSid(class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x13079  ldstr    aUnableToFetchN// "Unable to fetch name related informatio"...
0x1307e  ldc.i4.1
0x1307f  newarr   [mscorlib]System.Object
0x13084  dup
0x13085  ldc.i4.0
0x13086  ldarg.0
0x13087  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.DomainAccount::get_DomainAndAccount()
0x1308c  stelem.ref
0x1308d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x13092  ldloc.2
0x13093  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchSuccess::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User)
0x13098  stloc.s  4
0x1309a  leave.s  loc_130C0
0x1309c  stloc.s  5
0x1309e  ldloc.s  5
0x130a0  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException
0x130a5  brfalse.s loc_130B2
0x130a7  ldloc.s  5
0x130a9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.SearchExceptionError::.ctor(class [mscorlib]System.Exception)
0x130ae  stloc.s  4
0x130b0  leave.s  loc_130C0
0x130b2  ldstr    aFailedWhileTry// "Failed while trying to get user Sid and"...
0x130b7  ldloc.s  5
0x130b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteError(string, class [mscorlib]System.Exception)
0x130be  rethrow
0x130c0  ldloc.s  4
0x130c2  ret
```
