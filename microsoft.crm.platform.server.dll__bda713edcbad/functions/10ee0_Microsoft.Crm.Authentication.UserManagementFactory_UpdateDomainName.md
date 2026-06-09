# Microsoft.Crm.Authentication.UserManagementFactory::UpdateDomainName

- ea: `0x10ee0`
- end: `0x11143`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::UpdateDomainName`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x10b80`

## callees

- `0x108f0`
- `0x10e20`
- `0x10ee0`
- `0x11150`
- `0x111a0`
- `0x111d0`
- `0x119b0`
- `0x11c90`
- `0x120e0`
- `0x12130`

## string_xrefs

- `0x10ee1`: `systemUserService`
- `0x10f99`: `azureactivedirectoryobjectid`
- `0x10fa6`: `azureactivedirectoryobjectid`
- `0x10feb`: `azureactivedirectoryobjectid`
- `0x11066`: `	UserManagementFactory.UpdateUser for user {0} : User's domain name is not valid anymore`
- `0x110ec`: `	UserManagementFactory.UpdateUser for user {0} : User's domain name is not valid anymore`

## pseudocode

```c

```

## disassembly

```asm
0x10ee0  ldarg.3
0x10ee1  ldstr    aSystemuserserv// "systemUserService"
0x10ee6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10eeb  ldarg.3
0x10eec  isinst   Microsoft.Crm.Authentication.IUserManagement
0x10ef1  stloc.0
0x10ef2  ldloc.0
0x10ef3  ldstr    aUsermanagement_1// "userManagementInterface"
0x10ef8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10efd  ldarg.2
0x10efe  ldstr    aSystemuserid_0// "systemuserid"
0x10f03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10f08  unbox.any [mscorlib]System.Guid
0x10f0d  stloc.1
0x10f0e  ldarg.2
0x10f0f  ldstr    aIsdisabled// "isdisabled"
0x10f14  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10f19  brtrue.s loc_10F2D
0x10f1b  ldarg.2
0x10f1c  ldstr    aIsdisabled// "isdisabled"
0x10f21  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10f26  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x10f2b  br.s     loc_10F37
0x10f2d  ldloca.s 7
0x10f2f  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x10f35  ldloc.s  7
0x10f37  stloc.2
0x10f38  ldarg.1
0x10f39  ldstr    aIsdisabled// "isdisabled"
0x10f3e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10f43  brtrue.s loc_10F57
0x10f45  ldarg.1
0x10f46  ldstr    aIsdisabled// "isdisabled"
0x10f4b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10f50  unbox.any [mscorlib]System.Boolean
0x10f55  br.s     loc_10F58
0x10f57  ldc.i4.0
0x10f58  brfalse.s loc_10F78
0x10f5a  ldloc.2
0x10f5b  stloc.s  7
0x10f5d  ldc.i4.0
0x10f5e  stloc.s  8
0x10f60  ldloca.s 7
0x10f62  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x10f67  ldloc.s  8
0x10f69  ceq
0x10f6b  ldloca.s 7
0x10f6d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x10f72  and
0x10f73  ldc.i4.0
0x10f74  ceq
0x10f76  br.s     loc_10F79
0x10f78  ldc.i4.0
0x10f79  stloc.3
0x10f7a  ldc.i4.2
0x10f7b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x10f80  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x10f85  bne.un   loc_11010
0x10f8a  ldarg.s  6
0x10f8c  brfalse.s loc_10F8F
0x10f8e  ret
0x10f8f  ldarg.s  7
0x10f91  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10f96  stloc.s  9
0x10f98  ldarg.1
0x10f99  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x10f9e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10fa3  brtrue.s loc_10FB7
0x10fa5  ldarg.1
0x10fa6  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x10fab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10fb0  unbox.any [mscorlib]System.Guid
0x10fb5  br.s     loc_10FBC
0x10fb7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10fbc  stloc.s  0xA
0x10fbe  ldloc.s  0xA
0x10fc0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10fc5  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10fca  brtrue.s loc_10FD7
0x10fcc  ldloc.s  9
0x10fce  ldloc.s  0xA
0x10fd0  call     bool Microsoft.Crm.Authentication.GraphUserHelper::IsUserHardDeleted(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid aadObjectId)
0x10fd5  br.s     loc_10FD8
0x10fd7  ldc.i4.1
0x10fd8  stloc.s  0xB
0x10fda  ldloc.3
0x10fdb  ldloc.s  0xB
0x10fdd  and
0x10fde  brfalse.s loc_11000
0x10fe0  ldarg.0
0x10fe1  ldloc.1
0x10fe2  ldloc.0
0x10fe3  ldarg.s  7
0x10fe5  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::CheckDomainNameChangeAllowed(valuetype [mscorlib]System.Guid systemUserId, class Microsoft.Crm.Authentication.IUserManagement userManagementInterface, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10fea  ldarg.2
0x10feb  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x10ff0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10ff5  box      [mscorlib]System.Guid
0x10ffa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x10fff  ret
0x11000  ldstr    aDomainNameChan// "domain name change is not supported"
0x11005  ldc.i4   0x80048405
0x1100a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1100f  throw
0x11010  ldarg.s  7
0x11012  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11017  call     bool [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::IsClaimsEnabled(valuetype [mscorlib]System.Guid)
0x1101c  brtrue.s loc_11021
0x1101e  ldc.i4.1
0x1101f  br.s     loc_11022
0x11021  ldc.i4.2
0x11022  stloc.s  4
0x11024  ldarg.s  6
0x11026  brtrue.s loc_11032
0x11028  ldarg.0
0x11029  ldloc.1
0x1102a  ldloc.0
0x1102b  ldarg.s  7
0x1102d  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::CheckDomainNameChangeAllowed(valuetype [mscorlib]System.Guid systemUserId, class Microsoft.Crm.Authentication.IUserManagement userManagementInterface, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x11032  ldarg.2
0x11033  ldstr    aDomainname// "domainname"
0x11038  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1103d  castclass [mscorlib]System.String
0x11042  stloc.s  5
0x11044  ldnull
0x11045  stloc.s  6
0x11047  ldarg.0
0x11048  ldarg.2
0x11049  ldloc.s  4
0x1104b  ldarg.s  7
0x1104d  call     instance class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation Microsoft.Crm.Authentication.UserManagementFactory::GetUserAuthenticationInformation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, valuetype [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.AuthenticationMode authMode, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x11052  stloc.s  6
0x11054  leave    loc_11142
0x11059  pop
0x1105a  ldloc.3
0x1105b  brfalse.s loc_11081
0x1105d  ldarg.s  7
0x1105f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11064  ldc.i4.s 0x14
0x11066  ldstr    aUsermanagement_2// "\tUserManagementFactory.UpdateUser for "...
0x1106b  ldc.i4.1
0x1106c  newarr   [mscorlib]System.Object
0x11071  dup
0x11072  ldc.i4.0
0x11073  ldloc.1
0x11074  box      [mscorlib]System.Guid
0x11079  stelem.ref
0x1107a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1107f  br.s     loc_11083
0x11081  rethrow
0x11083  leave    loc_11142
0x11088  ldloc.s  6
0x1108a  brfalse.s loc_110E0
0x1108c  ldloc.s  6
0x1108e  callvirt instance bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_IsValidated()
0x11093  brfalse.s loc_110E0
0x11095  ldarg.s  5
0x11097  brtrue.s loc_110A6
0x11099  ldarg.0
0x1109a  ldloc.1
0x1109b  ldloc.s  6
0x1109d  ldarg.3
0x1109e  ldarg.s  7
0x110a0  ldc.i4.0
0x110a1  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::CheckUserDoesNotExist(valuetype [mscorlib]System.Guid systemUserId, class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation, class Microsoft.Crm.BusinessEntities.BusinessProcessObject systemUserService, class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool ignoreCurrentOrgUser)
0x110a6  ldarg.0
0x110a7  ldloc.1
0x110a8  ldarg.s  4
0x110aa  ldarg.s  7
0x110ac  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::RemoveADUserFromGroups(valuetype [mscorlib]System.Guid systemUserId, valuetype [mscorlib]System.Guid oldActiveDirectoryGuid, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x110b1  ldarg.0
0x110b2  ldarg.2
0x110b3  ldloc.1
0x110b4  ldarg.s  7
0x110b6  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::RemoveUserFromConfigDB(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, valuetype [mscorlib]System.Guid crmId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x110bb  ldarg.2
0x110bc  ldloc.s  6
0x110be  ldarg.s  7
0x110c0  ldc.i4.0
0x110c1  call     void Microsoft.Crm.Authentication.UserManagementFactory::SetSystemUserAuthenticationInformation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool create)
0x110c6  ldarg.0
0x110c7  ldloc.s  6
0x110c9  ldarg.s  7
0x110cb  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::AddPrincipalToGroup(class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x110d0  ldarg.0
0x110d1  ldarg.2
0x110d2  ldloc.s  6
0x110d4  ldloc.1
0x110d5  ldloc.s  5
0x110d7  ldarg.s  7
0x110d9  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::AddUserToConfigDatabase(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation, valuetype [mscorlib]System.Guid systemUserId, string traceDomainName, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x110de  br.s     loc_11141
0x110e0  ldloc.3
0x110e1  brfalse.s loc_11107
0x110e3  ldarg.s  7
0x110e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x110ea  ldc.i4.s 0x14
0x110ec  ldstr    aUsermanagement_2// "\tUserManagementFactory.UpdateUser for "...
0x110f1  ldc.i4.1
0x110f2  newarr   [mscorlib]System.Object
0x110f7  dup
0x110f8  ldc.i4.0
0x110f9  ldloc.1
0x110fa  box      [mscorlib]System.Guid
0x110ff  stelem.ref
0x11100  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11105  br.s     loc_11141
0x11107  ldloc.s  4
0x11109  ldc.i4.1
0x1110a  bne.un.s loc_1111C
0x1110c  ldstr    aDomainNameDoes// "domain name does not exist"
0x11111  ldc.i4   0x80041D2A
0x11116  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1111b  throw
0x1111c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11121  ldstr    aTheDomainLogon// "The domain logon for this user is inval"...
0x11126  ldc.i4.1
0x11127  newarr   [mscorlib]System.Object
0x1112c  dup
0x1112d  ldc.i4.0
0x1112e  ldloc.s  5
0x11130  stelem.ref
0x11131  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11136  ldc.i4   0x80048015
0x1113b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x11140  throw
0x11141  endfinally
0x11142  ret
```
