# Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::Create

- ea: `0x240e0`
- end: `0x2418c`
- name: `Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::Create`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x240e0`
- `0x24400`

## string_xrefs

- `0x24169`: `Create`
- `0x24103`: `StorageGroup capacity already exists.`
- `0x2416e`: `D:\a\1\s\src\CrmLive\Admin\StorageGroupCapacity\CrmStorageGroupCapacityService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x240e0  ldarg.1
0x240e1  ldstr    aName_0// "name"
0x240e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x240eb  ldarg.2
0x240ec  ldc.i4.0
0x240ed  bgt.s    loc_240FA
0x240ef  ldstr    aNumberOfOrgsMu// "Number of orgs must be positive."
0x240f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x240f9  throw
0x240fa  ldarg.0
0x240fb  ldarg.1
0x240fc  call     instance bool Microsoft.Crm.Admin.AdminService.CrmStorageGroupCapacityService::DoesCapacityExist(string storageGroupCapacityName)
0x24101  brfalse.s loc_2410E
0x24103  ldstr    aStoragegroupCa// "StorageGroup capacity already exists."
0x24108  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2410d  throw
0x2410e  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24113  stloc.0
0x24114  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x24119  stloc.1
0x2411a  ldloc.1
0x2411b  ldstr    aId// "Id"
0x24120  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x24125  box      [mscorlib]System.Guid
0x2412a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2412f  ldloc.1
0x24130  ldstr    aName// "Name"
0x24135  ldarg.1
0x24136  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2413b  ldloc.1
0x2413c  ldstr    aNumberoforgs// "NumberOfOrgs"
0x24141  ldarg.2
0x24142  box      [mscorlib]System.Int32
0x24147  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2414c  ldarg.3
0x2414d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x24152  brtrue.s loc_24160
0x24154  ldloc.1
0x24155  ldstr    aDescription// "Description"
0x2415a  ldarg.3
0x2415b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x24160  ldloc.0
0x24161  ldstr    aStoragegroupca// "StorageGroupCapacity"
0x24166  ldloc.1
0x24167  ldc.i4.s 0x3D
0x24169  ldstr    aCreate// "Create"
0x2416e  ldstr    aDA1SSrcCrmlive_46// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Stora"...
0x24173  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x24178  unbox.any [mscorlib]System.Guid
0x2417d  stloc.2
0x2417e  leave.s  loc_2418A
0x24180  ldloc.0
0x24181  brfalse.s loc_24189
0x24183  ldloc.0
0x24184  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24189  endfinally
0x2418a  ldloc.2
0x2418b  ret
```
