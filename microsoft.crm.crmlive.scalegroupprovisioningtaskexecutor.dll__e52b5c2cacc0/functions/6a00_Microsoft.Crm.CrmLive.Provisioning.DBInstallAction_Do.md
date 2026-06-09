# Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::Do

- ea: `0x6a00`
- end: `0x6a6d`
- name: `Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::Do`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x6a00`
- `0x6ab0`
- `0x91b0`
- `0x9410`

## string_xrefs

- `0x6a34`: `_DBInstallAction`

## pseudocode

```c

```

## disassembly

```asm
0x6a00  ldarg.0
0x6a01  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6a06  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_IsBackedByXdb()
0x6a0b  brfalse.s loc_6A0E
0x6a0d  ret
0x6a0e  ldarg.0
0x6a0f  ldarg.0
0x6a10  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6a15  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6a1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6a1f  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x6a24  ldarg.0
0x6a25  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6a2a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6a2f  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_SqlServerName()
0x6a34  ldstr    aDbinstallactio// "_DBInstallAction"
0x6a39  call     string [mscorlib]System.String::Concat(string, string)
0x6a3e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigDBLock::.ctor(string)
0x6a43  stloc.0
0x6a44  ldarg.0
0x6a45  call     instance void Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::CleanupExistingDatabase()
0x6a4a  leave.s  loc_6A56
0x6a4c  ldloc.0
0x6a4d  brfalse.s loc_6A55
0x6a4f  ldloc.0
0x6a50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a55  endfinally
0x6a56  ldarg.0
0x6a57  ldarg.0
0x6a58  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x6a5d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x6a62  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x6a67  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x6a6c  ret
```
