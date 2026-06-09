# Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::Update

- ea: `0x24290`
- end: `0x24336`
- name: `Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::Update`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x150d0`
- `0x15150`
- `0x15190`
- `0x24190`
- `0x24290`

## string_xrefs

- `0x24319`: `Update`
- `0x2431e`: `D:\a\1\s\src\CrmLive\Admin\StorageGroupCapacity\CrmStorageGroupCapacityService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x24290  ldarg.1
0x24291  ldstr    aName_0// "name"
0x24296  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2429b  ldarg.2
0x2429c  ldstr    aStoragegroupca_1// "storageGroupCapacity"
0x242a1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x242a6  ldarg.2
0x242a7  callvirt instance int32 Microsoft.Crm.Admin.Api.StorageGroupCapacityData::get_NumberOfOrgs()
0x242ac  ldc.i4.0
0x242ad  bgt.s    loc_242BA
0x242af  ldstr    aNumberOfOrgsMu// "Number of orgs must be positive."
0x242b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x242b9  throw
0x242ba  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x242bf  stloc.0
0x242c0  ldloc.0
0x242c1  ldstr    aNumberoforgs// "NumberOfOrgs"
0x242c6  ldarg.2
0x242c7  callvirt instance int32 Microsoft.Crm.Admin.Api.StorageGroupCapacityData::get_NumberOfOrgs()
0x242cc  box      [mscorlib]System.Int32
0x242d1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x242d6  ldarg.2
0x242d7  callvirt instance string Microsoft.Crm.Admin.Api.StorageGroupCapacityData::get_Description()
0x242dc  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x242e1  brtrue.s loc_242F4
0x242e3  ldloc.0
0x242e4  ldstr    aDescription// "Description"
0x242e9  ldarg.2
0x242ea  callvirt instance string Microsoft.Crm.Admin.Api.StorageGroupCapacityData::get_Description()
0x242ef  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x242f4  ldarg.0
0x242f5  ldarg.1
0x242f6  call     instance class Microsoft.Crm.Admin.Api.StorageGroupCapacityData Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::Retrieve(string storageGroupCapacityName)
0x242fb  stloc.1
0x242fc  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24301  stloc.2
0x24302  ldloc.2
0x24303  ldstr    aStoragegroupca// "StorageGroupCapacity"
0x24308  ldloc.1
0x24309  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.Api.StorageGroupCapacityData::get_Id()
0x2430e  box      [mscorlib]System.Guid
0x24313  ldloc.0
0x24314  ldc.i4   0x8D
0x24319  ldstr    aUpdate// "Update"
0x2431e  ldstr    aDA1SSrcCrmlive_46// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Stora"...
0x24323  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x24328  pop
0x24329  leave.s  loc_24335
0x2432b  ldloc.2
0x2432c  brfalse.s loc_24334
0x2432e  ldloc.2
0x2432f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24334  endfinally
0x24335  ret
```
