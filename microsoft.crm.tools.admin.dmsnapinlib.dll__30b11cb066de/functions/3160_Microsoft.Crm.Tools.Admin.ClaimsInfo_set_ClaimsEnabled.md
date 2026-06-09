# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsEnabled

- ea: `0x3160`
- end: `0x3177`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsEnabled`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d50`

## string_xrefs

- `0x3166`: `ClaimsInfo.ClaimsEnabledProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3160  ldarg.0
0x3161  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x3166  ldstr    aClaimsinfoClai// "ClaimsInfo.ClaimsEnabledProperty"
0x316b  ldarg.1
0x316c  box      [mscorlib]System.Boolean
0x3171  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3176  ret
```
