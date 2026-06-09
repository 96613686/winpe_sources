# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsLiveIdFederationMetadataUrl

- ea: `0x3200`
- end: `0x3211`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsLiveIdFederationMetadataUrl`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x3201`: `ClaimsInfo.ClaimsLiveIdFederationMetadataUrlProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3200  ldarg.0
0x3201  ldstr    aClaimsinfoClai_3// "ClaimsInfo.ClaimsLiveIdFederationMetada"...
0x3206  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x320b  castclass [mscorlib]System.String
0x3210  ret
```
