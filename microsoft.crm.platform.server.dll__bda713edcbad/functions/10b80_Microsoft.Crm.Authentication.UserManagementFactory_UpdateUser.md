# Microsoft.Crm.Authentication.UserManagementFactory::UpdateUser

- ea: `0x10b80`
- end: `0x10d1e`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::UpdateUser`
- size: `414`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x10b80`
- `0x10ee0`
- `0x12190`
- `0x121a0`

## string_xrefs

- `0x10bb1`: `activedirectoryguid`
- `0x10bc3`: `activedirectoryguid`
- `0x10be0`: `isactivedirectoryuser`
- `0x10bf2`: `isactivedirectoryuser`
- `0x10c15`: `accessmode`
- `0x10c22`: `accessmode`
- `0x10c41`: `accessmode`
- `0x10c4e`: `accessmode`
- `0x10c36`: `accessMode`

## pseudocode

```c

```

## disassembly

```asm
0x10b80  ldarg.2
0x10b81  ldstr    aSystemuserid_0// "systemuserid"
0x10b86  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10b8b  brtrue.s loc_10B9F
0x10b8d  ldarg.2
0x10b8e  ldstr    aSystemuserid_0// "systemuserid"
0x10b93  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10b98  unbox.any [mscorlib]System.Guid
0x10b9d  br.s     loc_10BA4
0x10b9f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10ba4  stloc.0
0x10ba5  ldloc.0
0x10ba6  ldstr    aSystemuserid_1// "systemUserId"
0x10bab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x10bb0  ldarg.1
0x10bb1  ldstr    aActivedirector// "activedirectoryguid"
0x10bb6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10bbb  brtrue.s loc_10BD9
0x10bbd  ldarg.1
0x10bbe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x10bc3  ldstr    aActivedirector// "activedirectoryguid"
0x10bc8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x10bcd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x10bd2  unbox.any [mscorlib]System.Guid
0x10bd7  br.s     loc_10BDE
0x10bd9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10bde  stloc.1
0x10bdf  ldarg.1
0x10be0  ldstr    aIsactivedirect// "isactivedirectoryuser"
0x10be5  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10bea  brtrue.s loc_10C08
0x10bec  ldarg.1
0x10bed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x10bf2  ldstr    aIsactivedirect// "isactivedirectoryuser"
0x10bf7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x10bfc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x10c01  unbox.any [mscorlib]System.Boolean
0x10c06  br.s     loc_10C09
0x10c08  ldc.i4.0
0x10c09  stloc.2
0x10c0a  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_ManageExternalGroups()
0x10c0f  brfalse  loc_10CC7
0x10c14  ldarg.1
0x10c15  ldstr    aAccessmode// "accessmode"
0x10c1a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10c1f  brtrue.s loc_10C33
0x10c21  ldarg.1
0x10c22  ldstr    aAccessmode// "accessmode"
0x10c27  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10c2c  unbox.any [mscorlib]System.Int32
0x10c31  br.s     loc_10C34
0x10c33  ldc.i4.m1
0x10c34  stloc.3
0x10c35  ldloc.3
0x10c36  ldstr    aAccessmode_0// "accessMode"
0x10c3b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x10c40  ldarg.2
0x10c41  ldstr    aAccessmode// "accessmode"
0x10c46  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10c4b  brtrue.s loc_10C5F
0x10c4d  ldarg.2
0x10c4e  ldstr    aAccessmode// "accessmode"
0x10c53  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10c58  unbox.any [mscorlib]System.Int32
0x10c5d  br.s     loc_10C60
0x10c5f  ldloc.3
0x10c60  stloc.s  4
0x10c62  ldloc.s  4
0x10c64  ldloc.3
0x10c65  beq.s    loc_10CC7
0x10c67  ldloc.2
0x10c68  brfalse.s loc_10CC7
0x10c6a  ldloc.1
0x10c6b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10c70  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10c75  brfalse.s loc_10CC7
0x10c77  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x10c7c  ldloc.0
0x10c7d  ldarg.s  6
0x10c7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10c84  ldc.i4.1
0x10c85  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetAuthInfo(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AuthInfoType)
0x10c8a  stloc.s  5
0x10c8c  ldloc.s  5
0x10c8e  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x10c93  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10c98  brtrue.s loc_10CC7
0x10c9a  ldloc.s  5
0x10c9c  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x10ca1  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(string)
0x10ca6  stloc.s  6
0x10ca8  ldc.i4.1
0x10ca9  ldloc.s  4
0x10cab  bne.un.s loc_10CB8
0x10cad  ldarg.0
0x10cae  ldloc.1
0x10caf  ldloc.s  6
0x10cb1  ldarg.s  6
0x10cb3  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::RemovePrincipalFromGroup(valuetype [mscorlib]System.Guid activeDirectoryId, class [mscorlib]System.Security.Principal.SecurityIdentifier identifier, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10cb8  ldc.i4.1
0x10cb9  ldloc.3
0x10cba  bne.un.s loc_10CC7
0x10cbc  ldarg.0
0x10cbd  ldloc.1
0x10cbe  ldloc.s  6
0x10cc0  ldarg.s  6
0x10cc2  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::AddPrincipalToGroup(valuetype [mscorlib]System.Guid activeDirectoryId, class [mscorlib]System.Security.Principal.SecurityIdentifier identifier, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10cc7  ldarg.2
0x10cc8  ldstr    aDomainname// "domainname"
0x10ccd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10cd2  brtrue.s loc_10D1D
0x10cd4  ldarg.1
0x10cd5  ldstr    aDomainname// "domainname"
0x10cda  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10cdf  brtrue.s loc_10D1D
0x10ce1  ldarg.2
0x10ce2  ldstr    aDomainname// "domainname"
0x10ce7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10cec  castclass [mscorlib]System.String
0x10cf1  ldarg.1
0x10cf2  ldstr    aDomainname// "domainname"
0x10cf7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10cfc  castclass [mscorlib]System.String
0x10d01  stloc.s  7
0x10d03  ldloc.s  7
0x10d05  ldc.i4.5
0x10d06  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x10d0b  brfalse.s loc_10D1D
0x10d0d  ldarg.0
0x10d0e  ldarg.1
0x10d0f  ldarg.2
0x10d10  ldarg.3
0x10d11  ldloc.1
0x10d12  ldarg.s  4
0x10d14  ldarg.s  5
0x10d16  ldarg.s  6
0x10d18  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::UpdateDomainName(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity newSystemUser, class Microsoft.Crm.BusinessEntities.BusinessProcessObject systemUserService, valuetype [mscorlib]System.Guid oldActiveDirectoryId, bool usersAlreadyInConfigDatabase, bool provisioning, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10d1d  ret
```
