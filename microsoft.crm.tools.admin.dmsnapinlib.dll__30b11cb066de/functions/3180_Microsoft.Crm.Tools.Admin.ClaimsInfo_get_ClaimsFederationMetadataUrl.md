# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsFederationMetadataUrl

- ea: `0x3180`
- end: `0x3191`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsFederationMetadataUrl`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2eb0`
- `0x34c0`

## string_xrefs

- `0x3181`: `ClaimsInfo.ClaimsFederationMetadataUrlProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3180  ldarg.0
0x3181  ldstr    aClaimsinfoClai_0// "ClaimsInfo.ClaimsFederationMetadataUrlP"...
0x3186  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x318b  castclass [mscorlib]System.String
0x3190  ret
```
