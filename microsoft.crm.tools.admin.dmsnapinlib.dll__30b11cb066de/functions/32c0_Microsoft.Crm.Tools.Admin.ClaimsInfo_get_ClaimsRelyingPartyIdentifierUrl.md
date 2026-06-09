# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsRelyingPartyIdentifierUrl

- ea: `0x32c0`
- end: `0x32d1`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsRelyingPartyIdentifierUrl`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x32c1`: `ClaimsInfo.ClaimsRelyingPartyIdentifierProperty`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldarg.0
0x32c1  ldstr    aClaimsinfoClai_5// "ClaimsInfo.ClaimsRelyingPartyIdentifier"...
0x32c6  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x32cb  castclass [System]System.Uri
0x32d0  ret
```
