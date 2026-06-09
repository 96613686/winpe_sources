# Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::UpdateOrgSettingsLight

- ea: `0x4cc0`
- end: `0x4ccc`
- name: `Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::UpdateOrgSettingsLight`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x4ca0`

## pseudocode

```c

```

## disassembly

```asm
0x4cc0  ldarg.0
0x4cc1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0x4cc6  call     void Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::RemoveOrgFromOrgSettingsLightCache(valuetype [mscorlib]System.Guid organizationId)
0x4ccb  ret
```
