# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsLiveIdFederationMetadataUrl

- ea: `0x3220`
- end: `0x3232`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsLiveIdFederationMetadataUrl`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x3226`: `ClaimsInfo.ClaimsLiveIdFederationMetadataUrlProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3220  ldarg.0
0x3221  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x3226  ldstr    aClaimsinfoClai_3// "ClaimsInfo.ClaimsLiveIdFederationMetada"...
0x322b  ldarg.1
0x322c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3231  ret
```
