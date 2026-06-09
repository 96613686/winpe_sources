# Microsoft.Crm.Authentication.UserManagementFactory::SetExternalGroupMembership

- ea: `0x10ac0`
- end: `0x10b78`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::SetExternalGroupMembership`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x10ac0`
- `0x12190`
- `0x121a0`

## string_xrefs

- `0x10acb`: `activedirectoryguid`
- `0x10add`: `activedirectoryguid`
- `0x10afa`: `isactivedirectoryuser`
- `0x10b0c`: `isactivedirectoryuser`

## pseudocode

```c

```

## disassembly

```asm
0x10ac0  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_ManageExternalGroups()
0x10ac5  brfalse  loc_10B77
0x10aca  ldarg.1
0x10acb  ldstr    aActivedirector// "activedirectoryguid"
0x10ad0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10ad5  brtrue.s loc_10AF3
0x10ad7  ldarg.1
0x10ad8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x10add  ldstr    aActivedirector// "activedirectoryguid"
0x10ae2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x10ae7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x10aec  unbox.any [mscorlib]System.Guid
0x10af1  br.s     loc_10AF8
0x10af3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10af8  stloc.0
0x10af9  ldarg.1
0x10afa  ldstr    aIsactivedirect// "isactivedirectoryuser"
0x10aff  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x10b04  brtrue.s loc_10B22
0x10b06  ldarg.1
0x10b07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x10b0c  ldstr    aIsactivedirect// "isactivedirectoryuser"
0x10b11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x10b16  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x10b1b  unbox.any [mscorlib]System.Boolean
0x10b20  br.s     loc_10B23
0x10b22  ldc.i4.0
0x10b23  brfalse.s loc_10B77
0x10b25  ldloc.0
0x10b26  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10b2b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10b30  brfalse.s loc_10B77
0x10b32  call     class [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.UserInfoProvider::get_Instance()
0x10b37  ldarg.2
0x10b38  ldarg.s  4
0x10b3a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10b3f  ldc.i4.1
0x10b40  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo [Microsoft.Crm.Core]Microsoft.Crm.IUserInfoProvider::GetAuthInfo(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.AuthInfoType)
0x10b45  stloc.1
0x10b46  ldloc.1
0x10b47  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x10b4c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10b51  brtrue.s loc_10B77
0x10b53  ldloc.1
0x10b54  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.AuthInfo::get_Value()
0x10b59  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(string)
0x10b5e  stloc.2
0x10b5f  ldarg.3
0x10b60  brtrue.s loc_10B6D
0x10b62  ldarg.0
0x10b63  ldloc.0
0x10b64  ldloc.2
0x10b65  ldarg.s  4
0x10b67  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::RemovePrincipalFromGroup(valuetype [mscorlib]System.Guid activeDirectoryId, class [mscorlib]System.Security.Principal.SecurityIdentifier identifier, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10b6c  ret
0x10b6d  ldarg.0
0x10b6e  ldloc.0
0x10b6f  ldloc.2
0x10b70  ldarg.s  4
0x10b72  call     instance void Microsoft.Crm.Authentication.UserManagementFactory::AddPrincipalToGroup(valuetype [mscorlib]System.Guid activeDirectoryId, class [mscorlib]System.Security.Principal.SecurityIdentifier identifier, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10b77  ret
```
