# Microsoft.Crm.Authentication.UserManagementFactory::AddUserToConfigDatabase

- ea: `0x111d0`
- end: `0x113ae`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::AddUserToConfigDatabase`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10ee0`

## callees

- `0x111d0`
- `0x113b0`
- `0x114d0`
- `0x11720`
- `0x11bd0`

## string_xrefs

- `0x11211`: `issyncwithdirectory`
- `0x1121e`: `issyncwithdirectory`
- `0x112c4`: `DirectoryObjectId`
- `0x112d9`: `DirectoryObjectId`
- `0x11376`: `	UserManagementFactory.AddUserToConfigDB for crmuserid {0} did not have the DirectoryObjectIdPopulated`
- `0x11398`: `	UserManagementFactory.AddUserToConfigDB for user {0} Completed`

## pseudocode

```c

```

## disassembly

```asm
0x111d0  ldarg.1
0x111d1  ldstr    aSystemuser// "systemUser"
0x111d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x111db  ldarg.2
0x111dc  ldstr    aUserinformatio// "userInformation"
0x111e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x111e6  ldarg.3
0x111e7  ldstr    aSystemuserid_1// "systemUserId"
0x111ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x111f1  ldarg.s  5
0x111f3  ldstr    aContext// "context"
0x111f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x111fd  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x11202  ldarg.s  5
0x11204  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11209  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x1120e  brfalse.s loc_11230
0x11210  ldarg.1
0x11211  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x11216  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1121b  brtrue.s loc_11230
0x1121d  ldarg.1
0x1121e  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x11223  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x11228  unbox.any [mscorlib]System.Boolean
0x1122d  brtrue.s loc_11230
0x1122f  ret
0x11230  ldarg.2
0x11231  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation Microsoft.Crm.Authentication.UserManagementFactory::GetActiveDirectoryInformation(class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation)
0x11236  stloc.0
0x11237  ldc.i4.0
0x11238  stloc.1
0x11239  ldloc.0
0x1123a  brfalse.s loc_11266
0x1123c  ldloc.0
0x1123d  callvirt instance bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_IsValidated()
0x11242  brfalse.s loc_11266
0x11244  ldloc.0
0x11245  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_Identifier()
0x1124a  ldstr    aIdentifier// "identifier"
0x1124f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11254  ldarg.0
0x11255  ldarg.1
0x11256  ldarg.3
0x11257  ldloc.0
0x11258  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_Identifier()
0x1125d  ldarg.s  5
0x1125f  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::AddUserToConfigDB(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, valuetype [mscorlib]System.Guid crmId, class [mscorlib]System.Security.Principal.SecurityIdentifier identifier, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x11264  ldc.i4.1
0x11265  stloc.1
0x11266  ldarg.2
0x11267  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_AuthInfo()
0x1126c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.AuthInfoType [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Type()
0x11271  ldc.i4.2
0x11272  bne.un.s loc_112A8
0x11274  ldloc.1
0x11275  brfalse.s loc_1129D
0x11277  ldarg.s  5
0x11279  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1127e  ldarg.3
0x1127f  ldarg.2
0x11280  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_AuthInfo()
0x11285  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x1128a  ldc.i4.1
0x1128b  ldloc.0
0x1128c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_AuthInfo()
0x11291  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x11296  call     void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.CrmPrincipal::AddPrincipalToConfigDB(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, bool, string)
0x1129b  br.s     loc_112A8
0x1129d  ldarg.0
0x1129e  ldarg.1
0x1129f  ldarg.3
0x112a0  ldarg.2
0x112a1  ldarg.s  5
0x112a3  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::AddUserToConfigDB(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemUser, valuetype [mscorlib]System.Guid crmId, class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation, class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context)
0x112a8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x112ad  ldarg.s  5
0x112af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x112b4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x112b9  brfalse  loc_1138F
0x112be  ldarg.2
0x112bf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_Properties()
0x112c4  ldstr    aDirectoryobjec// "DirectoryObjectId"
0x112c9  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x112ce  brfalse  loc_1138F
0x112d3  ldarg.2
0x112d4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_Properties()
0x112d9  ldstr    aDirectoryobjec// "DirectoryObjectId"
0x112de  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x112e3  unbox.any [mscorlib]System.Guid
0x112e8  stloc.2
0x112e9  ldarg.2
0x112ea  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_Properties()
0x112ef  ldstr    aAuthinfo// "authinfo"
0x112f4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x112f9  brfalse.s loc_11317
0x112fb  ldarg.2
0x112fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_Properties()
0x11301  ldstr    aAuthinfo// "authinfo"
0x11306  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1130b  castclass [mscorlib]System.String
0x11310  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x11315  brfalse.s loc_11324
0x11317  ldarg.2
0x11318  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_AuthInfo()
0x1131d  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x11322  br.s     loc_11339
0x11324  ldarg.2
0x11325  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_Properties()
0x1132a  ldstr    aAuthinfo// "authinfo"
0x1132f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x11334  castclass [mscorlib]System.String
0x11339  stloc.3
0x1133a  ldloc.3
0x1133b  ldstr    aAuthinfo_0// "authInfo"
0x11340  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x11345  ldarg.s  5
0x11347  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1134c  ldarg.3
0x1134d  ldloc.3
0x1134e  ldloc.2
0x1134f  call     void [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.CrmPrincipal::AddPrincipalToConfigDB(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x11354  ldloc.2
0x11355  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1135a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1135f  brfalse.s loc_1136D
0x11361  ldarg.0
0x11362  ldarg.s  5
0x11364  ldarg.3
0x11365  ldloc.2
0x11366  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::UpdateDirectoryObjectId(class Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid systemUserId, valuetype [mscorlib]System.Guid directoryObjectId)
0x1136b  br.s     loc_1138F
0x1136d  ldarg.s  5
0x1136f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11374  ldc.i4.s 0x14
0x11376  ldstr    aUsermanagement_3// "\tUserManagementFactory.AddUserToConfig"...
0x1137b  ldc.i4.1
0x1137c  newarr   [mscorlib]System.Object
0x11381  dup
0x11382  ldc.i4.0
0x11383  ldarg.3
0x11384  box      [mscorlib]System.Guid
0x11389  stelem.ref
0x1138a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1138f  ldarg.s  5
0x11391  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11396  ldc.i4.s 0x14
0x11398  ldstr    aUsermanagement_4// "\tUserManagementFactory.AddUserToConfig"...
0x1139d  ldc.i4.1
0x1139e  newarr   [mscorlib]System.Object
0x113a3  dup
0x113a4  ldc.i4.0
0x113a5  ldarg.s  4
0x113a7  stelem.ref
0x113a8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x113ad  ret
```
