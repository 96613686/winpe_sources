# Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::TryDeleteTemplate

- ea: `0x1fa70`
- end: `0x1fbfd`
- name: `Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::TryDeleteTemplate`
- size: `397`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1fa70`
- `0x1fc20`

## string_xrefs

- `0x1fae0`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`
- `0x1fb35`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`
- `0x1fa84`: `Start delete provisioning template for scalegroup {0}, language {1}`
- `0x1fadb`: `TryDeleteTemplate`
- `0x1fb30`: `TryDeleteTemplate`
- `0x1fb65`: `organizationtemplate`
- `0x1fb96`: `Deleted provisioning template for scalegroup {0}, language {1} from path {2}`
- `0x1fbca`: `Exception deleting org template for scalegroup {0}, language {1}, {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1fa70  ldarg.1
0x1fa71  ldstr    aScalegroupid// "scaleGroupId"
0x1fa76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1fa7b  ldc.i4.0
0x1fa7c  stloc.0
0x1fa7d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1fa82  ldc.i4.s 0x14
0x1fa84  ldstr    aStartDeletePro// "Start delete provisioning template for "...
0x1fa89  ldc.i4.2
0x1fa8a  newarr   [mscorlib]System.Object
0x1fa8f  dup
0x1fa90  ldc.i4.0
0x1fa91  ldarg.1
0x1fa92  box      [mscorlib]System.Guid
0x1fa97  stelem.ref
0x1fa98  dup
0x1fa99  ldc.i4.1
0x1fa9a  ldarg.2
0x1fa9b  box      [mscorlib]System.Int32
0x1faa0  stelem.ref
0x1faa1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1faa6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1faab  stloc.1
0x1faac  ldloc.1
0x1faad  ldstr    aScalegroupid_0// "ScaleGroupId"
0x1fab2  ldarg.1
0x1fab3  box      [mscorlib]System.Guid
0x1fab8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1fabd  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x1fac2  ldstr    aScalegroupdepl// "ScaleGroupDeployment"
0x1fac7  ldc.i4.1
0x1fac8  newarr   [mscorlib]System.String
0x1facd  dup
0x1face  ldc.i4.0
0x1facf  ldstr    aDeploymentid// "DeploymentId"
0x1fad4  stelem.ref
0x1fad5  ldloc.1
0x1fad6  ldc.i4   0x31F
0x1fadb  ldstr    aTrydeletetempl// "TryDeleteTemplate"
0x1fae0  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1fae5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1faea  stloc.2
0x1faeb  ldloc.2
0x1faec  brtrue.s loc_1FAF6
0x1faee  ldc.i4.0
0x1faef  stloc.s  6
0x1faf1  leave    loc_1FBFA
0x1faf6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1fafb  stloc.3
0x1fafc  ldloc.3
0x1fafd  ldstr    aId// "Id"
0x1fb02  ldloc.2
0x1fb03  ldstr    aDeploymentid// "DeploymentId"
0x1fb08  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1fb0d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1fb12  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x1fb17  ldstr    aDeployment// "Deployment"
0x1fb1c  ldc.i4.1
0x1fb1d  newarr   [mscorlib]System.String
0x1fb22  dup
0x1fb23  ldc.i4.0
0x1fb24  ldstr    aDatabasebackup// "DatabaseBackupShareLocation"
0x1fb29  stelem.ref
0x1fb2a  ldloc.3
0x1fb2b  ldc.i4   0x32B
0x1fb30  ldstr    aTrydeletetempl// "TryDeleteTemplate"
0x1fb35  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1fb3a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1fb3f  stloc.s  4
0x1fb41  ldloc.s  4
0x1fb43  brtrue.s loc_1FB4D
0x1fb45  ldc.i4.0
0x1fb46  stloc.s  6
0x1fb48  leave    loc_1FBFA
0x1fb4d  ldarg.0
0x1fb4e  ldarg.1
0x1fb4f  ldloc.s  4
0x1fb51  ldstr    aDatabasebackup// "DatabaseBackupShareLocation"
0x1fb56  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1fb5b  isinst   [mscorlib]System.String
0x1fb60  call     instance string Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::GetTemplatePath(valuetype [mscorlib]System.Guid scaleGroupId, string path)
0x1fb65  ldstr    aOrganizationte// "organizationtemplate"
0x1fb6a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1fb6f  stloc.s  5
0x1fb71  ldloc.s  5
0x1fb73  ldarga.s 2
0x1fb75  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1fb7a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1fb7f  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1fb84  stloc.s  5
0x1fb86  ldloc.s  5
0x1fb88  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.SqlBackupRestoreUtility::DeleteTemplateFiles(string)
0x1fb8d  ldc.i4.1
0x1fb8e  stloc.0
0x1fb8f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1fb94  ldc.i4.s 0x14
0x1fb96  ldstr    aDeletedProvisi// "Deleted provisioning template for scale"...
0x1fb9b  ldc.i4.3
0x1fb9c  newarr   [mscorlib]System.Object
0x1fba1  dup
0x1fba2  ldc.i4.0
0x1fba3  ldarg.1
0x1fba4  box      [mscorlib]System.Guid
0x1fba9  stelem.ref
0x1fbaa  dup
0x1fbab  ldc.i4.1
0x1fbac  ldarg.2
0x1fbad  box      [mscorlib]System.Int32
0x1fbb2  stelem.ref
0x1fbb3  dup
0x1fbb4  ldc.i4.2
0x1fbb5  ldloc.s  5
0x1fbb7  stelem.ref
0x1fbb8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fbbd  leave.s  loc_1FBF8
0x1fbbf  stloc.s  7
0x1fbc1  ldloc.s  7
0x1fbc3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1fbc8  ldc.i4.s 0x14
0x1fbca  ldstr    aExceptionDelet_3// "Exception deleting org template for sca"...
0x1fbcf  ldc.i4.3
0x1fbd0  newarr   [mscorlib]System.Object
0x1fbd5  dup
0x1fbd6  ldc.i4.0
0x1fbd7  ldarg.1
0x1fbd8  box      [mscorlib]System.Guid
0x1fbdd  stelem.ref
0x1fbde  dup
0x1fbdf  ldc.i4.1
0x1fbe0  ldarg.2
0x1fbe1  box      [mscorlib]System.Int32
0x1fbe6  stelem.ref
0x1fbe7  dup
0x1fbe8  ldc.i4.2
0x1fbe9  ldloc.s  7
0x1fbeb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1fbf0  stelem.ref
0x1fbf1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fbf6  leave.s  loc_1FBF8
0x1fbf8  ldloc.0
0x1fbf9  ret
0x1fbfa  ldloc.s  6
0x1fbfc  ret
```
