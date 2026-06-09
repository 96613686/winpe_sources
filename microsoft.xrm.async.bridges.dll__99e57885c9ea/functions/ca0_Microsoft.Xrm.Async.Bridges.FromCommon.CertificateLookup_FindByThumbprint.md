# Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::FindByThumbprint

- ea: `0xca0`
- end: `0xce3`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::FindByThumbprint`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xca0`

## pseudocode

```c

```

## disassembly

```asm
0xca0  ldarg.0
0xca1  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Store Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::store
0xca6  ldc.i4.0
0xca7  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509Store::Open(valuetype [System]System.Security.Cryptography.X509Certificates.OpenFlags)
0xcac  ldarg.0
0xcad  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Store Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::store
0xcb2  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection [System]System.Security.Cryptography.X509Certificates.X509Store::get_Certificates()
0xcb7  ldc.i4.0
0xcb8  ldarg.1
0xcb9  ldc.i4.1
0xcba  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::Find(valuetype [System]System.Security.Cryptography.X509Certificates.X509FindType, object, bool)
0xcbf  stloc.0
0xcc0  ldloc.0
0xcc1  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xcc6  brfalse.s loc_CD1
0xcc8  ldloc.0
0xcc9  ldc.i4.0
0xcca  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System]System.Security.Cryptography.X509Certificates.X509Certificate2Collection::get_Item(int32)
0xccf  br.s     loc_CD2
0xcd1  ldnull
0xcd2  stloc.1
0xcd3  leave.s  loc_CE1
0xcd5  ldarg.0
0xcd6  ldfld    class [System]System.Security.Cryptography.X509Certificates.X509Store Microsoft.Xrm.Async.Bridges.FromCommon.CertificateLookup::store
0xcdb  callvirt instance void [System]System.Security.Cryptography.X509Certificates.X509Store::Close()
0xce0  endfinally
0xce1  ldloc.1
0xce2  ret
```
