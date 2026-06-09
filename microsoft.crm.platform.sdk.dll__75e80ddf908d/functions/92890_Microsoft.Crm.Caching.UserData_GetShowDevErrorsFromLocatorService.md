# Microsoft.Crm.Caching.UserData::GetShowDevErrorsFromLocatorService

- ea: `0x92890`
- end: `0x92997`
- name: `Microsoft.Crm.Caching.UserData::GetShowDevErrorsFromLocatorService`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x92580`

## callees

- `0x91980`
- `0x91a20`
- `0x92890`

## string_xrefs

- `0x92897`: `IsInSyncServiceContext`
- `0x92908`: `GetShowDevErrorsFromLocatorService`
- `0x92961`: `GetShowDevErrorsFromLocatorService`
- `0x9290d`: `D:\a\1\s\src\ManagedPlatform\SDK\Caching\CacheData\User.cs`
- `0x92966`: `D:\a\1\s\src\ManagedPlatform\SDK\Caching\CacheData\User.cs`

## pseudocode

```c

```

## disassembly

```asm
0x92890  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInServerContext()
0x92895  brfalse.s loc_928B1
0x92897  ldstr    aIsinsyncservic// "IsInSyncServiceContext"
0x9289c  ldc.i4.0
0x9289d  box      [mscorlib]System.Boolean
0x928a2  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x928a7  unbox.any [mscorlib]System.Boolean
0x928ac  ldc.i4.0
0x928ad  ceq
0x928af  br.s     loc_928B2
0x928b1  ldc.i4.0
0x928b2  brtrue.s loc_928B6
0x928b4  ldc.i4.0
0x928b5  ret
0x928b6  ldc.i4.0
0x928b7  stloc.0
0x928b8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x928bd  stloc.1
0x928be  ldloc.1
0x928bf  ldstr    aCrmuserid// "CrmUserId"
0x928c4  ldarg.0
0x928c5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.UserData::get_SystemUserId()
0x928ca  box      [mscorlib]System.Guid
0x928cf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x928d4  ldloc.1
0x928d5  ldstr    aOrganizationid_2// "OrganizationId"
0x928da  ldarg.0
0x928db  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Caching.UserData::get_OrganizationId()
0x928e0  box      [mscorlib]System.Guid
0x928e5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x928ea  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x928ef  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x928f4  ldc.i4.1
0x928f5  newarr   [mscorlib]System.String
0x928fa  dup
0x928fb  ldc.i4.0
0x928fc  ldstr    aUserid// "UserId"
0x92901  stelem.ref
0x92902  ldloc.1
0x92903  ldc.i4   0x559
0x92908  ldstr    aGetshowdeverro// "GetShowDevErrorsFromLocatorService"
0x9290d  ldstr    aDA1SSrcManaged_12// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x92912  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x92917  stloc.2
0x92918  ldloc.2
0x92919  brfalse.s loc_92995
0x9291b  ldloc.2
0x9291c  ldstr    aUserid// "UserId"
0x92921  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x92926  unbox.any [mscorlib]System.Guid
0x9292b  stloc.3
0x9292c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x92931  stloc.1
0x92932  ldloc.1
0x92933  ldstr    aId_0// "Id"
0x92938  ldloc.3
0x92939  box      [mscorlib]System.Guid
0x9293e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x92943  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x92948  ldstr    aSystemuser_0// "SystemUser"
0x9294d  ldc.i4.1
0x9294e  newarr   [mscorlib]System.String
0x92953  dup
0x92954  ldc.i4.0
0x92955  ldstr    aShowdeverrors// "ShowDevErrors"
0x9295a  stelem.ref
0x9295b  ldloc.1
0x9295c  ldc.i4   0x563
0x92961  ldstr    aGetshowdeverro// "GetShowDevErrorsFromLocatorService"
0x92966  ldstr    aDA1SSrcManaged_12// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x9296b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x92970  stloc.2
0x92971  ldloc.2
0x92972  brfalse.s loc_92995
0x92974  ldloc.2
0x92975  ldstr    aShowdeverrors// "ShowDevErrors"
0x9297a  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x9297f  brfalse.s loc_92995
0x92981  ldloc.2
0x92982  ldstr    aShowdeverrors// "ShowDevErrors"
0x92987  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x9298c  unbox.any [mscorlib]System.Boolean
0x92991  brfalse.s loc_92995
0x92993  ldc.i4.1
0x92994  stloc.0
0x92995  ldloc.0
0x92996  ret
```
