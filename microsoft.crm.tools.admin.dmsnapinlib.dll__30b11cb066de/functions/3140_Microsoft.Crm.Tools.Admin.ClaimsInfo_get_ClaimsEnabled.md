# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsEnabled

- ea: `0x3140`
- end: `0x3151`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsEnabled`
- size: `17`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2eb0`
- `0x33d0`
- `0x12320`

## string_xrefs

- `0x3141`: `ClaimsInfo.ClaimsEnabledProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3140  ldarg.0
0x3141  ldstr    aClaimsinfoClai// "ClaimsInfo.ClaimsEnabledProperty"
0x3146  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x314b  unbox.any [mscorlib]System.Boolean
0x3150  ret
```
