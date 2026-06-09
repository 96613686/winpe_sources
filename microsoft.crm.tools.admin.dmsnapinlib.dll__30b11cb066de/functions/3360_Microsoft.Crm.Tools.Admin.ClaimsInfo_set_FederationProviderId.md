# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_FederationProviderId

- ea: `0x3360`
- end: `0x3377`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_FederationProviderId`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d50`

## string_xrefs

- `0x3366`: `ClaimsInfo.FederationProviderIdProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3360  ldarg.0
0x3361  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x3366  ldstr    aClaimsinfoFede// "ClaimsInfo.FederationProviderIdProperty"
0x336b  ldarg.1
0x336c  box      [mscorlib]System.Guid
0x3371  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3376  ret
```
