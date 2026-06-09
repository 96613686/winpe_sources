# SandboxCertificateValidator::Validate

- ea: `0x30`
- end: `0x5f`
- name: `SandboxCertificateValidator::Validate`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x30`

## string_xrefs

- `0x53`: `Certificate does not match the configured certificate`

## pseudocode

```c

```

## disassembly

```asm
0x30  ldarg.1
0x31  ldstr    aCertificatetov// "certificateToValidate"
0x36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3b  ldarg.1
0x3c  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x41  ldarg.0
0x42  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 SandboxCertificateValidator::certificate
0x47  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x4c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x51  brtrue.s loc_5E
0x53  ldstr    aCertificateDoe// "Certificate does not match the configur"...
0x58  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmSecurityException::.ctor(string)
0x5d  throw
0x5e  ret
```
