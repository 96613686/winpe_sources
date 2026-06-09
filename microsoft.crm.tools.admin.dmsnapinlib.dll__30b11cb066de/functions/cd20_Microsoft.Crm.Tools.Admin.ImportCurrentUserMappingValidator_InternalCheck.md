# Microsoft.Crm.Tools.Admin.ImportCurrentUserMappingValidator::InternalCheck

- ea: `0xcd20`
- end: `0xcd7f`
- name: `Microsoft.Crm.Tools.Admin.ImportCurrentUserMappingValidator::InternalCheck`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x22e0`
- `0x84f0`
- `0x89f0`
- `0xcd00`
- `0xcd20`
- `0x143b0`
- `0x159a0`

## string_xrefs

- `0xcd34`: `InstallInfo.CreateDatabase`
- `0xcd48`: `Cannot call this ImportCurrentUserMapingValidator if CreateDatabase property is set to true`

## pseudocode

```c

```

## disassembly

```asm
0xcd20  ldarg.1
0xcd21  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xcd26  stloc.0
0xcd27  ldloc.0
0xcd28  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.IImportOrganizationInfo::get_Users()
0xcd2d  stloc.1
0xcd2e  ldloc.0
0xcd2f  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xcd34  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0xcd39  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xcd3e  brfalse.s loc_CD53
0xcd40  ldloc.0
0xcd41  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase()
0xcd46  brfalse.s loc_CD53
0xcd48  ldstr    aCannotCallThis_3// "Cannot call this ImportCurrentUserMapin"...
0xcd4d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xcd52  throw
0xcd53  ldarg.0
0xcd54  call     instance string Microsoft.Crm.Tools.Admin.ImportCurrentUserMappingValidator::get_AdminUserName()
0xcd59  ldloc.1
0xcd5a  call     bool Microsoft.Crm.Tools.Admin.ImportValidation::IsUserMappedToValidSystemAdminRole(string targetUserName, class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> users)
0xcd5f  brtrue.s loc_CD78
0xcd61  ldc.i4.2
0xcd62  ldstr    aImportcurrentu// "ImportCurrentUserMapingValidator.MapToV"...
0xcd67  ldc.i4.0
0xcd68  newarr   [mscorlib]System.Object
0xcd6d  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xcd72  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xcd77  ret
0xcd78  ldc.i4.0
0xcd79  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xcd7e  ret
```
