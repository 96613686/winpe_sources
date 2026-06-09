# Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Retrieve

- ea: `0x24ee0`
- end: `0x24f9c`
- name: `Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Retrieve`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x17810`
- `0x24ee0`
- `0x250c0`

## string_xrefs

- `0x24f24`: `UpdateHistory`
- `0x24f48`: `UpdateHistory`
- `0x24f3a`: `D:\a\1\s\src\CrmLive\Admin\UpdateHistory\CrmUpdateHistoryService.cs`
- `0x24ee1`: `UpdateHistory identifier`
- `0x24ef2`: `Retrieve UpdateHistory, Id=({0})`
- `0x24f75`: `Exception in retrieve UpdateHistory, Id=({0} : {1})`

## pseudocode

```c

```

## disassembly

```asm
0x24ee0  ldarg.1
0x24ee1  ldstr    aUpdatehistoryI_0// "UpdateHistory identifier"
0x24ee6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x24eeb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24ef0  ldc.i4.s 9
0x24ef2  ldstr    aRetrieveUpdate// "Retrieve UpdateHistory, Id=({0})"
0x24ef7  ldc.i4.1
0x24ef8  newarr   [mscorlib]System.Object
0x24efd  dup
0x24efe  ldc.i4.0
0x24eff  ldarg.1
0x24f00  box      [mscorlib]System.Guid
0x24f05  stelem.ref
0x24f06  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24f0b  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x24f10  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x24f15  stloc.0
0x24f16  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24f1b  stloc.1
0x24f1c  ldloc.1
0x24f1d  ldloc.0
0x24f1e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x24f23  ldloc.1
0x24f24  ldstr    aUpdatehistory// "UpdateHistory"
0x24f29  ldarg.1
0x24f2a  box      [mscorlib]System.Guid
0x24f2f  ldnull
0x24f30  ldc.i4   0x9E
0x24f35  ldstr    aRetrieve// "Retrieve"
0x24f3a  ldstr    aDA1SSrcCrmlive_49// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Updat"...
0x24f3f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x24f44  stloc.2
0x24f45  ldloc.2
0x24f46  brtrue.s loc_24F59
0x24f48  ldstr    aUpdatehistory// "UpdateHistory"
0x24f4d  ldarg.1
0x24f4e  box      [mscorlib]System.Guid
0x24f53  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBObjectDoesNotExist(string objectType, object value)
0x24f58  throw
0x24f59  ldloc.2
0x24f5a  newobj   instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x24f5f  stloc.3
0x24f60  leave.s  loc_24F9A
0x24f62  ldloc.1
0x24f63  brfalse.s loc_24F6B
0x24f65  ldloc.1
0x24f66  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24f6b  endfinally
0x24f6c  stloc.s  4
0x24f6e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24f73  ldc.i4.s 9
0x24f75  ldstr    aExceptionInRet_12// "Exception in retrieve UpdateHistory, Id"...
0x24f7a  ldc.i4.2
0x24f7b  newarr   [mscorlib]System.Object
0x24f80  dup
0x24f81  ldc.i4.0
0x24f82  ldarg.1
0x24f83  box      [mscorlib]System.Guid
0x24f88  stelem.ref
0x24f89  dup
0x24f8a  ldc.i4.1
0x24f8b  ldloc.s  4
0x24f8d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24f92  stelem.ref
0x24f93  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24f98  rethrow
0x24f9a  ldloc.3
0x24f9b  ret
```
