# Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::Delete

- ea: `0x22ce0`
- end: `0x22d89`
- name: `Microsoft.Crm.Admin.AdminService.CrmStorageGroupService::Delete`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x22ce0`

## string_xrefs

- `0x22d1f`: `Delete`
- `0x22d24`: `D:\a\1\s\src\CrmLive\Admin\StorageGroup\CrmStorageGroupService.cs`
- `0x22d35`: `Deleted StorageGroup, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x22ce0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22ce5  ldc.i4.s 9
0x22ce7  ldstr    aDeletingStorag// "Deleting StorageGroup, Id=({0})"
0x22cec  ldc.i4.1
0x22ced  newarr   [mscorlib]System.Object
0x22cf2  dup
0x22cf3  ldc.i4.0
0x22cf4  ldarg.1
0x22cf5  box      [mscorlib]System.Guid
0x22cfa  stelem.ref
0x22cfb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22d00  ldarg.1
0x22d01  ldstr    aStoragegroupId// "StorageGroup identifier"
0x22d06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x22d0b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x22d10  stloc.0
0x22d11  ldloc.0
0x22d12  ldstr    aStoragegroup// "StorageGroup"
0x22d17  ldarg.1
0x22d18  box      [mscorlib]System.Guid
0x22d1d  ldc.i4.s 0x7F
0x22d1f  ldstr    aDelete// "Delete"
0x22d24  ldstr    aDA1SSrcCrmlive_45// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Stora"...
0x22d29  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x22d2e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22d33  ldc.i4.s 9
0x22d35  ldstr    aDeletedStorage// "Deleted StorageGroup, Id=({0})"
0x22d3a  ldc.i4.1
0x22d3b  newarr   [mscorlib]System.Object
0x22d40  dup
0x22d41  ldc.i4.0
0x22d42  ldarg.1
0x22d43  box      [mscorlib]System.Guid
0x22d48  stelem.ref
0x22d49  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22d4e  leave.s  loc_22D5A
0x22d50  ldloc.0
0x22d51  brfalse.s loc_22D59
0x22d53  ldloc.0
0x22d54  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22d59  endfinally
0x22d5a  leave.s  loc_22D88
0x22d5c  stloc.1
0x22d5d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x22d62  ldc.i4.s 9
0x22d64  ldstr    aExceptionDelet_5// "Exception deleting StorageGroup, Id=({0"...
0x22d69  ldc.i4.2
0x22d6a  newarr   [mscorlib]System.Object
0x22d6f  dup
0x22d70  ldc.i4.0
0x22d71  ldarg.1
0x22d72  box      [mscorlib]System.Guid
0x22d77  stelem.ref
0x22d78  dup
0x22d79  ldc.i4.1
0x22d7a  ldloc.1
0x22d7b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x22d80  stelem.ref
0x22d81  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x22d86  rethrow
0x22d88  ret
```
