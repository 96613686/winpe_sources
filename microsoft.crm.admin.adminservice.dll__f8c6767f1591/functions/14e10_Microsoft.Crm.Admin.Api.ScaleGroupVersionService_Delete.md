# Microsoft.Crm.Admin.Api.ScaleGroupVersionService::Delete

- ea: `0x14e10`
- end: `0x14ec2`
- name: `Microsoft.Crm.Admin.Api.ScaleGroupVersionService::Delete`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x14e10`
- `0x1e9b0`
- `0x1f430`
- `0x205b0`

## string_xrefs

- `0x14e98`: `Delete`
- `0x14e9d`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroupVersion\ScaleGroupVersionService.cs`
- `0x14e29`: `Can not delete the default scale group version.`
- `0x14e56`: `Can not delete the scale group version because there are scale groups associated.`
- `0x14eaa`: `The scale group version does not exist or delete failed`

## pseudocode

```c

```

## disassembly

```asm
0x14e10  ldarg.1
0x14e11  ldstr    aName_0// "name"
0x14e16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x14e1b  ldarg.1
0x14e1c  ldstr    aDefault// "Default"
0x14e21  ldc.i4.5
0x14e22  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x14e27  brfalse.s loc_14E34
0x14e29  ldstr    aCanNotDeleteTh// "Can not delete the default scale group "...
0x14e2e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x14e33  throw
0x14e34  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::.ctor()
0x14e39  callvirt instance class Microsoft.Crm.Admin.AdminService.ScaleGroupData[] Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RetrieveMultiple()
0x14e3e  stloc.0
0x14e3f  ldc.i4.0
0x14e40  stloc.1
0x14e41  br.s     loc_14E65
0x14e43  ldloc.0
0x14e44  ldloc.1
0x14e45  ldelem.ref
0x14e46  stloc.2
0x14e47  ldarg.1
0x14e48  ldloc.2
0x14e49  callvirt instance string Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ScaleGroupVersion()
0x14e4e  ldc.i4.5
0x14e4f  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x14e54  brfalse.s loc_14E61
0x14e56  ldstr    aCanNotDeleteTh_0// "Can not delete the scale group version "...
0x14e5b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x14e60  throw
0x14e61  ldloc.1
0x14e62  ldc.i4.1
0x14e63  add
0x14e64  stloc.1
0x14e65  ldloc.1
0x14e66  ldloc.0
0x14e67  ldlen
0x14e68  conv.i4
0x14e69  blt.s    loc_14E43
0x14e6b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x14e70  stloc.3
0x14e71  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x14e76  stloc.s  4
0x14e78  ldloc.s  4
0x14e7a  ldstr    aName// "Name"
0x14e7f  ldarg.1
0x14e80  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x14e85  ldloc.3
0x14e86  ldstr    aScalegroupvers// "ScaleGroupVersion"
0x14e8b  ldc.i4.1
0x14e8c  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x14e91  dup
0x14e92  ldc.i4.0
0x14e93  ldloc.s  4
0x14e95  stelem.ref
0x14e96  ldc.i4.s 0x5B
0x14e98  ldstr    aDelete// "Delete"
0x14e9d  ldstr    aDA1SSrcCrmlive_29// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x14ea2  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x14ea7  ldc.i4.0
0x14ea8  bgt.s    loc_14EB5
0x14eaa  ldstr    aTheScaleGroupV// "The scale group version does not exist "...
0x14eaf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x14eb4  throw
0x14eb5  leave.s  loc_14EC1
0x14eb7  ldloc.3
0x14eb8  brfalse.s loc_14EC0
0x14eba  ldloc.3
0x14ebb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ec0  endfinally
0x14ec1  ret
```
