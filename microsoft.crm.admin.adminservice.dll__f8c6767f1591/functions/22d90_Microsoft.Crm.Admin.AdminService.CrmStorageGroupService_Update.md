# Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::Update

- ea: `0x22d90`
- end: `0x22e47`
- name: `Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::Update`
- size: `183`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x23080`
- `0x23100`
- `0x23130`

## callees

- `0x18790`
- `0x22d90`
- `0x23580`
- `0x24400`
- `0x24460`

## string_xrefs

- `0x22e2a`: `Update`
- `0x22e2f`: `D:\a\1\s\src\CrmLive\Admin\StorageGroup\CrmStorageGroupService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x22d90  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22d95  ldc.i4.s 9
0x22d97  ldstr    aUpdatingStorag// "Updating StorageGroup state, Id=({0}))"
0x22d9c  ldc.i4.1
0x22d9d  newarr   [mscorlib]System.Object
0x22da2  dup
0x22da3  ldc.i4.0
0x22da4  ldarg.1
0x22da5  box      [mscorlib]System.Guid
0x22daa  stelem.ref
0x22dab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22db0  ldarg.1
0x22db1  ldstr    aStoragegroupId// "StorageGroup identifier"
0x22db6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x22dbb  ldarg.2
0x22dbc  ldstr    aStoragegroupda// "storageGroupData"
0x22dc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x22dc6  ldarg.2
0x22dc7  callvirt instance string Microsoft.Crm.Admin.AdminService.StorageGroupData::get_StorageGroupCapacity()
0x22dcc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22dd1  brtrue.s loc_22DFB
0x22dd3  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::.ctor()
0x22dd8  ldarg.2
0x22dd9  callvirt instance string Microsoft.Crm.Admin.AdminService.StorageGroupData::get_StorageGroupCapacity()
0x22dde  call     instance bool Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::DoesCapacityExist(string storageGroupCapacityName)
0x22de3  brtrue.s loc_22DFB
0x22de5  ldstr    aUnableToFindCa// "Unable to find capacity: "
0x22dea  ldarg.2
0x22deb  callvirt instance string Microsoft.Crm.Admin.AdminService.StorageGroupData::get_StorageGroupCapacity()
0x22df0  call     string [mscorlib]System.String::Concat(string, string)
0x22df5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x22dfa  throw
0x22dfb  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x22e00  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x22e05  stloc.0
0x22e06  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x22e0b  stloc.1
0x22e0c  ldloc.1
0x22e0d  ldloc.0
0x22e0e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x22e13  ldloc.1
0x22e14  ldstr    aStoragegroup// "StorageGroup"
0x22e19  ldarg.1
0x22e1a  box      [mscorlib]System.Guid
0x22e1f  ldarg.2
0x22e20  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x22e25  ldc.i4   0xA4
0x22e2a  ldstr    aUpdate// "Update"
0x22e2f  ldstr    aDA1SSrcCrmlive_45// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Stora"...
0x22e34  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x22e39  pop
0x22e3a  leave.s  loc_22E46
0x22e3c  ldloc.1
0x22e3d  brfalse.s loc_22E45
0x22e3f  ldloc.1
0x22e40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22e45  endfinally
0x22e46  ret
```
