# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsOrgIdFederationMetadataUrl

- ea: `0x3240`
- end: `0x3251`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsOrgIdFederationMetadataUrl`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x3241`: `ClaimsInfo.ClaimsOrgIdFederationMetadataUrlProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3240  ldarg.0
0x3241  ldstr    aClaimsinfoClai_4// "ClaimsInfo.ClaimsOrgIdFederationMetadat"...
0x3246  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x324b  castclass [mscorlib]System.String
0x3250  ret
```
