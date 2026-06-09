# Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::Deprovision

- ea: `0x5ef0`
- end: `0x5f87`
- name: `Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::Deprovision`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5ad0`
- `0x5ef0`
- `0x5fa0`
- `0x64b0`
- `0x65e0`
- `0x6610`
- `0x91b0`

## string_xrefs

- `0x5f0b`: `PlatformSharedServiceURL`

## pseudocode

```c

```

## disassembly

```asm
0x5ef0  ldarg.0
0x5ef1  ldarg.0
0x5ef2  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5ef7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5efc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5f01  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDeprovisionMethodEntry(valuetype [mscorlib]System.Guid organizationId)
0x5f06  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x5f0b  ldstr    aPlatformshared// "PlatformSharedServiceURL"
0x5f10  ldc.i4.0
0x5f11  callvirt T0x2B000011
0x5f16  newobj   instance void [System]System.Uri::.ctor(string)
0x5f1b  ldc.i4   0x80
0x5f20  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::.ctor(class [System]System.Uri, valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.CrmLiveConnections)
0x5f25  stloc.0
0x5f26  ldloc.0
0x5f27  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.ClientProvision.ProvisionWsdl [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_ProvisionService()
0x5f2c  ldarg.0
0x5f2d  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5f32  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5f37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5f3c  ldarg.0
0x5f3d  call     instance bool Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::get_DeleteForSandboxInstanceReprovision()
0x5f42  callvirt instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.ClientProvision.ProvisionWsdl::DeleteAllOrganizationRelatedRecords(valuetype [mscorlib]System.Guid, bool)
0x5f47  leave.s  loc_5F53
0x5f49  ldloc.0
0x5f4a  brfalse.s loc_5F52
0x5f4c  ldloc.0
0x5f4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f52  endfinally
0x5f53  ldarg.0
0x5f54  call     instance bool Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::get_DeleteForSandboxInstanceReprovision()
0x5f59  brtrue.s loc_5F70
0x5f5b  ldarg.0
0x5f5c  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5f61  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5f66  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5f6b  call     void Microsoft.Crm.CrmLive.Provisioning.CreateOrganizationInConfigDBAction::QueueForDeletion(valuetype [mscorlib]System.Guid organizationId)
0x5f70  ldarg.0
0x5f71  ldarg.0
0x5f72  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x5f77  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x5f7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x5f81  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::TraceDeprovisionMethodExit(valuetype [mscorlib]System.Guid organizationId)
0x5f86  ret
```
