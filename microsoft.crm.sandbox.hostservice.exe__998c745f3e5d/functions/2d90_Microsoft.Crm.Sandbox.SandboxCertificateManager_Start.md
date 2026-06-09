# Microsoft.Crm.Sandbox.SandboxCertificateManager::Start

- ea: `0x2d90`
- end: `0x2edc`
- name: `Microsoft.Crm.Sandbox.SandboxCertificateManager::Start`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140`

## callees

- `0x2d90`
- `0x2ee0`
- `0x2fe0`

## string_xrefs

- `0x2d97`: `SandboxCertificateManager.Start: HostCertificatePath: {0}`
- `0x2dc2`: `SandboxCertificateManager.Start: Create directory for host certificate`
- `0x2df1`: `SandboxCertificateManager.Start: Create directory for worker certificate`

## pseudocode

```c

```

## disassembly

```asm
0x2d90  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2d95  ldc.i4.s 0x26
0x2d97  ldstr    aSandboxcertifi// "SandboxCertificateManager.Start: HostCe"...
0x2d9c  ldc.i4.1
0x2d9d  newarr   [mscorlib]System.Object
0x2da2  dup
0x2da3  ldc.i4.0
0x2da4  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxHostCertificatePath()
0x2da9  stelem.ref
0x2daa  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2daf  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxHostCertificatePath()
0x2db4  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x2db9  brtrue.s loc_2DDD
0x2dbb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2dc0  ldc.i4.s 0x26
0x2dc2  ldstr    aSandboxcertifi_0// "SandboxCertificateManager.Start: Create"...
0x2dc7  ldc.i4.0
0x2dc8  newarr   [mscorlib]System.Object
0x2dcd  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2dd2  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxHostCertificatePath()
0x2dd7  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x2ddc  pop
0x2ddd  ldnull
0x2dde  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath(string)
0x2de3  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x2de8  brtrue.s loc_2E0D
0x2dea  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2def  ldc.i4.s 0x26
0x2df1  ldstr    aSandboxcertifi_1// "SandboxCertificateManager.Start: Create"...
0x2df6  ldc.i4.0
0x2df7  newarr   [mscorlib]System.Object
0x2dfc  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e01  ldnull
0x2e02  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath(string)
0x2e07  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x2e0c  pop
0x2e0d  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxHostCertificatePath()
0x2e12  ldstr    aSandboxhost// "SandboxHost"
0x2e17  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Sandbox.SandboxCertificateManager::CreateCertificateIfExpiringOrMissing(string certificateFolderPath, string certificateName)
0x2e1c  stloc.0
0x2e1d  ldnull
0x2e1e  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath(string)
0x2e23  ldstr    aSandboxworker// "SandboxWorker"
0x2e28  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Sandbox.SandboxCertificateManager::CreateCertificateIfExpiringOrMissing(string certificateFolderPath, string certificateName)
0x2e2d  stloc.1
0x2e2e  ldloc.0
0x2e2f  brfalse.s loc_2E74
0x2e31  ldstr    a012// "{0}/{1}.{2}"
0x2e36  ldnull
0x2e37  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxWorkerCertificatePath(string)
0x2e3c  ldstr    aSandboxhost// "SandboxHost"
0x2e41  ldstr    aCer// "cer"
0x2e46  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2e4b  stloc.3
0x2e4c  ldloc.3
0x2e4d  ldloc.0
0x2e4e  ldc.i4.1
0x2e4f  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::Export(valuetype [mscorlib]System.Security.Cryptography.X509Certificates.X509ContentType)
0x2e54  call     void [mscorlib]System.IO.File::WriteAllBytes(string, unsigned int8[])
0x2e59  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2e5e  ldc.i4.s 0x26
0x2e60  ldstr    aSandboxcertifi_2// "SandboxCertificateManager.Start: Export"...
0x2e65  ldc.i4.1
0x2e66  newarr   [mscorlib]System.Object
0x2e6b  dup
0x2e6c  ldc.i4.0
0x2e6d  ldloc.3
0x2e6e  stelem.ref
0x2e6f  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e74  ldloc.1
0x2e75  brfalse.s loc_2EBC
0x2e77  ldstr    a012// "{0}/{1}.{2}"
0x2e7c  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::SandboxHostCertificatePath()
0x2e81  ldstr    aSandboxworker// "SandboxWorker"
0x2e86  ldstr    aCer// "cer"
0x2e8b  call     string [mscorlib]System.String::Format(string, object, object, object)
0x2e90  stloc.s  4
0x2e92  ldloc.s  4
0x2e94  ldloc.1
0x2e95  ldc.i4.1
0x2e96  callvirt instance unsigned int8[] [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::Export(valuetype [mscorlib]System.Security.Cryptography.X509Certificates.X509ContentType)
0x2e9b  call     void [mscorlib]System.IO.File::WriteAllBytes(string, unsigned int8[])
0x2ea0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2ea5  ldc.i4.s 0x26
0x2ea7  ldstr    aSandboxcertifi_3// "SandboxCertificateManager.Start: Export"...
0x2eac  ldc.i4.1
0x2ead  newarr   [mscorlib]System.Object
0x2eb2  dup
0x2eb3  ldc.i4.0
0x2eb4  ldloc.s  4
0x2eb6  stelem.ref
0x2eb7  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ebc  ldc.i4.s 0x16
0x2ebe  ldc.i4.0
0x2ebf  call     T0x2B000001
0x2ec4  stloc.2
0x2ec5  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2eca  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2ecf  ldc.i4.1
0x2ed0  bne.un.s loc_2EDB
0x2ed2  ldloc.2
0x2ed3  ldc.i4.0
0x2ed4  ble.s    loc_2EDB
0x2ed6  call     void Microsoft.Crm.Sandbox.SandboxCertificateManager::GrantAccessToCertFolder()
0x2edb  ret
```
