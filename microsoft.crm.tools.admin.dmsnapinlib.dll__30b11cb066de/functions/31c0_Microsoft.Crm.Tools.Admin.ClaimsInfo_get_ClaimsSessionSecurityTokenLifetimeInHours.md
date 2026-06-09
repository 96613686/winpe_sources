# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsSessionSecurityTokenLifetimeInHours

- ea: `0x31c0`
- end: `0x31d1`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsSessionSecurityTokenLifetimeInHours`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2eb0`

## string_xrefs

- `0x31c1`: `ClaimsInfo.ClaimsSessionSecurityTokenLifetimeInHoursProperty`

## pseudocode

```c

```

## disassembly

```asm
0x31c0  ldarg.0
0x31c1  ldstr    aClaimsinfoClai_2// "ClaimsInfo.ClaimsSessionSecurityTokenLi"...
0x31c6  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x31cb  unbox.any [mscorlib]System.Int32
0x31d0  ret
```
