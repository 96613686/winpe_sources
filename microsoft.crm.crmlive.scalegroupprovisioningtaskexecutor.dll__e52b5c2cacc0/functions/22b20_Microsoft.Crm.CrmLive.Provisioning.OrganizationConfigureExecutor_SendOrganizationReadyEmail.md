# Microsoft.Crm.CrmLive.Provisioning.OrganizationConfigureExecutor::SendOrganizationReadyEmail

- ea: `0x22b20`
- end: `0x22b81`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationConfigureExecutor::SendOrganizationReadyEmail`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x22740`

## callees

- `0x64f0`
- `0x9110`
- `0x91b0`
- `0xa2d0`

## string_xrefs

- `0x22b62`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationConfigureExecutor.cs`
- `0x22b5d`: `SendOrganizationReadyEmail`

## pseudocode

```c

```

## disassembly

```asm
0x22b20  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::.ctor()
0x22b25  dup
0x22b26  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x22b2b  ldarg.0
0x22b2c  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid)
0x22b31  dup
0x22b32  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x22b37  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x22b3c  ldarg.0
0x22b3d  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationName(valuetype [mscorlib]System.Guid)
0x22b42  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_UniqueName(string)
0x22b47  dup
0x22b48  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x22b4d  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x22b52  ldarg.0
0x22b53  ldstr    aType// "Type"
0x22b58  ldc.i4   0x100
0x22b5d  ldstr    aSendorganizati_0// "SendOrganizationReadyEmail"
0x22b62  ldstr    aDDbsShDccm2110_35// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x22b67  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x22b6c  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType
0x22b71  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::set_Type(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType)
0x22b76  call     class Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction Microsoft.Crm.CrmLive.Provisioning.SendOrganizationReadyEmailAction::BuildActionForConfigureTask(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties organizationProperties)
0x22b7b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::Do()
0x22b80  ret
```
