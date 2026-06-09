# Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::.ctor_0

- ea: `0xc80`
- end: `0xc94`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::.ctor_0`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xc70`

## pseudocode

```c

```

## disassembly

```asm
0xc80  ldarg.0
0xc81  call     instance void [mscorlib]System.Object::.ctor()
0xc86  ldarg.0
0xc87  ldarg.1
0xc88  ldarg.2
0xc89  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Store::.ctor(valuetype [System]System.Security.Cryptography.X509Certificates.StoreName, valuetype [System]System.Security.Cryptography.X509Certificates.StoreLocation)
0xc8e  stfld    class [System]System.Security.Cryptography.X509Certificates.X509Store Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::store
0xc93  ret
```
