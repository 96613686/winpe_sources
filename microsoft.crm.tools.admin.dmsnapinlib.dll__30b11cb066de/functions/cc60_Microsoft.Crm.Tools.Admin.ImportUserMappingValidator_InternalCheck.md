# Microsoft.Crm.Tools.Admin.ImportUserMappingValidator::InternalCheck

- ea: `0xcc60`
- end: `0xccbe`
- name: `Microsoft.Crm.Tools.Admin.ImportUserMappingValidator::InternalCheck`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x22e0`
- `0x84f0`
- `0x89f0`
- `0xcc60`
- `0x143b0`

## string_xrefs

- `0xcc73`: `InstallInfo.CreateDatabase`
- `0xcc87`: `Cannot call this ImportUserMappingValidator if CreateDatabase property is set to true`

## pseudocode

```c

```

## disassembly

```asm
0xcc60  ldarg.1
0xcc61  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xcc66  stloc.0
0xcc67  ldloc.0
0xcc68  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> Microsoft.Crm.Tools.Admin.IImportOrganizationInfo::get_Users()
0xcc6d  ldloc.0
0xcc6e  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xcc73  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0xcc78  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xcc7d  brfalse.s loc_CC92
0xcc7f  ldloc.0
0xcc80  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase()
0xcc85  brfalse.s loc_CC92
0xcc87  ldstr    aCannotCallThis_2// "Cannot call this ImportUserMappingValid"...
0xcc8c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xcc91  throw
0xcc92  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User> [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.UserMappingValidation::AreUsersMappingValid(class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>)
0xcc97  stloc.1
0xcc98  ldloc.1
0xcc99  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.UserManagement.User>::get_Count()
0xcc9e  brfalse.s loc_CCB7
0xcca0  ldc.i4.2
0xcca1  ldstr    aImportusermapp// "ImportUserMappingValidator.MultiCrmUser"...
0xcca6  ldc.i4.0
0xcca7  newarr   [mscorlib]System.Object
0xccac  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xccb1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xccb6  ret
0xccb7  ldc.i4.0
0xccb8  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xccbd  ret
```
