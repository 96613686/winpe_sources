# Microsoft.Crm.Tools.Admin.ClaimsConfiguration::IsClaimsEnabled

- ea: `0x2f80`
- end: `0x2fa1`
- name: `Microsoft.Crm.Tools.Admin.ClaimsConfiguration::IsClaimsEnabled`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3340`

## string_xrefs

- `0x2f81`: `claimsInfo`

## pseudocode

```c

```

## disassembly

```asm
0x2f80  ldarg.0
0x2f81  ldstr    aClaimsinfo// "claimsInfo"
0x2f86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2f8b  ldarg.0
0x2f8c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2f91  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::.ctor(valuetype [mscorlib]System.Guid)
0x2f96  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::GetFederationProviderData()
0x2f9b  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_Enabled()
0x2fa0  ret
```
