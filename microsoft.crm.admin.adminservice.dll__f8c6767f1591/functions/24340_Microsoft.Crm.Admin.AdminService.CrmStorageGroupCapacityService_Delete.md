# Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::Delete

- ea: `0x24340`
- end: `0x243cf`
- name: `Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::Delete`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x24340`
- `0x243d0`

## string_xrefs

- `0x243a5`: `Delete`
- `0x243aa`: `D:\a\1\s\src\CrmLive\Admin\StorageGroupCapacity\CrmStorageGroupCapacityService.cs`
- `0x24359`: `Cannot delete the default StorageGroupCapacity.`
- `0x2436d`: `Cannot delete the StorageGroupCapacity because there are storage groups configured to use this.`
- `0x243b7`: `The StorageGroupCapacity does not exist or delete failed`

## pseudocode

```c

```

## disassembly

```asm
0x24340  ldarg.1
0x24341  ldstr    aName_0// "name"
0x24346  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2434b  ldarg.1
0x2434c  ldstr    aDefault// "Default"
0x24351  ldc.i4.5
0x24352  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x24357  brfalse.s loc_24364
0x24359  ldstr    aCannotDeleteTh// "Cannot delete the default StorageGroupC"...
0x2435e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x24363  throw
0x24364  ldarg.0
0x24365  ldarg.1
0x24366  call     instance bool Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::IsCapacityInUse(string storageGroupCapacityName)
0x2436b  brfalse.s loc_24378
0x2436d  ldstr    aCannotDeleteTh_0// "Cannot delete the StorageGroupCapacity "...
0x24372  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x24377  throw
0x24378  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2437d  stloc.0
0x2437e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x24383  stloc.1
0x24384  ldloc.1
0x24385  ldstr    aName// "Name"
0x2438a  ldarg.1
0x2438b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x24390  ldloc.0
0x24391  ldstr    aStoragegroupca// "StorageGroupCapacity"
0x24396  ldc.i4.1
0x24397  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x2439c  dup
0x2439d  ldc.i4.0
0x2439e  ldloc.1
0x2439f  stelem.ref
0x243a0  ldc.i4   0xA9
0x243a5  ldstr    aDelete// "Delete"
0x243aa  ldstr    aDA1SSrcCrmlive_46// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Stora"...
0x243af  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x243b4  ldc.i4.0
0x243b5  bgt.s    loc_243C2
0x243b7  ldstr    aTheStoragegrou// "The StorageGroupCapacity does not exist"...
0x243bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x243c1  throw
0x243c2  leave.s  loc_243CE
0x243c4  ldloc.0
0x243c5  brfalse.s loc_243CD
0x243c7  ldloc.0
0x243c8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x243cd  endfinally
0x243ce  ret
```
