# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::BrandTemplate

- ea: `0x1d6a0`
- end: `0x1d6de`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::BrandTemplate`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1fc70`
- `0x20140`
- `0x20670`

## string_xrefs

- `0x1d6b1`: `Finished UpdateOrganizationReferences`
- `0x1d6c2`: `Finished UpdateSystemUserReferences`
- `0x1d6d3`: `Finished UpdateQueueName`

## pseudocode

```c

```

## disassembly

```asm
0x1d6a0  ldarg.1
0x1d6a1  ldstr    aOrganizationpr// "organizationProperties"
0x1d6a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d6ab  ldarg.1
0x1d6ac  call     void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateOrganizationReferences(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties properties)
0x1d6b1  ldstr    aFinishedUpdate_1// "Finished UpdateOrganizationReferences"
0x1d6b6  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1d6bb  ldarg.0
0x1d6bc  ldarg.1
0x1d6bd  call     instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateSystemUserReferences(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties properties)
0x1d6c2  ldstr    aFinishedUpdate_2// "Finished UpdateSystemUserReferences"
0x1d6c7  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1d6cc  ldarg.0
0x1d6cd  ldarg.1
0x1d6ce  call     instance void Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateQueueName(class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties properties)
0x1d6d3  ldstr    aFinishedUpdate_3// "Finished UpdateQueueName"
0x1d6d8  call     void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.ProvisioningTaskLogger::LogLine(string)
0x1d6dd  ret
```
