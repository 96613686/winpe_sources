# Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServerToStorageGroup

- ea: `0x20e20`
- end: `0x20f42`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServerToStorageGroup`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x17890`
- `0x18790`
- `0x20e20`
- `0x21570`
- `0x21ec0`
- `0x22130`

## string_xrefs

- `0x20eb2`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`
- `0x20ead`: `MoveServerToStorageGroup`
- `0x20edc`: `Moved Server to StorageGroup, Server Id=({0}), StorageGroup Id=({1})`

## pseudocode

```c

```

## disassembly

```asm
0x20e20  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20e25  ldc.i4.s 0x14
0x20e27  ldstr    aMovingServerTo_0// "Moving Server to another StorageGroup, "...
0x20e2c  ldc.i4.2
0x20e2d  newarr   [mscorlib]System.Object
0x20e32  dup
0x20e33  ldc.i4.0
0x20e34  ldarg.1
0x20e35  box      [mscorlib]System.Guid
0x20e3a  stelem.ref
0x20e3b  dup
0x20e3c  ldc.i4.1
0x20e3d  ldarg.2
0x20e3e  box      [mscorlib]System.Guid
0x20e43  stelem.ref
0x20e44  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20e49  ldarg.1
0x20e4a  ldstr    aServerIdentifi// "Server identifier"
0x20e4f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20e54  ldarg.2
0x20e55  ldstr    aStoragegroupId// "StorageGroup identifier"
0x20e5a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20e5f  ldarg.0
0x20e60  ldarg.1
0x20e61  call     instance class Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Admin.AdminService.CrmServerService::Retrieve(valuetype [mscorlib]System.Guid serverId)
0x20e66  stloc.0
0x20e67  ldloc.0
0x20e68  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.ServerState Microsoft.Crm.Admin.AdminService.ServerData::get_State()
0x20e6d  stloc.1
0x20e6e  ldc.i4.1
0x20e6f  ldloc.1
0x20e70  bne.un.s loc_20E89
0x20e72  ldstr    aServer_1// "Server"
0x20e77  ldarg.1
0x20e78  box      [mscorlib]System.Guid
0x20e7d  ldloc.1
0x20e7e  box      Microsoft.Crm.Admin.AdminService.ServerState
0x20e83  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCannotUpdateObjectDueState(string objectType, object value, class [mscorlib]System.Enum state)
0x20e88  throw
0x20e89  ldloc.0
0x20e8a  ldarg.2
0x20e8b  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_StorageGroupId(valuetype [mscorlib]System.Guid value)
0x20e90  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x20e95  stloc.2
0x20e96  ldloc.2
0x20e97  ldstr    aServer_1// "Server"
0x20e9c  ldarg.1
0x20e9d  box      [mscorlib]System.Guid
0x20ea2  ldloc.0
0x20ea3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x20ea8  ldc.i4   0x1D5
0x20ead  ldstr    aMoveservertost// "MoveServerToStorageGroup"
0x20eb2  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x20eb7  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x20ebc  pop
0x20ebd  ldc.i4.s 0x2C
0x20ebf  ldarga.s 1
0x20ec1  ldstr    aB// "B"
0x20ec6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20ecb  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x20ed0  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x20ed5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20eda  ldc.i4.s 0x14
0x20edc  ldstr    aMovedServerToS_0// "Moved Server to StorageGroup, Server Id"...
0x20ee1  ldc.i4.2
0x20ee2  newarr   [mscorlib]System.Object
0x20ee7  dup
0x20ee8  ldc.i4.0
0x20ee9  ldarg.1
0x20eea  box      [mscorlib]System.Guid
0x20eef  stelem.ref
0x20ef0  dup
0x20ef1  ldc.i4.1
0x20ef2  ldarg.2
0x20ef3  box      [mscorlib]System.Guid
0x20ef8  stelem.ref
0x20ef9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20efe  leave.s  loc_20F0A
0x20f00  ldloc.2
0x20f01  brfalse.s loc_20F09
0x20f03  ldloc.2
0x20f04  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20f09  endfinally
0x20f0a  leave.s  loc_20F41
0x20f0c  stloc.3
0x20f0d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20f12  ldc.i4.s 0x14
0x20f14  ldstr    aExceptionInMov_0// "Exception in moving Server to StorageGr"...
0x20f19  ldc.i4.3
0x20f1a  newarr   [mscorlib]System.Object
0x20f1f  dup
0x20f20  ldc.i4.0
0x20f21  ldarg.1
0x20f22  box      [mscorlib]System.Guid
0x20f27  stelem.ref
0x20f28  dup
0x20f29  ldc.i4.1
0x20f2a  ldarg.2
0x20f2b  box      [mscorlib]System.Guid
0x20f30  stelem.ref
0x20f31  dup
0x20f32  ldc.i4.2
0x20f33  ldloc.3
0x20f34  callvirt instance string [mscorlib]System.Exception::get_Message()
0x20f39  stelem.ref
0x20f3a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20f3f  rethrow
0x20f41  ret
```
