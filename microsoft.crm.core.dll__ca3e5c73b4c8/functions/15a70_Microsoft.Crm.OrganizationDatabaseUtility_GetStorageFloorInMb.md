# Microsoft.Crm.OrganizationDatabaseUtility::GetStorageFloorInMb

- ea: `0x15a70`
- end: `0x15bd7`
- name: `Microsoft.Crm.OrganizationDatabaseUtility::GetStorageFloorInMb`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x158c0`

## callees

- `0x4640`
- `0x47a0`
- `0x4c60`
- `0x15a70`
- `0x44400`
- `0x444f0`
- `0x44510`

## string_xrefs

- `0x15aaa`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`
- `0x15b0a`: `D:\a\1\s\src\Platform\Core\DataServices\OrganizationDatabaseUtility.cs`

## pseudocode

```c

```

## disassembly

```asm
0x15a70  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x15a75  stloc.0
0x15a76  ldloc.0
0x15a77  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x15a7c  ldarg.0
0x15a7d  box      [mscorlib]System.Guid
0x15a82  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x15a87  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x15a8c  ldstr    aOrganizationli// "OrganizationLifecycle"
0x15a91  ldc.i4.1
0x15a92  newarr   [mscorlib]System.String
0x15a97  dup
0x15a98  ldc.i4.0
0x15a99  ldstr    aContextid// "ContextId"
0x15a9e  stelem.ref
0x15a9f  ldloc.0
0x15aa0  ldc.i4   0x13E
0x15aa5  ldstr    aGetstoragefloo// "GetStorageFloorInMb"
0x15aaa  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x15aaf  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x15ab4  stloc.1
0x15ab5  ldloc.1
0x15ab6  brfalse  loc_15BD5
0x15abb  ldloc.1
0x15abc  ldstr    aContextid// "ContextId"
0x15ac1  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x15ac6  stloc.2
0x15ac7  ldloc.2
0x15ac8  brfalse  loc_15B78
0x15acd  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x15ad2  stloc.3
0x15ad3  ldloc.3
0x15ad4  ldstr    aContextid// "ContextId"
0x15ad9  ldloc.2
0x15ada  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x15adf  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x15ae4  ldstr    aContext_0// "Context"
0x15ae9  ldc.i4.2
0x15aea  newarr   [mscorlib]System.String
0x15aef  dup
0x15af0  ldc.i4.0
0x15af1  ldstr    aStoragefloorex// "StorageFloorExpiresOn"
0x15af6  stelem.ref
0x15af7  dup
0x15af8  ldc.i4.1
0x15af9  ldstr    aStoragefloormb// "StorageFloorMb"
0x15afe  stelem.ref
0x15aff  ldloc.3
0x15b00  ldc.i4   0x149
0x15b05  ldstr    aGetstoragefloo// "GetStorageFloorInMb"
0x15b0a  ldstr    aDA1SSrcPlatfor_10// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x15b0f  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x15b14  stloc.s  4
0x15b16  ldloc.s  4
0x15b18  brfalse  loc_15BD5
0x15b1d  ldloc.s  4
0x15b1f  ldstr    aStoragefloorex// "StorageFloorExpiresOn"
0x15b24  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x15b29  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x15b2e  stloc.s  5
0x15b30  ldloca.s 5
0x15b32  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x15b37  brfalse  loc_15BD5
0x15b3c  ldloca.s 5
0x15b3e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x15b43  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x15b48  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15b4d  brfalse  loc_15BD5
0x15b52  ldloc.s  4
0x15b54  ldstr    aStoragefloormb// "StorageFloorMb"
0x15b59  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x15b5e  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x15b63  stloc.s  6
0x15b65  ldloca.s 6
0x15b67  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15b6c  brtrue.s loc_15B70
0x15b6e  ldc.i4.0
0x15b6f  ret
0x15b70  ldloca.s 6
0x15b72  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x15b77  ret
0x15b78  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x15b7d  ldarg.0
0x15b7e  ldstr    aStoragefloorex// "StorageFloorExpiresOn"
0x15b83  callvirt instance object Microsoft.Crm.LocatorService::GetOrganizationSetting(valuetype [mscorlib]System.Guid organizationId, string settingName)
0x15b88  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x15b8d  stloc.s  7
0x15b8f  ldloca.s 7
0x15b91  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x15b96  brfalse.s loc_15BD5
0x15b98  ldloca.s 7
0x15b9a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_Value()
0x15b9f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x15ba4  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x15ba9  brfalse.s loc_15BD5
0x15bab  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x15bb0  ldarg.0
0x15bb1  ldstr    aStoragefloormb// "StorageFloorMb"
0x15bb6  callvirt instance object Microsoft.Crm.LocatorService::GetOrganizationSetting(valuetype [mscorlib]System.Guid organizationId, string settingName)
0x15bbb  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x15bc0  stloc.s  6
0x15bc2  ldloca.s 6
0x15bc4  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x15bc9  brtrue.s loc_15BCD
0x15bcb  ldc.i4.0
0x15bcc  ret
0x15bcd  ldloca.s 6
0x15bcf  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x15bd4  ret
0x15bd5  ldc.i4.0
0x15bd6  ret
```
