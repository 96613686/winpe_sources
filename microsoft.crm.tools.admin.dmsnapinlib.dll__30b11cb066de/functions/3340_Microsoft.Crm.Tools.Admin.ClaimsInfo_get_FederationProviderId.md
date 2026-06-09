# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId

- ea: `0x3340`
- end: `0x335b`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_FederationProviderId`
- size: `27`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d30`
- `0x2d50`
- `0x2e50`
- `0x2eb0`
- `0x2f80`

## string_xrefs

- `0x3341`: `ClaimsInfo.FederationProviderIdProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3340  ldarg.0
0x3341  ldstr    aClaimsinfoFede// "ClaimsInfo.FederationProviderIdProperty"
0x3346  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::get_DefaultId()
0x334b  box      [mscorlib]System.Guid
0x3350  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::Get(object, object)
0x3355  unbox.any [mscorlib]System.Guid
0x335a  ret
```
