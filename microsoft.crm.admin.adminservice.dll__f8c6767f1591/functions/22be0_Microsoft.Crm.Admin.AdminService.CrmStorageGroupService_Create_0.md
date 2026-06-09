# Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::Create_0

- ea: `0x22be0`
- end: `0x22cda`
- name: `Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::Create_0`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x22bd0`

## callees

- `0x18790`
- `0x22be0`
- `0x23480`
- `0x234a0`
- `0x234c0`
- `0x23500`
- `0x235a0`
- `0x235e0`

## string_xrefs

- `0x22c45`: `Create`
- `0x22c4a`: `D:\a\1\s\src\CrmLive\Admin\StorageGroup\CrmStorageGroupService.cs`
- `0x22c7a`: `Created StorageGroup, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x22be0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22be5  ldc.i4.s 9
0x22be7  ldstr    aCreatingStorag// "Creating StorageGroup, Name=({0})"
0x22bec  ldc.i4.1
0x22bed  newarr   [mscorlib]System.Object
0x22bf2  dup
0x22bf3  ldc.i4.0
0x22bf4  ldarg.1
0x22bf5  stelem.ref
0x22bf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22bfb  ldarg.1
0x22bfc  ldstr    aStoragegroupNa// "StorageGroup name"
0x22c01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x22c06  newobj   instance void Microsoft.Crm.Admin.AdminService.StorageGroupData::.ctor()
0x22c0b  stloc.0
0x22c0c  ldloc.0
0x22c0d  ldarg.1
0x22c0e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::MakeGuidFromName(string)
0x22c13  callvirt instance void Microsoft.Crm.Admin.AdminService.StorageGroupData::set_Id(valuetype [mscorlib]System.Guid value)
0x22c18  ldloc.0
0x22c19  ldarg.1
0x22c1a  callvirt instance void Microsoft.Crm.Admin.AdminService.StorageGroupData::set_Name(string value)
0x22c1f  ldloc.0
0x22c20  ldarg.2
0x22c21  callvirt instance void Microsoft.Crm.Admin.AdminService.StorageGroupData::set_MaintenanceScaleGroupId(valuetype [mscorlib]System.Guid value)
0x22c26  ldloc.0
0x22c27  ldstr    aDefault// "Default"
0x22c2c  callvirt instance void Microsoft.Crm.Admin.AdminService.StorageGroupData::set_StorageGroupCapacity(string value)
0x22c31  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x22c36  stloc.1
0x22c37  ldloc.1
0x22c38  ldstr    aStoragegroup// "StorageGroup"
0x22c3d  ldloc.0
0x22c3e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x22c43  ldc.i4.s 0x5F
0x22c45  ldstr    aCreate// "Create"
0x22c4a  ldstr    aDA1SSrcCrmlive_45// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Stora"...
0x22c4f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x22c54  unbox.any [mscorlib]System.Guid
0x22c59  stloc.2
0x22c5a  ldloc.0
0x22c5b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.StorageGroupData::get_Id()
0x22c60  ldloc.2
0x22c61  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x22c66  brfalse.s loc_22C73
0x22c68  ldstr    aStoragegroupId_0// "StorageGroup Ids must be equal"
0x22c6d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x22c72  throw
0x22c73  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22c78  ldc.i4.s 9
0x22c7a  ldstr    aCreatedStorage// "Created StorageGroup, Id=({0})"
0x22c7f  ldc.i4.1
0x22c80  newarr   [mscorlib]System.Object
0x22c85  dup
0x22c86  ldc.i4.0
0x22c87  ldloc.0
0x22c88  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.StorageGroupData::get_Id()
0x22c8d  box      [mscorlib]System.Guid
0x22c92  stelem.ref
0x22c93  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22c98  ldloc.0
0x22c99  stloc.3
0x22c9a  leave.s  loc_22CD8
0x22c9c  ldloc.1
0x22c9d  brfalse.s loc_22CA5
0x22c9f  ldloc.1
0x22ca0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22ca5  endfinally
0x22ca6  stloc.s  4
0x22ca8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22cad  ldc.i4.s 9
0x22caf  ldstr    aExceptionCreat_5// "Exception creating StorageGroup, Name=("...
0x22cb4  ldc.i4.3
0x22cb5  newarr   [mscorlib]System.Object
0x22cba  dup
0x22cbb  ldc.i4.0
0x22cbc  ldarg.1
0x22cbd  stelem.ref
0x22cbe  dup
0x22cbf  ldc.i4.1
0x22cc0  ldloc.s  4
0x22cc2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x22cc7  stelem.ref
0x22cc8  dup
0x22cc9  ldc.i4.2
0x22cca  ldarg.2
0x22ccb  box      [mscorlib]System.Guid
0x22cd0  stelem.ref
0x22cd1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22cd6  rethrow
0x22cd8  ldloc.3
0x22cd9  ret
```
