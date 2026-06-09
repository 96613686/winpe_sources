# Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::GetSecurityGroups

- ea: `0x2e060`
- end: `0x2e1cf`
- name: `Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::GetSecurityGroups`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x2dca0`
- `0x2e060`
- `0x2e1d0`
- `0x2e200`
- `0x2e310`
- `0x2e330`
- `0x2e350`
- `0x2e370`
- `0x2e390`
- `0x2e3b0`
- `0x2e3d0`
- `0x2e3f0`
- `0x2e410`

## string_xrefs

- `0x2e151`: `SetSecurityGroups, Sql=({0}) PrivUsr=({1}) PrivRpt=({2}) Rpt=({3})`
- `0x2e067`: `GetSecurityGroups)`
- `0x2e08c`: `SqlAccessGroupId`
- `0x2e09b`: `ConfigSettingOverride_SqlAccessGroupId`
- `0x2e0ac`: `PrivilegeUserGroupId`
- `0x2e0bb`: `ConfigSettingOverride_PrivilegeUserGroupId`
- `0x2e0cc`: `PrivilegeReportGroupId`
- `0x2e0db`: `ConfigSettingOverride_PrivilegeReportGroupId`
- `0x2e0fb`: `ConfigSettingOverride_ReportingGroupId`
- `0x2e110`: `data.SqlAccessGroupId`
- `0x2e120`: `data.PrivilegeUserGroupId`
- `0x2e130`: `data.PrivilegeReportGroupId`
- `0x2e1a5`: `Exception GetSecurityGroups, Id=({0} :{1})`

## pseudocode

```c

```

## disassembly

```asm
0x2e060  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2e065  ldc.i4.s 0x14
0x2e067  ldstr    aGetsecuritygro// "GetSecurityGroups)"
0x2e06c  ldc.i4.0
0x2e06d  newarr   [mscorlib]System.Object
0x2e072  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e077  ldarg.0
0x2e078  ldc.i4.0
0x2e079  newarr   [mscorlib]System.String
0x2e07e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve(string[] columns)
0x2e083  stloc.0
0x2e084  newobj   instance void Microsoft.Crm.Admin.AdminService.SecurityGroupsData::.ctor()
0x2e089  stloc.1
0x2e08a  ldloc.1
0x2e08b  ldloc.0
0x2e08c  ldstr    aSqlaccessgroup// "SqlAccessGroupId"
0x2e091  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2e096  unbox.any [mscorlib]System.Guid
0x2e09b  ldstr    aConfigsettingo// "ConfigSettingOverride_SqlAccessGroupId"
0x2e0a0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::ResolveSetting(valuetype [mscorlib]System.Guid value, string registryOverride)
0x2e0a5  callvirt instance void Microsoft.Crm.Admin.AdminService.SecurityGroupsData::set_SqlAccessGroupId(valuetype [mscorlib]System.Guid value)
0x2e0aa  ldloc.1
0x2e0ab  ldloc.0
0x2e0ac  ldstr    aPrivilegeuserg// "PrivilegeUserGroupId"
0x2e0b1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2e0b6  unbox.any [mscorlib]System.Guid
0x2e0bb  ldstr    aConfigsettingo_0// "ConfigSettingOverride_PrivilegeUserGrou"...
0x2e0c0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::ResolveSetting(valuetype [mscorlib]System.Guid value, string registryOverride)
0x2e0c5  callvirt instance void Microsoft.Crm.Admin.AdminService.SecurityGroupsData::set_PrivilegeUserGroupId(valuetype [mscorlib]System.Guid value)
0x2e0ca  ldloc.1
0x2e0cb  ldloc.0
0x2e0cc  ldstr    aPrivilegerepor// "PrivilegeReportGroupId"
0x2e0d1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2e0d6  unbox.any [mscorlib]System.Guid
0x2e0db  ldstr    aConfigsettingo_1// "ConfigSettingOverride_PrivilegeReportGr"...
0x2e0e0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::ResolveSetting(valuetype [mscorlib]System.Guid value, string registryOverride)
0x2e0e5  callvirt instance void Microsoft.Crm.Admin.AdminService.SecurityGroupsData::set_PrivilegeReportGroupId(valuetype [mscorlib]System.Guid value)
0x2e0ea  ldloc.1
0x2e0eb  ldloc.0
0x2e0ec  ldstr    aReportinggroup// "ReportingGroupId"
0x2e0f1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2e0f6  unbox.any [mscorlib]System.Guid
0x2e0fb  ldstr    aConfigsettingo_2// "ConfigSettingOverride_ReportingGroupId"
0x2e100  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::ResolveSetting(valuetype [mscorlib]System.Guid value, string registryOverride)
0x2e105  callvirt instance void Microsoft.Crm.Admin.AdminService.SecurityGroupsData::set_ReportingGroupId(valuetype [mscorlib]System.Guid value)
0x2e10a  ldloc.1
0x2e10b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_SqlAccessGroupId()
0x2e110  ldstr    aDataSqlaccessg// "data.SqlAccessGroupId"
0x2e115  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2e11a  ldloc.1
0x2e11b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeUserGroupId()
0x2e120  ldstr    aDataPrivilegeu// "data.PrivilegeUserGroupId"
0x2e125  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2e12a  ldloc.1
0x2e12b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeReportGroupId()
0x2e130  ldstr    aDataPrivileger// "data.PrivilegeReportGroupId"
0x2e135  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2e13a  ldloc.1
0x2e13b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x2e140  ldstr    aDataReportingg// "data.ReportingGroupId"
0x2e145  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2e14a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2e14f  ldc.i4.s 0x14
0x2e151  ldstr    aSetsecuritygro// "SetSecurityGroups, Sql=({0}) PrivUsr=({"...
0x2e156  ldc.i4.4
0x2e157  newarr   [mscorlib]System.Object
0x2e15c  dup
0x2e15d  ldc.i4.0
0x2e15e  ldloc.1
0x2e15f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_SqlAccessGroupId()
0x2e164  box      [mscorlib]System.Guid
0x2e169  stelem.ref
0x2e16a  dup
0x2e16b  ldc.i4.1
0x2e16c  ldloc.1
0x2e16d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeUserGroupId()
0x2e172  box      [mscorlib]System.Guid
0x2e177  stelem.ref
0x2e178  dup
0x2e179  ldc.i4.2
0x2e17a  ldloc.1
0x2e17b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_PrivilegeReportGroupId()
0x2e180  box      [mscorlib]System.Guid
0x2e185  stelem.ref
0x2e186  dup
0x2e187  ldc.i4.3
0x2e188  ldloc.1
0x2e189  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.SecurityGroupsData::get_ReportingGroupId()
0x2e18e  box      [mscorlib]System.Guid
0x2e193  stelem.ref
0x2e194  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e199  ldloc.1
0x2e19a  stloc.2
0x2e19b  leave.s  loc_2E1CD
0x2e19d  stloc.3
0x2e19e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2e1a3  ldc.i4.s 0x14
0x2e1a5  ldstr    aExceptionGetse// "Exception GetSecurityGroups, Id=({0} :{"...
0x2e1aa  ldc.i4.2
0x2e1ab  newarr   [mscorlib]System.Object
0x2e1b0  dup
0x2e1b1  ldc.i4.0
0x2e1b2  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2e1b7  box      [mscorlib]System.Guid
0x2e1bc  stelem.ref
0x2e1bd  dup
0x2e1be  ldc.i4.1
0x2e1bf  ldloc.3
0x2e1c0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2e1c5  stelem.ref
0x2e1c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e1cb  rethrow
0x2e1cd  ldloc.2
0x2e1ce  ret
```
