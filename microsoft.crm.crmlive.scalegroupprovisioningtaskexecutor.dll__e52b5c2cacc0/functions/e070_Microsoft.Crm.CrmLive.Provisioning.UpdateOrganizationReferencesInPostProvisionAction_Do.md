# Microsoft.Crm.CrmLive.Provisioning.UpdateOrganizationReferencesInPostProvisionAction::Do

- ea: `0xe070`
- end: `0xe11a`
- name: `Microsoft.Crm.CrmLive.Provisioning.UpdateOrganizationReferencesInPostProvisionAction::Do`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x64b0`
- `0x6520`
- `0x6550`
- `0x9190`
- `0x91b0`
- `0xe070`
- `0xe150`
- `0x1c230`
- `0x1c2f0`
- `0x1c3b0`

## string_xrefs

- `0xe098`: `Finished UpdateDefaultPublisher`
- `0xe0f9`: `Finished UpdateOrganizationUrlsInTemplates`

## pseudocode

```c

```

## disassembly

```asm
0xe070  ldarg.0
0xe071  ldarg.0
0xe072  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xe077  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xe07c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xe081  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0xe086  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0xe08b  stloc.0
0xe08c  ldloc.0
0xe08d  ldarg.0
0xe08e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xe093  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateDefaultPublisher(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties properties)
0xe098  ldstr    aFinishedUpdate// "Finished UpdateDefaultPublisher"
0xe09d  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0xe0a2  ldarg.0
0xe0a3  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xe0a8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xe0ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xe0b2  call     bool Microsoft.Crm.CrmLive.Provisioning.UpdateOrganizationReferencesInPostProvisionAction::IsOsdpOrganization(valuetype [mscorlib]System.Guid orgId)
0xe0b7  brfalse.s loc_E103
0xe0b9  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xe0be  ldstr    aRootdomain// "RootDomain"
0xe0c3  ldc.i4.0
0xe0c4  callvirt T0x2B000011
0xe0c9  stloc.1
0xe0ca  ldarg.0
0xe0cb  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xe0d0  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_DomainName()
0xe0d5  ldstr    asc_3CF8E// "."
0xe0da  ldloc.1
0xe0db  call     string [mscorlib]System.String::Concat(string, string, string)
0xe0e0  stloc.2
0xe0e1  ldloc.0
0xe0e2  ldarg.0
0xe0e3  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xe0e8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xe0ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xe0f2  ldloc.2
0xe0f3  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::UpdateOrganizationUrlsInTemplates(valuetype [mscorlib]System.Guid organizationId, string newFullDomain)
0xe0f8  pop
0xe0f9  ldstr    aFinishedUpdate_0// "Finished UpdateOrganizationUrlsInTempla"...
0xe0fe  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0xe103  ldarg.0
0xe104  ldarg.0
0xe105  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0xe10a  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0xe10f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0xe114  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDoMethodExit(valuetype [mscorlib]System.Guid organizationId)
0xe119  ret
```
