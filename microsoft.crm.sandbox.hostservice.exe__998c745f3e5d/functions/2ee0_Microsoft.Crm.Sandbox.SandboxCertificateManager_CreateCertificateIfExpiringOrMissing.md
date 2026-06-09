# Microsoft.Crm.Sandbox.SandboxCertificateManager::CreateCertificateIfExpiringOrMissing

- ea: `0x2ee0`
- end: `0x2fdf`
- name: `Microsoft.Crm.Sandbox.SandboxCertificateManager::CreateCertificateIfExpiringOrMissing`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2d90`

## callees

- `0x2ee0`

## string_xrefs

- `0x2f1c`: `SandboxCertificateManager.CreateCertificateIfExpiringOrMissing: Unable to read existing certificate at {0}. Regenerating new certificate file`
- `0x2f39`: `SandboxCertificateManager.CreateCertificateIfExpiringOrMissing: Unable to find existing certificate at {0}. Regenerating new certificate file`
- `0x2f6b`: `SandboxCertificateManager.CreateCertificateIfExpiringOrMissing: Certificate at {0} is missing or expiring within 6 months. Regenerating new certificate file`
- `0x2fbe`: `SandboxCertificateManager.CreateCertificateIfExpiringOrMissing: Certificate with thumbprint {0} was created at {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x2ee0  ldstr    a012// "{0}/{1}.{2}"
0x2ee5  ldarg.0
0x2ee6  ldarg.1
0x2ee7  ldstr    aPfx// "pfx"
0x2eec  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2ef1  stloc.0
0x2ef2  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x2ef7  stloc.1
0x2ef8  ldloc.0
0x2ef9  call     bool [mscorlib]System.IO.File::Exists(string)
0x2efe  brfalse.s loc_2F32
0x2f00  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor()
0x2f05  dup
0x2f06  ldloc.0
0x2f07  callvirt instance void [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::Import(string)
0x2f0c  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotAfter()
0x2f11  stloc.1
0x2f12  leave.s  loc_2F4D
0x2f14  pop
0x2f15  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2f1a  ldc.i4.s 0x26
0x2f1c  ldstr    aSandboxcertifi_4// "SandboxCertificateManager.CreateCertifi"...
0x2f21  ldc.i4.1
0x2f22  newarr   [mscorlib]System.Object
0x2f27  dup
0x2f28  ldc.i4.0
0x2f29  ldloc.0
0x2f2a  stelem.ref
0x2f2b  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f30  leave.s  loc_2F4D
0x2f32  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2f37  ldc.i4.s 0x26
0x2f39  ldstr    aSandboxcertifi_5// "SandboxCertificateManager.CreateCertifi"...
0x2f3e  ldc.i4.1
0x2f3f  newarr   [mscorlib]System.Object
0x2f44  dup
0x2f45  ldc.i4.0
0x2f46  ldloc.0
0x2f47  stelem.ref
0x2f48  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f4d  ldloc.1
0x2f4e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2f53  stloc.2
0x2f54  ldloca.s 2
0x2f56  ldc.i4.s 0xFA
0x2f58  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMonths(int32)
0x2f5d  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2f62  brfalse.s loc_2FDD
0x2f64  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2f69  ldc.i4.s 0x26
0x2f6b  ldstr    aSandboxcertifi_6// "SandboxCertificateManager.CreateCertifi"...
0x2f70  ldc.i4.1
0x2f71  newarr   [mscorlib]System.Object
0x2f76  dup
0x2f77  ldc.i4.0
0x2f78  ldloc.0
0x2f79  stelem.ref
0x2f7a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f7f  ldstr    aCn0// "CN={0}"
0x2f84  ldarg.1
0x2f85  call     string [mscorlib]System.String::Format(string, object)
0x2f8a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2f8f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x2f94  stloc.2
0x2f95  ldloca.s 2
0x2f97  ldc.i4.2
0x2f98  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddYears(int32)
0x2f9d  call     unsigned int8[] [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx(string, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2fa2  ldnull
0x2fa3  ldc.i4.4
0x2fa4  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(unsigned int8[], string, valuetype [mscorlib]System.Security.Cryptography.X509Certificates.X509KeyStorageFlags)
0x2fa9  stloc.3
0x2faa  ldloc.0
0x2fab  ldloc.3
0x2fac  ldc.i4.3
0x2fad  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::Export(valuetype [mscorlib]System.Security.Cryptography.X509Certificates.X509ContentType)
0x2fb2  call     void [mscorlib]System.IO.File::WriteAllBytes(string, unsigned int8[])
0x2fb7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2fbc  ldc.i4.s 0x26
0x2fbe  ldstr    aSandboxcertifi_7// "SandboxCertificateManager.CreateCertifi"...
0x2fc3  ldc.i4.2
0x2fc4  newarr   [mscorlib]System.Object
0x2fc9  dup
0x2fca  ldc.i4.0
0x2fcb  ldloc.3
0x2fcc  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x2fd1  stelem.ref
0x2fd2  dup
0x2fd3  ldc.i4.1
0x2fd4  ldloc.0
0x2fd5  stelem.ref
0x2fd6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2fdb  ldloc.3
0x2fdc  ret
0x2fdd  ldnull
0x2fde  ret
```
