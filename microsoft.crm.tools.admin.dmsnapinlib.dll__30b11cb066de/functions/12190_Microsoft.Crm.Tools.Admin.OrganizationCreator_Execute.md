# Microsoft.Crm.Tools.Admin.OrganizationCreator::Execute

- ea: `0x12190`
- end: `0x121ce`
- name: `Microsoft.Crm.Tools.Admin.OrganizationCreator::Execute`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x7640`
- `0x82c0`
- `0x8630`
- `0x9870`
- `0x9d30`
- `0xa3d0`
- `0x12190`
- `0x17a20`
- `0x17ae0`

## string_xrefs

- `0x121a8`: `The deployment does not support multiple tenancy. All other orgs will be deleted and the newly created org will be set as default.`

## pseudocode

```c

```

## disassembly

```asm
0x12190  ldarg.0
0x12191  call     instance void Microsoft.Crm.Tools.Admin.OrganizationOperation::Execute()
0x12196  call     class Microsoft.Crm.Tools.Admin.LicenseController Microsoft.Crm.Tools.Admin.LicenseController::get_Instance()
0x1219b  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.StoredLicenseData Microsoft.Crm.Tools.Admin.LicenseController::ReadLicense()
0x121a0  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.LicenseData::get_IsMultipleTenancy()
0x121a5  brtrue.s loc_121CD
0x121a7  ldc.i4.2
0x121a8  ldstr    aTheDeploymentD// "The deployment does not support multipl"...
0x121ad  ldc.i4.0
0x121ae  newarr   [mscorlib]System.Object
0x121b3  call     void Microsoft.Crm.Tools.Admin.OrganizationOperation::LogEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.LogLevel logLevel, string message, object[] args)
0x121b8  call     class Microsoft.Crm.Tools.Admin.OrganizationController Microsoft.Crm.Tools.Admin.OrganizationController::get_Instance()
0x121bd  ldarg.0
0x121be  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationInfo()
0x121c3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x121c8  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationController::DeleteAllOtherOrganizations(valuetype [mscorlib]System.Guid organizationId)
0x121cd  ret
```
