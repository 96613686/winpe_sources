# Microsoft.Crm.Admin.AdminService.CrmDatacenterService::Delete

- ea: `0x1a150`
- end: `0x1a20c`
- name: `Microsoft.Crm.Admin.AdminService.CrmDatacenterService::Delete`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x17870`
- `0x1a150`
- `0x20730`
- `0x21670`
- `0x22290`
- `0x22300`

## string_xrefs

- `0x1a1d0`: `Delete`
- `0x1a1d5`: `D:\a\1\s\src\CrmLive\Admin\Datacenter\CrmDatacenterService.cs`
- `0x1a1e6`: `Deleted Datacenter, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1a150  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1a155  ldc.i4.s 9
0x1a157  ldstr    aDeletingDatace// "Deleting Datacenter, Id=({0})"
0x1a15c  ldc.i4.1
0x1a15d  newarr   [mscorlib]System.Object
0x1a162  dup
0x1a163  ldc.i4.0
0x1a164  ldarg.1
0x1a165  box      [mscorlib]System.Guid
0x1a16a  stelem.ref
0x1a16b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a170  ldarg.1
0x1a171  ldstr    aDatacenterIden// "Datacenter identifier"
0x1a176  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1a17b  newobj   instance void Microsoft.Crm.Admin.AdminService.ServerFilter::.ctor()
0x1a180  stloc.0
0x1a181  ldloc.0
0x1a182  ldarg.1
0x1a183  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerFilter::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x1a188  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmServerService::.ctor()
0x1a18d  ldloc.0
0x1a18e  callvirt instance class Microsoft.Crm.Admin.AdminService.ServerData[] Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveMultiple(class Microsoft.Crm.Admin.AdminService.ServerFilter filter)
0x1a193  stloc.1
0x1a194  ldloc.1
0x1a195  ldstr    aArrserverdata// "arrServerData"
0x1a19a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1a19f  ldloc.1
0x1a1a0  ldlen
0x1a1a1  brfalse.s loc_1A1B9
0x1a1a3  ldstr    aDatacenter// "Datacenter"
0x1a1a8  ldarg.1
0x1a1a9  box      [mscorlib]System.Guid
0x1a1ae  ldstr    aServer_1// "Server"
0x1a1b3  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCascadeDeleteNotAllowDelete(string objectType, object value, string objectTypeChild)
0x1a1b8  throw
0x1a1b9  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1a1be  stloc.2
0x1a1bf  ldloc.2
0x1a1c0  ldstr    aDatacenter// "Datacenter"
0x1a1c5  ldarg.1
0x1a1c6  box      [mscorlib]System.Guid
0x1a1cb  ldc.i4   0xC0
0x1a1d0  ldstr    aDelete// "Delete"
0x1a1d5  ldstr    aDA1SSrcCrmlive_35// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Datac"...
0x1a1da  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1a1df  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1a1e4  ldc.i4.s 9
0x1a1e6  ldstr    aDeletedDatacen// "Deleted Datacenter, Id=({0})"
0x1a1eb  ldc.i4.1
0x1a1ec  newarr   [mscorlib]System.Object
0x1a1f1  dup
0x1a1f2  ldc.i4.0
0x1a1f3  ldarg.1
0x1a1f4  box      [mscorlib]System.Guid
0x1a1f9  stelem.ref
0x1a1fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a1ff  leave.s  loc_1A20B
0x1a201  ldloc.2
0x1a202  brfalse.s loc_1A20A
0x1a204  ldloc.2
0x1a205  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a20a  endfinally
0x1a20b  ret
```
