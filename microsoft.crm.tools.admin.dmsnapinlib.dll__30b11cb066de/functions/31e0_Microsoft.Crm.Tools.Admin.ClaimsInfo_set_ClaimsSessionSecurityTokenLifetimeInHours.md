# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsSessionSecurityTokenLifetimeInHours

- ea: `0x31e0`
- end: `0x31f7`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsSessionSecurityTokenLifetimeInHours`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d50`

## string_xrefs

- `0x31e6`: `ClaimsInfo.ClaimsSessionSecurityTokenLifetimeInHoursProperty`

## pseudocode

```c

```

## disassembly

```asm
0x31e0  ldarg.0
0x31e1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x31e6  ldstr    aClaimsinfoClai_2// "ClaimsInfo.ClaimsSessionSecurityTokenLi"...
0x31eb  ldarg.1
0x31ec  box      [mscorlib]System.Int32
0x31f1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x31f6  ret
```
