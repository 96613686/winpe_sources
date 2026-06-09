# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsRelyingPartyIdentifierUrl

- ea: `0x32e0`
- end: `0x32f2`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsRelyingPartyIdentifierUrl`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x32e6`: `ClaimsInfo.ClaimsRelyingPartyIdentifierProperty`

## pseudocode

```c

```

## disassembly

```asm
0x32e0  ldarg.0
0x32e1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x32e6  ldstr    aClaimsinfoClai_5// "ClaimsInfo.ClaimsRelyingPartyIdentifier"...
0x32eb  ldarg.1
0x32ec  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x32f1  ret
```
