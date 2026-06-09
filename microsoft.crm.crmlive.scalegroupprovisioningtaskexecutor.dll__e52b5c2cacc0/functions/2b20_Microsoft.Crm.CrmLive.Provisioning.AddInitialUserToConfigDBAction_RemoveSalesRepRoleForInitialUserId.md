# Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RemoveSalesRepRoleForInitialUserId

- ea: `0x2b20`
- end: `0x2b7e`
- name: `Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::RemoveSalesRepRoleForInitialUserId`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2580`

## callees

- `0x26e0`
- `0x2b20`
- `0x64b0`
- `0x91b0`
- `0x9480`
- `0x1c1b0`
- `0x1c3b0`
- `0x24210`

## string_xrefs

- `0x2b47`: `RemoveSalesRepRoleForInitialUserId triggered`

## pseudocode

```c

```

## disassembly

```asm
0x2b20  ldarg.0
0x2b21  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2b26  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OriginalCreateInfo()
0x2b2b  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserScenario()
0x2b30  stloc.0
0x2b31  ldloc.0
0x2b32  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b37  brtrue.s loc_2B7D
0x2b39  ldloc.0
0x2b3a  ldstr    aDeveloperediti// "DeveloperEdition"
0x2b3f  callvirt instance bool [mscorlib]System.String::Equals(string)
0x2b44  brfalse.s loc_2B7D
0x2b46  ldarg.0
0x2b47  ldstr    aRemovesalesrep// "RemoveSalesRepRoleForInitialUserId trig"...
0x2b4c  call     instance void Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::Log(string text)
0x2b51  ldarg.0
0x2b52  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.AddInitialUserToConfigDBAction::_crmUserId
0x2b57  stloc.1
0x2b58  call     class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::NewService()
0x2b5d  ldarg.0
0x2b5e  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x2b63  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OrganizationData()
0x2b68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x2b6d  ldstr    aA4be89ff7c354d// "{A4BE89FF-7C35-4D69-9900-999C3F603E6F}"
0x2b72  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2b77  ldloc.1
0x2b78  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::RemoveUserRole(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid roleTemplateId, valuetype [mscorlib]System.Guid crmUserId)
0x2b7d  ret
```
