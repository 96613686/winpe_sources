# Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServerToPod

- ea: `0x20f50`
- end: `0x21072`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServerToPod`
- size: `290`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x17890`
- `0x18790`
- `0x20f50`
- `0x21570`
- `0x21f50`
- `0x22130`

## string_xrefs

- `0x20fe2`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`
- `0x20fdd`: `MoveServerToPod`
- `0x2100c`: `Moved Server to Pod, Server Id=({0}), Pod Id=({1})`

## pseudocode

```c

```

## disassembly

```asm
0x20f50  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20f55  ldc.i4.s 0x14
0x20f57  ldstr    aMovingServerTo_1// "Moving Server to another Pod, Server Id"...
0x20f5c  ldc.i4.2
0x20f5d  newarr   [mscorlib]System.Object
0x20f62  dup
0x20f63  ldc.i4.0
0x20f64  ldarg.1
0x20f65  box      [mscorlib]System.Guid
0x20f6a  stelem.ref
0x20f6b  dup
0x20f6c  ldc.i4.1
0x20f6d  ldarg.2
0x20f6e  box      [mscorlib]System.Guid
0x20f73  stelem.ref
0x20f74  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20f79  ldarg.1
0x20f7a  ldstr    aServerIdentifi// "Server identifier"
0x20f7f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20f84  ldarg.2
0x20f85  ldstr    aPodIdentifier// "Pod identifier"
0x20f8a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20f8f  ldarg.0
0x20f90  ldarg.1
0x20f91  call     instance class Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Admin.AdminService.CrmServerService::Retrieve(valuetype [mscorlib]System.Guid serverId)
0x20f96  stloc.0
0x20f97  ldloc.0
0x20f98  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.ServerState Microsoft.Crm.Admin.AdminService.ServerData::get_State()
0x20f9d  stloc.1
0x20f9e  ldc.i4.1
0x20f9f  ldloc.1
0x20fa0  bne.un.s loc_20FB9
0x20fa2  ldstr    aServer_1// "Server"
0x20fa7  ldarg.1
0x20fa8  box      [mscorlib]System.Guid
0x20fad  ldloc.1
0x20fae  box      Microsoft.Crm.Admin.AdminService.ServerState
0x20fb3  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBCannotUpdateObjectDueState(string objectType, object value, class [mscorlib]System.Enum state)
0x20fb8  throw
0x20fb9  ldloc.0
0x20fba  ldarg.2
0x20fbb  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_PodId(valuetype [mscorlib]System.Guid value)
0x20fc0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x20fc5  stloc.2
0x20fc6  ldloc.2
0x20fc7  ldstr    aServer_1// "Server"
0x20fcc  ldarg.1
0x20fcd  box      [mscorlib]System.Guid
0x20fd2  ldloc.0
0x20fd3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x20fd8  ldc.i4   0x1FB
0x20fdd  ldstr    aMoveservertopo// "MoveServerToPod"
0x20fe2  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x20fe7  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x20fec  pop
0x20fed  ldc.i4.s 0x2C
0x20fef  ldarga.s 1
0x20ff1  ldstr    aB// "B"
0x20ff6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20ffb  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x21000  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x21005  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2100a  ldc.i4.s 0x14
0x2100c  ldstr    aMovedServerToP// "Moved Server to Pod, Server Id=({0}), P"...
0x21011  ldc.i4.2
0x21012  newarr   [mscorlib]System.Object
0x21017  dup
0x21018  ldc.i4.0
0x21019  ldarg.1
0x2101a  box      [mscorlib]System.Guid
0x2101f  stelem.ref
0x21020  dup
0x21021  ldc.i4.1
0x21022  ldarg.2
0x21023  box      [mscorlib]System.Guid
0x21028  stelem.ref
0x21029  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2102e  leave.s  loc_2103A
0x21030  ldloc.2
0x21031  brfalse.s loc_21039
0x21033  ldloc.2
0x21034  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21039  endfinally
0x2103a  leave.s  loc_21071
0x2103c  stloc.3
0x2103d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21042  ldc.i4.s 0x14
0x21044  ldstr    aExceptionInMov_1// "Exception in moving Server to Pod, Serv"...
0x21049  ldc.i4.3
0x2104a  newarr   [mscorlib]System.Object
0x2104f  dup
0x21050  ldc.i4.0
0x21051  ldarg.1
0x21052  box      [mscorlib]System.Guid
0x21057  stelem.ref
0x21058  dup
0x21059  ldc.i4.1
0x2105a  ldarg.2
0x2105b  box      [mscorlib]System.Guid
0x21060  stelem.ref
0x21061  dup
0x21062  ldc.i4.2
0x21063  ldloc.3
0x21064  callvirt instance string [mscorlib]System.Exception::get_Message()
0x21069  stelem.ref
0x2106a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2106f  rethrow
0x21071  ret
```
