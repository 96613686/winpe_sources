# Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Create

- ea: `0x24c10`
- end: `0x24d52`
- name: `Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::Create`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x18790`
- `0x24c10`
- `0x250b0`
- `0x250d0`
- `0x250f0`
- `0x25130`
- `0x25170`
- `0x251b0`
- `0x251f0`
- `0x25230`
- `0x25260`
- `0x252a0`
- `0x252e0`
- `0x25320`

## string_xrefs

- `0x24cca`: `Create`
- `0x24c46`: `Creating UpdateHistory`
- `0x24cbd`: `UpdateHistory`
- `0x24ccf`: `D:\a\1\s\src\CrmLive\Admin\UpdateHistory\CrmUpdateHistoryService.cs`
- `0x24ced`: `UpdateHistory Ids are not equal`
- `0x24cff`: `Created UpdateHistory, Id=({0})`
- `0x24d34`: `Exception creating UpdateHistory exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x24c10  ldarg.2
0x24c11  ldstr    aUnitname// "unitName"
0x24c16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x24c1b  ldarg.s  4
0x24c1d  ldstr    aBuildversion_0// "buildVersion"
0x24c22  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x24c27  ldarg.s  5
0x24c29  ldstr    aLoglocation// "logLocation"
0x24c2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x24c33  ldarg.s  6
0x24c35  ldstr    aRelease_0// "release"
0x24c3a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x24c3f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24c44  ldc.i4.s 9
0x24c46  ldstr    aCreatingUpdate// "Creating UpdateHistory"
0x24c4b  ldc.i4.0
0x24c4c  newarr   [mscorlib]System.Object
0x24c51  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24c56  newobj   instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::.ctor()
0x24c5b  stloc.0
0x24c5c  ldloc.0
0x24c5d  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x24c62  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_Id(valuetype [mscorlib]System.Guid value)
0x24c67  ldloc.0
0x24c68  ldarg.1
0x24c69  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_Unit(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.UnitScope value)
0x24c6e  ldloc.0
0x24c6f  ldarg.2
0x24c70  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_UnitName(string value)
0x24c75  ldloc.0
0x24c76  ldarg.3
0x24c77  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_Operation(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.UpdateOperation value)
0x24c7c  ldloc.0
0x24c7d  ldarg.s  4
0x24c7f  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_BuildVersion(string value)
0x24c84  ldloc.0
0x24c85  ldarg.s  5
0x24c87  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_LogLocation(string value)
0x24c8c  ldloc.0
0x24c8d  ldarg.s  6
0x24c8f  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_Release(string value)
0x24c94  ldloc.0
0x24c95  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x24c9a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x24c9f  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_StartTime(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> value)
0x24ca4  ldloc.0
0x24ca5  ldc.i4.2
0x24ca6  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_Status(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OperationStatus value)
0x24cab  ldloc.0
0x24cac  ldsfld   string [mscorlib]System.String::Empty
0x24cb1  callvirt instance void Microsoft.Crm.Admin.AdminService.UpdateHistoryData::set_Details(string value)
0x24cb6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24cbb  stloc.1
0x24cbc  ldloc.1
0x24cbd  ldstr    aUpdatehistory// "UpdateHistory"
0x24cc2  ldloc.0
0x24cc3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x24cc8  ldc.i4.s 0x41
0x24cca  ldstr    aCreate// "Create"
0x24ccf  ldstr    aDA1SSrcCrmlive_49// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Updat"...
0x24cd4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x24cd9  unbox.any [mscorlib]System.Guid
0x24cde  stloc.2
0x24cdf  ldloc.0
0x24ce0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UpdateHistoryData::get_Id()
0x24ce5  ldloc.2
0x24ce6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x24ceb  brfalse.s loc_24CF8
0x24ced  ldstr    aUpdatehistoryI// "UpdateHistory Ids are not equal"
0x24cf2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x24cf7  throw
0x24cf8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24cfd  ldc.i4.s 9
0x24cff  ldstr    aCreatedUpdateh// "Created UpdateHistory, Id=({0})"
0x24d04  ldc.i4.1
0x24d05  newarr   [mscorlib]System.Object
0x24d0a  dup
0x24d0b  ldc.i4.0
0x24d0c  ldloc.0
0x24d0d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.UpdateHistoryData::get_Id()
0x24d12  box      [mscorlib]System.Guid
0x24d17  stelem.ref
0x24d18  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24d1d  ldloc.2
0x24d1e  stloc.3
0x24d1f  leave.s  loc_24D50
0x24d21  ldloc.1
0x24d22  brfalse.s loc_24D2A
0x24d24  ldloc.1
0x24d25  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24d2a  endfinally
0x24d2b  stloc.s  4
0x24d2d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24d32  ldc.i4.s 9
0x24d34  ldstr    aExceptionCreat_6// "Exception creating UpdateHistory except"...
0x24d39  ldc.i4.1
0x24d3a  newarr   [mscorlib]System.Object
0x24d3f  dup
0x24d40  ldc.i4.0
0x24d41  ldloc.s  4
0x24d43  callvirt instance string [mscorlib]System.Exception::get_Message()
0x24d48  stelem.ref
0x24d49  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24d4e  rethrow
0x24d50  ldloc.3
0x24d51  ret
```
