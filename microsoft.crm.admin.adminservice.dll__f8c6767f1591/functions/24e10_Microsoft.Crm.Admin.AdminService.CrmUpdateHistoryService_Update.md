# Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Update

- ea: `0x24e10`
- end: `0x24ed4`
- name: `Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Update`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18790`
- `0x24e10`
- `0x250d0`

## string_xrefs

- `0x24e84`: `Update`
- `0x24e69`: `UpdateHistory`
- `0x24e89`: `D:\a\1\s\src\CrmLive\Admin\UpdateHistory\CrmUpdateHistoryService.cs`
- `0x24e21`: `UpdateHistory identifier`
- `0x24e11`: `UpdateHistoryData`
- `0x24e32`: `Updating UpdateHistory state, Id=({0}))`
- `0x24eaa`: `Exception Update UpdateHistory, Id=({0} : {1})`

## pseudocode

```c

```

## disassembly

```asm
0x24e10  ldarg.1
0x24e11  ldstr    aUpdatehistoryd// "UpdateHistoryData"
0x24e16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x24e1b  ldarg.1
0x24e1c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UpdateHistoryData::get_Id()
0x24e21  ldstr    aUpdatehistoryI_0// "UpdateHistory identifier"
0x24e26  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x24e2b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24e30  ldc.i4.s 9
0x24e32  ldstr    aUpdatingUpdate// "Updating UpdateHistory state, Id=({0}))"
0x24e37  ldc.i4.1
0x24e38  newarr   [mscorlib]System.Object
0x24e3d  dup
0x24e3e  ldc.i4.0
0x24e3f  ldarg.1
0x24e40  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UpdateHistoryData::get_Id()
0x24e45  box      [mscorlib]System.Guid
0x24e4a  stelem.ref
0x24e4b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24e50  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x24e55  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x24e5a  stloc.0
0x24e5b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24e60  stloc.1
0x24e61  ldloc.1
0x24e62  ldloc.0
0x24e63  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x24e68  ldloc.1
0x24e69  ldstr    aUpdatehistory// "UpdateHistory"
0x24e6e  ldarg.1
0x24e6f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UpdateHistoryData::get_Id()
0x24e74  box      [mscorlib]System.Guid
0x24e79  ldarg.1
0x24e7a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x24e7f  ldc.i4   0x81
0x24e84  ldstr    aUpdate// "Update"
0x24e89  ldstr    aDA1SSrcCrmlive_49// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Updat"...
0x24e8e  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x24e93  pop
0x24e94  leave.s  loc_24EA0
0x24e96  ldloc.1
0x24e97  brfalse.s loc_24E9F
0x24e99  ldloc.1
0x24e9a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24e9f  endfinally
0x24ea0  leave.s  loc_24ED3
0x24ea2  stloc.2
0x24ea3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24ea8  ldc.i4.s 9
0x24eaa  ldstr    aExceptionUpdat// "Exception Update UpdateHistory, Id=({0}"...
0x24eaf  ldc.i4.2
0x24eb0  newarr   [mscorlib]System.Object
0x24eb5  dup
0x24eb6  ldc.i4.0
0x24eb7  ldarg.1
0x24eb8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UpdateHistoryData::get_Id()
0x24ebd  box      [mscorlib]System.Guid
0x24ec2  stelem.ref
0x24ec3  dup
0x24ec4  ldc.i4.1
0x24ec5  ldloc.2
0x24ec6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24ecb  stelem.ref
0x24ecc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24ed1  rethrow
0x24ed3  ret
```
