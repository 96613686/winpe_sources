# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveAdministratorUsersInfo

- ea: `0x1cf40`
- end: `0x1cf87`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::RetrieveAdministratorUsersInfo`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1ce60`

## callees

- `0x1cf40`
- `0x1d040`

## string_xrefs

- `0x1cf4b`: `SELECT SUB.FirstName, SUB.LastName, SUB.InternalEmailAddress, SUB.WindowsLiveId, USB.UILanguageId, OB.LanguageCode, SUB.SystemUserId \n									FROM SystemUserBase as SUB, SystemUserRoles as SUR, UserSettingsBase USB, OrganizationBase OB \n									WHERE {0}\n										OB.OrganizationId = @OrganizationId\n										AND SUB.IsDisabled = 0\n										AND SUB.SystemUserId = SUR.SystemUserId\n										AND SUB.SystemUserId = USB.SystemUserId\n										AND SUR.RoleId in (SELECT RB.RoleId FROM`
- `0x1cf65`: `SUB.InviteStatusCode = @UserInvitationStatus AND SUB.AccessMode != 3 AND`
- `0x1cf6c`: `SUB.IsSyncWithDirectory =1 AND`

## pseudocode

```c

```

## disassembly

```asm
0x1cf40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::.ctor()
0x1cf45  stloc.0
0x1cf46  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1cf4b  ldstr    aSelectSubFirst// "SELECT SUB.FirstName, SUB.LastName, SUB"...
0x1cf50  ldc.i4.1
0x1cf51  newarr   [mscorlib]System.Object
0x1cf56  dup
0x1cf57  ldc.i4.0
0x1cf58  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x1cf5d  ldarg.1
0x1cf5e  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x1cf63  brtrue.s loc_1CF6C
0x1cf65  ldstr    aSubInvitestatu// "SUB.InviteStatusCode = @UserInvitationS"...
0x1cf6a  br.s     loc_1CF71
0x1cf6c  ldstr    aSubIssyncwithd// "SUB.IsSyncWithDirectory =1 AND"
0x1cf71  stelem.ref
0x1cf72  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1cf77  stloc.1
0x1cf78  ldarg.1
0x1cf79  ldloc.0
0x1cf7a  ldloc.1
0x1cf7b  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::ReadFromOrganizationDatabase(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo> userEmailInfo, string sqlCommand)
0x1cf80  ldloc.0
0x1cf81  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::ToArray()
0x1cf86  ret
```
