# Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServer

- ea: `0x20d00`
- end: `0x20e17`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServer`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x17890`
- `0x18790`
- `0x20d00`
- `0x21570`
- `0x21e70`
- `0x22130`

## string_xrefs

- `0x20d87`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`
- `0x20d82`: `MoveServer`
- `0x20db1`: `Moved Server to ScaleGroup, Server Id=({0}), ScaleGroup Id=({1})`

## pseudocode

```c

```

## disassembly

```asm
0x20d00  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20d05  ldc.i4.s 0x14
0x20d07  ldstr    aMovingServerTo// "Moving Server to another ScaleGroup, Se"...
0x20d0c  ldc.i4.2
0x20d0d  newarr   [mscorlib]System.Object
0x20d12  dup
0x20d13  ldc.i4.0
0x20d14  ldarg.1
0x20d15  box      [mscorlib]System.Guid
0x20d1a  stelem.ref
0x20d1b  dup
0x20d1c  ldc.i4.1
0x20d1d  ldarg.2
0x20d1e  box      [mscorlib]System.Guid
0x20d23  stelem.ref
0x20d24  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20d29  ldarg.1
0x20d2a  ldstr    aServerIdentifi// "Server identifier"
0x20d2f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20d34  ldarg.0
0x20d35  ldarg.1
0x20d36  call     instance class Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Admin.AdminService.CrmServerService::Retrieve(valuetype [mscorlib]System.Guid serverId)
0x20d3b  stloc.0
0x20d3c  ldloc.0
0x20d3d  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.ServerState Microsoft.Crm.Admin.AdminService.ServerData::get_State()
0x20d42  stloc.1
0x20d43  ldc.i4.1
0x20d44  ldloc.1
0x20d45  bne.un.s loc_20D5E
0x20d47  ldstr    aServer_1// "Server"
0x20d4c  ldarg.1
0x20d4d  box      [mscorlib]System.Guid
0x20d52  ldloc.1
0x20d53  box      Microsoft.Crm.Admin.AdminService.ServerState
0x20d58  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCannotUpdateObjectDueState(string objectType, object value, class [mscorlib]System.Enum state)
0x20d5d  throw
0x20d5e  ldloc.0
0x20d5f  ldarg.2
0x20d60  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x20d65  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x20d6a  stloc.2
0x20d6b  ldloc.2
0x20d6c  ldstr    aServer_1// "Server"
0x20d71  ldarg.1
0x20d72  box      [mscorlib]System.Guid
0x20d77  ldloc.0
0x20d78  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x20d7d  ldc.i4   0x1AF
0x20d82  ldstr    aMoveserver// "MoveServer"
0x20d87  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x20d8c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x20d91  pop
0x20d92  ldc.i4.s 0x2C
0x20d94  ldarga.s 1
0x20d96  ldstr    aB// "B"
0x20d9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20da0  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x20da5  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x20daa  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20daf  ldc.i4.s 0x14
0x20db1  ldstr    aMovedServerToS// "Moved Server to ScaleGroup, Server Id=("...
0x20db6  ldc.i4.2
0x20db7  newarr   [mscorlib]System.Object
0x20dbc  dup
0x20dbd  ldc.i4.0
0x20dbe  ldarg.1
0x20dbf  box      [mscorlib]System.Guid
0x20dc4  stelem.ref
0x20dc5  dup
0x20dc6  ldc.i4.1
0x20dc7  ldarg.2
0x20dc8  box      [mscorlib]System.Guid
0x20dcd  stelem.ref
0x20dce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20dd3  leave.s  loc_20DDF
0x20dd5  ldloc.2
0x20dd6  brfalse.s loc_20DDE
0x20dd8  ldloc.2
0x20dd9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20dde  endfinally
0x20ddf  leave.s  loc_20E16
0x20de1  stloc.3
0x20de2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20de7  ldc.i4.s 0x14
0x20de9  ldstr    aExceptionInMov// "Exception in moving Server to ScaleGrou"...
0x20dee  ldc.i4.3
0x20def  newarr   [mscorlib]System.Object
0x20df4  dup
0x20df5  ldc.i4.0
0x20df6  ldarg.1
0x20df7  box      [mscorlib]System.Guid
0x20dfc  stelem.ref
0x20dfd  dup
0x20dfe  ldc.i4.1
0x20dff  ldarg.2
0x20e00  box      [mscorlib]System.Guid
0x20e05  stelem.ref
0x20e06  dup
0x20e07  ldc.i4.2
0x20e08  ldloc.3
0x20e09  callvirt instance string [mscorlib]System.Exception::get_Message()
0x20e0e  stelem.ref
0x20e0f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20e14  rethrow
0x20e16  ret
```
