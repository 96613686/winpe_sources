# Microsoft.Crm.StorageNotificationUtility::SetOrganizationCurrentStorageSize

- ea: `0x252e0`
- end: `0x254a3`
- name: `Microsoft.Crm.StorageNotificationUtility::SetOrganizationCurrentStorageSize`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x24fb0`
- `0x252e0`
- `0x254b0`

## string_xrefs

- `0x253f9`: `Update storage objects (object, value): ({0}, {1}) ({2}, {3}) ({4}, {5}) ({6}, {7}).`
- `0x25472`: `UpdateStorageObject`

## pseudocode

```c

```

## disassembly

```asm
0x252e0  ldarg.0
0x252e1  ldstr    aOrganizationst// "OrganizationStorageData"
0x252e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x252eb  ldarg.0
0x252ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_OrganizationId()
0x252f1  ldstr    aOrganizationid_0// "organizationId"
0x252f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x252fb  ldarg.0
0x252fc  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_DataSizeMB()
0x25301  ldstr    aDatasizemb// "DataSizeMB"
0x25306  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x2530b  ldarg.0
0x2530c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_IndexSizeMB()
0x25311  ldstr    aIndexsizemb// "IndexSizeMB"
0x25316  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x2531b  ldarg.0
0x2531c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_UnusedSpaceSizeMB()
0x25321  ldstr    aUnusedspacesiz// "UnusedSpaceSizeMB"
0x25326  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x2532b  ldarg.0
0x2532c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_CurrentStorageSizeMB()
0x25331  ldstr    aCurrentstorage// "CurrentStorageSizeMB"
0x25336  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x2533b  ldc.i4.2
0x2533c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x25341  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x25346  beq.s    loc_2534A
0x25348  ldc.i4.0
0x25349  ret
0x2534a  ldarg.0
0x2534b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_OrganizationId()
0x25350  ldarg.0
0x25351  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_DataSizeMB()
0x25356  ldarg.0
0x25357  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_IndexSizeMB()
0x2535c  call     bool Microsoft.Crm.StorageNotificationUtility::HasStorageChanged(valuetype [mscorlib]System.Guid organizationId, int32 newDataSizeMB, int32 newIndexSizeMB)
0x25361  brfalse  loc_2549E
0x25366  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2536b  stloc.0
0x2536c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x25371  stloc.1
0x25372  ldloc.1
0x25373  ldstr    aDatasizemb// "DataSizeMB"
0x25378  ldarg.0
0x25379  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_DataSizeMB()
0x2537e  box      [mscorlib]System.Int32
0x25383  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x25388  ldloc.1
0x25389  ldstr    aIndexsizemb// "IndexSizeMB"
0x2538e  ldarg.0
0x2538f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_IndexSizeMB()
0x25394  box      [mscorlib]System.Int32
0x25399  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2539e  ldloc.1
0x2539f  ldstr    aUnusedspacesiz// "UnusedSpaceSizeMB"
0x253a4  ldarg.0
0x253a5  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_UnusedSpaceSizeMB()
0x253aa  box      [mscorlib]System.Int32
0x253af  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x253b4  ldloc.1
0x253b5  ldstr    aCurrentstorage_0// "CurrentStorageSizeMb"
0x253ba  ldarg.0
0x253bb  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_CurrentStorageSizeMB()
0x253c0  box      [mscorlib]System.Int32
0x253c5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x253ca  ldloc.0
0x253cb  ldstr    aOrganization// "Organization"
0x253d0  ldarg.0
0x253d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_OrganizationId()
0x253d6  box      [mscorlib]System.Guid
0x253db  ldloc.1
0x253dc  ldc.i4   0x2FE
0x253e1  ldstr    aSetorganizatio// "SetOrganizationCurrentStorageSize"
0x253e6  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x253eb  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x253f0  ldc.i4.0
0x253f1  cgt
0x253f3  stloc.2
0x253f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x253f9  ldstr    aUpdateStorageO// "Update storage objects (object, value):"...
0x253fe  ldc.i4.8
0x253ff  newarr   [mscorlib]System.Object
0x25404  dup
0x25405  ldc.i4.0
0x25406  ldstr    aDatasizemb// "DataSizeMB"
0x2540b  stelem.ref
0x2540c  dup
0x2540d  ldc.i4.1
0x2540e  ldarg.0
0x2540f  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_DataSizeMB()
0x25414  box      [mscorlib]System.Int32
0x25419  stelem.ref
0x2541a  dup
0x2541b  ldc.i4.2
0x2541c  ldstr    aIndexsizemb// "IndexSizeMB"
0x25421  stelem.ref
0x25422  dup
0x25423  ldc.i4.3
0x25424  ldarg.0
0x25425  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_IndexSizeMB()
0x2542a  box      [mscorlib]System.Int32
0x2542f  stelem.ref
0x25430  dup
0x25431  ldc.i4.4
0x25432  ldstr    aUnusedspacesiz// "UnusedSpaceSizeMB"
0x25437  stelem.ref
0x25438  dup
0x25439  ldc.i4.5
0x2543a  ldarg.0
0x2543b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_UnusedSpaceSizeMB()
0x25440  box      [mscorlib]System.Int32
0x25445  stelem.ref
0x25446  dup
0x25447  ldc.i4.6
0x25448  ldstr    aCurrentstorage_0// "CurrentStorageSizeMb"
0x2544d  stelem.ref
0x2544e  dup
0x2544f  ldc.i4.7
0x25450  ldarg.0
0x25451  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_CurrentStorageSizeMB()
0x25456  box      [mscorlib]System.Int32
0x2545b  stelem.ref
0x2545c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25461  stloc.3
0x25462  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x25467  ldarg.0
0x25468  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_OrganizationId()
0x2546d  ldstr    aOrganizationId_0// "Organization.Id"
0x25472  ldstr    aUpdatestorageo// "UpdateStorageObject"
0x25477  ldloc.3
0x25478  ldloc.2
0x25479  ldarg.0
0x2547a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_OrganizationId()
0x2547f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x25484  ldarg.0
0x25485  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationStorageData::get_OrganizationId()
0x2548a  call     void Microsoft.Crm.StorageNotificationUtility::CheckStorageLimit(valuetype [mscorlib]System.Guid orgId)
0x2548f  ldc.i4.1
0x25490  stloc.s  4
0x25492  leave.s  loc_254A0
0x25494  ldloc.0
0x25495  brfalse.s loc_2549D
0x25497  ldloc.0
0x25498  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2549d  endfinally
0x2549e  ldc.i4.0
0x2549f  ret
0x254a0  ldloc.s  4
0x254a2  ret
```
