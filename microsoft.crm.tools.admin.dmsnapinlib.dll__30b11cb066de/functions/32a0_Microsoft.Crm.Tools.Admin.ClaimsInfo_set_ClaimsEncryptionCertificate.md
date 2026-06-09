# Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsEncryptionCertificate

- ea: `0x32a0`
- end: `0x32b2`
- name: `Microsoft.Crm.Tools.Admin.ClaimsInfo::set_ClaimsEncryptionCertificate`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d50`

## string_xrefs

- `0x32a6`: `ClaimsInfo.ClaimsEncryptionCertificateProperty`

## pseudocode

```c

```

## disassembly

```asm
0x32a0  ldarg.0
0x32a1  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x32a6  ldstr    aClaimsinfoClai_1// "ClaimsInfo.ClaimsEncryptionCertificateP"...
0x32ab  ldarg.1
0x32ac  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x32b1  ret
```
