# Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::SetSecurityGroups

- ea: `0x2de10`
- end: `0x2def1`
- name: `Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::SetSecurityGroups`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18790`
- `0x2dca0`
- `0x2de10`
- `0x2dfa0`
- `0x2e330`
- `0x2e370`
- `0x2e3b0`
- `0x2e3f0`

## string_xrefs

- `0x2de22`: `SetSecurityGroups, Sql=({0}) PrivUsr=({1}) PrivRpt=({2}) Rpt=({3})`
- `0x2dea1`: `SetSecurityGroups, Id=({0})`
- `0x2dec8`: `SetSecurityGroups, Id=({0} :{1})`

## pseudocode

```c

```

## disassembly

```asm
0x2de10  ldarg.1
0x2de11  ldstr    aData_0// "data"
0x2de16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2de1b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2de20  ldc.i4.s 0x14
0x2de22  ldstr    aSetsecuritygro// "SetSecurityGroups, Sql=({0}) PrivUsr=({"...
0x2de27  ldc.i4.4
0x2de28  newarr   [mscorlib]System.Object
0x2de2d  dup
0x2de2e  ldc.i4.0
0x2de2f  ldarg.1
0x2de30  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_SqlAccessGroupId()
0x2de35  stloc.0
0x2de36  ldloca.s 0
0x2de38  constrained. [mscorlib]System.Guid
0x2de3e  callvirt instance string [mscorlib]System.Object::ToString()
0x2de43  stelem.ref
0x2de44  dup
0x2de45  ldc.i4.1
0x2de46  ldarg.1
0x2de47  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeUserGroupId()
0x2de4c  stloc.0
0x2de4d  ldloca.s 0
0x2de4f  constrained. [mscorlib]System.Guid
0x2de55  callvirt instance string [mscorlib]System.Object::ToString()
0x2de5a  stelem.ref
0x2de5b  dup
0x2de5c  ldc.i4.2
0x2de5d  ldarg.1
0x2de5e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeReportGroupId()
0x2de63  stloc.0
0x2de64  ldloca.s 0
0x2de66  constrained. [mscorlib]System.Guid
0x2de6c  callvirt instance string [mscorlib]System.Object::ToString()
0x2de71  stelem.ref
0x2de72  dup
0x2de73  ldc.i4.3
0x2de74  ldarg.1
0x2de75  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x2de7a  stloc.0
0x2de7b  ldloca.s 0
0x2de7d  constrained. [mscorlib]System.Guid
0x2de83  callvirt instance string [mscorlib]System.Object::ToString()
0x2de88  stelem.ref
0x2de89  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2de8e  ldarg.0
0x2de8f  ldarg.1
0x2de90  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x2de95  call     instance void Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Update(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x2de9a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2de9f  ldc.i4.s 0x14
0x2dea1  ldstr    aSetsecuritygro_0// "SetSecurityGroups, Id=({0})"
0x2dea6  ldc.i4.1
0x2dea7  newarr   [mscorlib]System.Object
0x2deac  dup
0x2dead  ldc.i4.0
0x2deae  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2deb3  box      [mscorlib]System.Guid
0x2deb8  stelem.ref
0x2deb9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2debe  leave.s  loc_2DEF0
0x2dec0  stloc.1
0x2dec1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2dec6  ldc.i4.s 0x14
0x2dec8  ldstr    aSetsecuritygro_1// "SetSecurityGroups, Id=({0} :{1})"
0x2decd  ldc.i4.2
0x2dece  newarr   [mscorlib]System.Object
0x2ded3  dup
0x2ded4  ldc.i4.0
0x2ded5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2deda  box      [mscorlib]System.Guid
0x2dedf  stelem.ref
0x2dee0  dup
0x2dee1  ldc.i4.1
0x2dee2  ldloc.1
0x2dee3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2dee8  stelem.ref
0x2dee9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2deee  rethrow
0x2def0  ret
```
