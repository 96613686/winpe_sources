# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsFederationMetadataUrl

- ea: `0x31a0`
- end: `0x31b2`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsFederationMetadataUrl`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d50`

## string_xrefs

- `0x31a6`: `ClaimsInfo.ClaimsFederationMetadataUrlProperty`

## pseudocode

```c

```

## disassembly

```asm
0x31a0  ldarg.0
0x31a1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x31a6  ldstr    aClaimsinfoClai_0// "ClaimsInfo.ClaimsFederationMetadataUrlP"...
0x31ab  ldarg.1
0x31ac  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x31b1  ret
```
