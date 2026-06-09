# Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Delete

- ea: `0x1ee60`
- end: `0x1efe8`
- name: `Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Delete`
- size: `392`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x17850`
- `0x17870`
- `0x1ee60`
- `0x1f280`
- `0x1f900`
- `0x20730`
- `0x21670`
- `0x22230`
- `0x22290`
- `0x22300`
- `0x25a40`
- `0x27750`
- `0x29880`
- `0x29920`
- `0x29950`

## string_xrefs

- `0x1ef7a`: `Delete`
- `0x1ef7f`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`
- `0x1ef90`: `Deleted ScaleGroup, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1ee60  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1ee65  ldc.i4.s 9
0x1ee67  ldstr    aDeletingScaleg// "Deleting ScaleGroup, Id=({0})"
0x1ee6c  ldc.i4.1
0x1ee6d  newarr   [mscorlib]System.Object
0x1ee72  dup
0x1ee73  ldc.i4.0
0x1ee74  ldarg.1
0x1ee75  box      [mscorlib]System.Guid
0x1ee7a  stelem.ref
0x1ee7b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ee80  ldarg.1
0x1ee81  ldstr    aScalegroupIden// "ScaleGroup identifier"
0x1ee86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1ee8b  ldarg.0
0x1ee8c  ldarg.1
0x1ee8d  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupState Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::GetState(valuetype [mscorlib]System.Guid scaleGroupId)
0x1ee92  stloc.0
0x1ee93  ldc.i4.1
0x1ee94  ldloc.0
0x1ee95  bne.un.s loc_1EEAE
0x1ee97  ldstr    aScalegroup// "ScaleGroup"
0x1ee9c  ldarg.1
0x1ee9d  box      [mscorlib]System.Guid
0x1eea2  ldloc.0
0x1eea3  box      [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupState
0x1eea8  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCannotDeleteObjectDueState(string objectType, object value, class [mscorlib]System.Enum state)
0x1eead  throw
0x1eeae  newobj   instance void Microsoft.Crm.Admin.AdminService.ServerFilter::.ctor()
0x1eeb3  stloc.1
0x1eeb4  ldloc.1
0x1eeb5  ldarg.1
0x1eeb6  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerFilter::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x1eebb  ldloc.1
0x1eebc  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x1eec1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x1eec6  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerFilter::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x1eecb  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmServerService::.ctor()
0x1eed0  ldloc.1
0x1eed1  callvirt instance class Microsoft.Crm.Admin.AdminService.ServerData[] Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveMultiple(class Microsoft.Crm.Admin.AdminService.ServerFilter filter)
0x1eed6  stloc.2
0x1eed7  ldloc.2
0x1eed8  ldstr    aArrserverdata// "arrServerData"
0x1eedd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1eee2  ldloc.2
0x1eee3  ldlen
0x1eee4  brfalse.s loc_1EEFC
0x1eee6  ldstr    aScalegroup// "ScaleGroup"
0x1eeeb  ldarg.1
0x1eeec  box      [mscorlib]System.Guid
0x1eef1  ldstr    aServer_1// "Server"
0x1eef6  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCascadeDeleteNotAllowDelete(string objectType, object value, string objectTypeChild)
0x1eefb  throw
0x1eefc  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationFilter::.ctor()
0x1ef01  stloc.3
0x1ef02  ldloc.3
0x1ef03  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x1ef08  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x1ef0d  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationFilter::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x1ef12  ldloc.3
0x1ef13  ldarg.1
0x1ef14  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationFilter::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x1ef19  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x1ef1e  ldc.i4.1
0x1ef1f  newarr   [mscorlib]System.String
0x1ef24  dup
0x1ef25  ldc.i4.0
0x1ef26  ldstr    aId// "Id"
0x1ef2b  stelem.ref
0x1ef2c  ldloc.3
0x1ef2d  callvirt instance class Microsoft.Crm.Admin.AdminService.OrganizationData[] Microsoft.Crm.Admin.AdminService.CrmOrganizationService::RetrieveMultiple(string[] columns, class Microsoft.Crm.Admin.AdminService.OrganizationFilter filter)
0x1ef32  stloc.s  4
0x1ef34  ldloc.s  4
0x1ef36  ldstr    aArrorgdata// "arrOrgData"
0x1ef3b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ef40  ldloc.s  4
0x1ef42  ldlen
0x1ef43  brfalse.s loc_1EF5B
0x1ef45  ldstr    aScalegroup// "ScaleGroup"
0x1ef4a  ldarg.1
0x1ef4b  box      [mscorlib]System.Guid
0x1ef50  ldstr    aOrganization// "Organization"
0x1ef55  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCascadeDeleteNotAllowDelete(string objectType, object value, string objectTypeChild)
0x1ef5a  throw
0x1ef5b  ldarg.1
0x1ef5c  call     void Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RemoveDeployment(valuetype [mscorlib]System.Guid scaleGroupId)
0x1ef61  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1ef66  stloc.s  5
0x1ef68  ldloc.s  5
0x1ef6a  ldstr    aScalegroup// "ScaleGroup"
0x1ef6f  ldarg.1
0x1ef70  box      [mscorlib]System.Guid
0x1ef75  ldc.i4   0x146
0x1ef7a  ldstr    aDelete// "Delete"
0x1ef7f  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1ef84  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1ef89  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1ef8e  ldc.i4.s 9
0x1ef90  ldstr    aDeletedScalegr// "Deleted ScaleGroup, Id=({0})"
0x1ef95  ldc.i4.1
0x1ef96  newarr   [mscorlib]System.Object
0x1ef9b  dup
0x1ef9c  ldc.i4.0
0x1ef9d  ldarg.1
0x1ef9e  box      [mscorlib]System.Guid
0x1efa3  stelem.ref
0x1efa4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1efa9  leave.s  loc_1EFB7
0x1efab  ldloc.s  5
0x1efad  brfalse.s loc_1EFB6
0x1efaf  ldloc.s  5
0x1efb1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1efb6  endfinally
0x1efb7  leave.s  loc_1EFE7
0x1efb9  stloc.s  6
0x1efbb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1efc0  ldc.i4.s 9
0x1efc2  ldstr    aExceptionDelet_2// "Exception deleting ScaleGroup, Id=({0} "...
0x1efc7  ldc.i4.2
0x1efc8  newarr   [mscorlib]System.Object
0x1efcd  dup
0x1efce  ldc.i4.0
0x1efcf  ldarg.1
0x1efd0  box      [mscorlib]System.Guid
0x1efd5  stelem.ref
0x1efd6  dup
0x1efd7  ldc.i4.1
0x1efd8  ldloc.s  6
0x1efda  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1efdf  stelem.ref
0x1efe0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1efe5  rethrow
0x1efe7  ret
```
