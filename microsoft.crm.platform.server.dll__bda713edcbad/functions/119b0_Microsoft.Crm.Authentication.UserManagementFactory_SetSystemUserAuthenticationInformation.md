# Microsoft.Crm.Authentication.UserManagementFactory::SetSystemUserAuthenticationInformation

- ea: `0x119b0`
- end: `0x11b03`
- name: `Microsoft.Crm.Authentication.UserManagementFactory::SetSystemUserAuthenticationInformation`
- size: `339`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10d20`
- `0x10ee0`

## callees

- `0x119b0`
- `0x11b10`
- `0x11bd0`

## string_xrefs

- `0x119f5`: `activedirectoryguid`
- `0x119e4`: `isactivedirectoryuser`
- `0x11a62`: `accessmode`
- `0x11ab4`: `azureactivedirectoryobjectid`
- `0x11ac1`: `azureactivedirectoryobjectid`
- `0x11ada`: `azureactivedirectoryobjectid`
- `0x11a41`: `issyncwithdirectory`
- `0x11a4e`: `issyncwithdirectory`
- `0x11af1`: `DirectoryObjectId`

## pseudocode

```c

```

## disassembly

```asm
0x119b0  ldarg.1
0x119b1  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation Microsoft.Crm.Authentication.UserManagementFactory::GetActiveDirectoryInformation(class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation userInformation)
0x119b6  stloc.0
0x119b7  ldc.i4.0
0x119b8  stloc.1
0x119b9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x119be  stloc.2
0x119bf  ldloc.0
0x119c0  brfalse.s loc_119D0
0x119c2  ldloc.0
0x119c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.ActiveDirectoryUserInformation::get_ActiveDirectoryId()
0x119c8  stloc.2
0x119c9  ldloc.0
0x119ca  callvirt instance bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_IsValidated()
0x119cf  stloc.1
0x119d0  ldloc.2
0x119d1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x119d6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x119db  brfalse.s loc_119E3
0x119dd  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x119e2  stloc.2
0x119e3  ldarg.0
0x119e4  ldstr    aIsactivedirect// "isactivedirectoryuser"
0x119e9  ldloc.1
0x119ea  box      [mscorlib]System.Boolean
0x119ef  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x119f4  ldarg.0
0x119f5  ldstr    aActivedirector// "activedirectoryguid"
0x119fa  ldloc.2
0x119fb  box      [mscorlib]System.Guid
0x11a00  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x11a05  ldarg.3
0x11a06  brfalse  loc_11B02
0x11a0b  ldc.i4.2
0x11a0c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x11a11  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x11a16  bne.un   loc_11B02
0x11a1b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x11a20  ldarg.2
0x11a21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x11a26  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x11a2b  brfalse  loc_11B02
0x11a30  ldarg.0
0x11a31  ldstr    aApplicationid// "applicationid"
0x11a36  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x11a3b  brfalse  loc_11B02
0x11a40  ldarg.0
0x11a41  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x11a46  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x11a4b  brtrue.s loc_11A5F
0x11a4d  ldarg.0
0x11a4e  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x11a53  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x11a58  unbox.any [mscorlib]System.Boolean
0x11a5d  br.s     loc_11A60
0x11a5f  ldc.i4.0
0x11a60  stloc.3
0x11a61  ldarg.0
0x11a62  ldstr    aAccessmode// "accessmode"
0x11a67  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x11a6c  unbox.any [mscorlib]System.Int32
0x11a71  ldc.i4.4
0x11a72  bne.un.s loc_11A88
0x11a74  ldloc.3
0x11a75  brtrue.s loc_11A88
0x11a77  ldc.i4   0x80041D4B
0x11a7c  ldc.i4.0
0x11a7d  newarr   [mscorlib]System.Object
0x11a82  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x11a87  throw
0x11a88  ldloc.3
0x11a89  brfalse.s loc_11B02
0x11a8b  ldarg.0
0x11a8c  ldarg.2
0x11a8d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.UserManagementFactory::GetDirectoryObjectId(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity systemuser, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x11a92  stloc.s  4
0x11a94  ldloc.s  4
0x11a96  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x11a9b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11aa0  brfalse.s loc_11AB3
0x11aa2  ldc.i4   0x80041D4B
0x11aa7  ldc.i4.0
0x11aa8  newarr   [mscorlib]System.Object
0x11aad  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x11ab2  throw
0x11ab3  ldarg.0
0x11ab4  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x11ab9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x11abe  brtrue.s loc_11AD9
0x11ac0  ldarg.0
0x11ac1  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x11ac6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x11acb  unbox.any [mscorlib]System.Guid
0x11ad0  ldloc.s  4
0x11ad2  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11ad7  brfalse.s loc_11AEB
0x11ad9  ldarg.0
0x11ada  ldstr    aAzureactivedir// "azureactivedirectoryobjectid"
0x11adf  ldloc.s  4
0x11ae1  box      [mscorlib]System.Guid
0x11ae6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x11aeb  ldarg.1
0x11aec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation::get_Properties()
0x11af1  ldstr    aDirectoryobjec// "DirectoryObjectId"
0x11af6  ldloc.s  4
0x11af8  box      [mscorlib]System.Guid
0x11afd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x11b02  ret
```
