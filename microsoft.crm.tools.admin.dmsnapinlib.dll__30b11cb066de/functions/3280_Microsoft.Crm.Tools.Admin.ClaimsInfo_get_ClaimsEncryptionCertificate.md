# Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsEncryptionCertificate

- ea: `0x3280`
- end: `0x3291`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::get_ClaimsEncryptionCertificate`
- size: `17`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2eb0`
- `0x3430`

## string_xrefs

- `0x3281`: `ClaimsInfo.ClaimsEncryptionCertificateProperty`

## pseudocode

```c

```

## disassembly

```asm
0x3280  ldarg.0
0x3281  ldstr    aClaimsinfoClai_1// "ClaimsInfo.ClaimsEncryptionCertificateP"...
0x3286  call     instance object [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::GetPropertyValue(string)
0x328b  castclass [mscorlib]System.String
0x3290  ret
```
