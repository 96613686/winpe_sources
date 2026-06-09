# Microsoft.Crm.Tools.Admin.ClaimsConfiguration::InitializeClaimsConfiguration

- ea: `0x2d30`
- end: `0x2d4d`
- name: `Microsoft.Crm.Tools.Admin.ClaimsConfiguration::InitializeClaimsConfiguration`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3340`

## string_xrefs

- `0x2d31`: `claimsInfo`

## pseudocode

```c

```

## disassembly

```asm
0x2d30  ldarg.0
0x2d31  ldstr    aClaimsinfo// "claimsInfo"
0x2d36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2d3b  ldarg.0
0x2d3c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId()
0x2d41  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::.ctor(valuetype [mscorlib]System.Guid)
0x2d46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::TryCreate()
0x2d4b  pop
0x2d4c  ret
```
