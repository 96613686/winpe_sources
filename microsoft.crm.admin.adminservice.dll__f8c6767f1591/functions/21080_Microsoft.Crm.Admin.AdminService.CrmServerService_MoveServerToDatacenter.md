# Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServerToDatacenter

- ea: `0x21080`
- end: `0x21180`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::MoveServerToDatacenter`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18790`
- `0x21080`
- `0x21570`
- `0x21f00`

## string_xrefs

- `0x210f0`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`
- `0x210eb`: `MoveServerToDatacenter`
- `0x2111a`: `Moved Server to Datacenter, Server Id=({0}), Datacenter Id=({1})`

## pseudocode

```c

```

## disassembly

```asm
0x21080  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21085  ldc.i4.s 0x14
0x21087  ldstr    aMovingServerTo_2// "Moving Server to another Datacenter, Se"...
0x2108c  ldc.i4.2
0x2108d  newarr   [mscorlib]System.Object
0x21092  dup
0x21093  ldc.i4.0
0x21094  ldarg.1
0x21095  box      [mscorlib]System.Guid
0x2109a  stelem.ref
0x2109b  dup
0x2109c  ldc.i4.1
0x2109d  ldarg.2
0x2109e  box      [mscorlib]System.Guid
0x210a3  stelem.ref
0x210a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x210a9  ldarg.1
0x210aa  ldstr    aServerIdentifi// "Server identifier"
0x210af  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x210b4  ldarg.2
0x210b5  ldstr    aDatacenterIden// "Datacenter identifier"
0x210ba  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x210bf  ldarg.0
0x210c0  ldarg.1
0x210c1  call     instance class Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Admin.AdminService.CrmServerService::Retrieve(valuetype [mscorlib]System.Guid serverId)
0x210c6  stloc.0
0x210c7  ldloc.0
0x210c8  ldarg.2
0x210c9  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x210ce  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x210d3  stloc.1
0x210d4  ldloc.1
0x210d5  ldstr    aServer_1// "Server"
0x210da  ldarg.1
0x210db  box      [mscorlib]System.Guid
0x210e0  ldloc.0
0x210e1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x210e6  ldc.i4   0x21B
0x210eb  ldstr    aMoveservertoda// "MoveServerToDatacenter"
0x210f0  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x210f5  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x210fa  pop
0x210fb  ldc.i4.s 0x2C
0x210fd  ldarga.s 1
0x210ff  ldstr    aB// "B"
0x21104  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21109  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x2110e  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x21113  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21118  ldc.i4.s 0x14
0x2111a  ldstr    aMovedServerToD// "Moved Server to Datacenter, Server Id=("...
0x2111f  ldc.i4.2
0x21120  newarr   [mscorlib]System.Object
0x21125  dup
0x21126  ldc.i4.0
0x21127  ldarg.1
0x21128  box      [mscorlib]System.Guid
0x2112d  stelem.ref
0x2112e  dup
0x2112f  ldc.i4.1
0x21130  ldarg.2
0x21131  box      [mscorlib]System.Guid
0x21136  stelem.ref
0x21137  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2113c  leave.s  loc_21148
0x2113e  ldloc.1
0x2113f  brfalse.s loc_21147
0x21141  ldloc.1
0x21142  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21147  endfinally
0x21148  leave.s  loc_2117F
0x2114a  stloc.2
0x2114b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21150  ldc.i4.s 0x14
0x21152  ldstr    aExceptionInMov_2// "Exception in moving Server to Pod, Serv"...
0x21157  ldc.i4.3
0x21158  newarr   [mscorlib]System.Object
0x2115d  dup
0x2115e  ldc.i4.0
0x2115f  ldarg.1
0x21160  box      [mscorlib]System.Guid
0x21165  stelem.ref
0x21166  dup
0x21167  ldc.i4.1
0x21168  ldarg.2
0x21169  box      [mscorlib]System.Guid
0x2116e  stelem.ref
0x2116f  dup
0x21170  ldc.i4.2
0x21171  ldloc.2
0x21172  callvirt instance string [mscorlib]System.Exception::get_Message()
0x21177  stelem.ref
0x21178  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2117d  rethrow
0x2117f  ret
```
