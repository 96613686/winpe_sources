# Microsoft.Crm.Authentication.UserManagementFactory::CreateUser

- ea: `0x10d20`
- end: `0x10e0a`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::CreateUser`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x10d20`
- `0x119b0`
- `0x11bd0`
- `0x11c90`
- `0x11f90`
- `0x12130`

## string_xrefs

- `0x10d83`: `	UserManagementFactory.CreateUser for user {0} : GetUserAuthenticationInformation Completed`
- `0x10dc2`: `	UserManagementFactory.CreateUser for user {0} : CheckUserUnderRootPath Completed`

## pseudocode

```c

```

## disassembly

```asm
0x10d20  ldarg.3
0x10d21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10d26  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::IsClaimsEnabled(valuetype [mscorlib]System.Guid)
0x10d2b  brtrue.s loc_10D30
0x10d2d  ldc.i4.1
0x10d2e  br.s     loc_10D31
0x10d30  ldc.i4.2
0x10d31  stloc.0
0x10d32  ldc.i4.2
0x10d33  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x10d38  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x10d3d  bne.un.s loc_10D41
0x10d3f  ldc.i4.3
0x10d40  stloc.0
0x10d41  ldarg.1
0x10d42  ldstr    aDomainname// "domainname"
0x10d47  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10d4c  brtrue.s loc_10D60
0x10d4e  ldarg.1
0x10d4f  ldstr    aDomainname// "domainname"
0x10d54  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10d59  castclass [mscorlib]System.String
0x10d5e  br.s     loc_10D65
0x10d60  ldstr    aNull// "NULL"
0x10d65  stloc.1
0x10d66  ldarg.0
0x10d67  ldarg.1
0x10d68  ldloc.0
0x10d69  ldarg.3
0x10d6a  call     instance class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation Microsoft.Crm.Authentication.UserManagementFactory::GetUserAuthenticationInformation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, valuetype [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.AuthenticationMode authMode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10d6f  stloc.2
0x10d70  ldloc.2
0x10d71  ldstr    aUserinformatio// "userInformation"
0x10d76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10d7b  ldarg.3
0x10d7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10d81  ldc.i4.s 0x14
0x10d83  ldstr    aUsermanagement// "\tUserManagementFactory.CreateUser for "...
0x10d88  ldc.i4.1
0x10d89  newarr   [mscorlib]System.Object
0x10d8e  dup
0x10d8f  ldc.i4.0
0x10d90  ldloc.1
0x10d91  stelem.ref
0x10d92  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10d97  ldloc.2
0x10d98  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation Microsoft.Crm.Authentication.UserManagementFactory::GetActiveDirectoryInformation(class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation)
0x10d9d  stloc.3
0x10d9e  ldloc.0
0x10d9f  ldc.i4.1
0x10da0  bne.un.s loc_10DD6
0x10da2  ldloc.3
0x10da3  brfalse.s loc_10DD6
0x10da5  ldloc.2
0x10da6  callvirt instance bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_IsValidated()
0x10dab  brfalse.s loc_10DD6
0x10dad  ldarg.0
0x10dae  ldloc.3
0x10daf  callvirt instance string [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_UniqueName()
0x10db4  ldarg.3
0x10db5  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::CheckUserUnderRootPath(string domainAccountName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10dba  ldarg.3
0x10dbb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10dc0  ldc.i4.s 0x14
0x10dc2  ldstr    aUsermanagement_0// "\tUserManagementFactory.CreateUser for "...
0x10dc7  ldc.i4.1
0x10dc8  newarr   [mscorlib]System.Object
0x10dcd  dup
0x10dce  ldc.i4.0
0x10dcf  ldloc.1
0x10dd0  stelem.ref
0x10dd1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10dd6  ldarg.1
0x10dd7  ldloc.2
0x10dd8  ldarg.3
0x10dd9  ldc.i4.1
0x10dda  call     void Microsoft.Crm.Authentication.UserManagementFactory::SetSystemUserAuthenticationInformation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool create)
0x10ddf  ldarg.2
0x10de0  brtrue.s loc_10DEA
0x10de2  ldarg.0
0x10de3  ldloc.2
0x10de4  ldarg.3
0x10de5  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::AddPrincipalToGroup(class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10dea  ldc.i4.2
0x10deb  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x10df0  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x10df5  beq.s    loc_10E08
0x10df7  ldarg.1
0x10df8  ldstr    aInvitestatusco// "invitestatuscode"
0x10dfd  ldc.i4.4
0x10dfe  box      [mscorlib]System.Int32
0x10e03  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x10e08  ldloc.2
0x10e09  ret
```
