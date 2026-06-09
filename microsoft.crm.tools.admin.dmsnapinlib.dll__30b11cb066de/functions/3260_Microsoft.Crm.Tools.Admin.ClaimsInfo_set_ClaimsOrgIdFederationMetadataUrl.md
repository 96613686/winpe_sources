# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsOrgIdFederationMetadataUrl

- ea: `0x3260`
- end: `0x3272`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsOrgIdFederationMetadataUrl`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x3266`: `ClaimsInfo.ClaimsOrgIdFederationMetadataUrlProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3260  ldarg.0
0x3261  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x3266  ldstr    aClaimsinfoClai_4// "ClaimsInfo.ClaimsOrgIdFederationMetadat"...
0x326b  ldarg.1
0x326c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3271  ret
```
