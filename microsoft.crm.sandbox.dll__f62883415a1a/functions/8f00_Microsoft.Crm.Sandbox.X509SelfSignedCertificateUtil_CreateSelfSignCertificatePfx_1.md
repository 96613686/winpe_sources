# Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx_1

- ea: `0x8f00`
- end: `0x91c9`
- name: `Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::CreateSelfSignCertificatePfx_1`
- size: `713`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x8e90`
- `0x8ea0`

## callees

- `0x8f00`
- `0x91d0`
- `0x91f0`
- `0xb190`
- `0xb1d0`
- `0xb1e0`
- `0xb1f0`
- `0xb200`
- `0xb210`
- `0xb220`
- `0xb230`
- `0xb240`
- `0xb250`
- `0xb260`
- `0xb270`
- `0xb280`

## pseudocode

```c

```

## disassembly

```asm
0x8f00  ldarg.0
0x8f01  brtrue.s loc_8F0A
0x8f03  ldstr    asc_10B52// ""
0x8f08  starg.s  0
0x8f0a  ldarg.1
0x8f0b  call     valuetype SystemTime Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::ToSystemTime(valuetype [mscorlib]System.DateTime dateTime)
0x8f10  stloc.1
0x8f11  ldarg.2
0x8f12  call     valuetype SystemTime Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::ToSystemTime(valuetype [mscorlib]System.DateTime dateTime)
0x8f17  stloc.2
0x8f18  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x8f1d  stloc.s  0xB
0x8f1f  ldloca.s 0xB
0x8f21  constrained. [mscorlib]System.Guid
0x8f27  callvirt instance string [mscorlib]System.Object::ToString()
0x8f2c  stloc.3
0x8f2d  ldloca.s 4
0x8f2f  initobj  [mscorlib]System.Runtime.InteropServices.GCHandle
0x8f35  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f3a  stloc.s  5
0x8f3c  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f41  stloc.s  6
0x8f43  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f48  stloc.s  7
0x8f4a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f4f  stloc.s  8
0x8f51  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f56  stloc.s  9
0x8f58  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8f5d  stloc.s  0xA
0x8f5f  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x8f64  ldloca.s 5
0x8f66  ldloc.3
0x8f67  ldnull
0x8f68  ldc.i4.1
0x8f69  ldc.i4.8
0x8f6a  call     bool NativeMethods::CryptAcquireContextW([hasfieldmarshal] native int&, [out] string providerContext, [hasfieldmarshal] string container, [hasfieldmarshal] int32 provider, int32 providerType)
0x8f6f  call     void Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::Check(bool nativeCallSucceeded)
0x8f74  ldloc.s  5
0x8f76  ldc.i4.1
0x8f77  ldc.i4   0x8000001
0x8f7c  ldloca.s 6
0x8f7e  call     bool NativeMethods::CryptGenKey([hasfieldmarshal] native int, int32 providerContext, int32 algorithmId, native int& flags)
0x8f83  call     void Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::Check(bool nativeCallSucceeded)
0x8f88  ldc.i4.0
0x8f89  stloc.s  0xD
0x8f8b  ldarg.0
0x8f8c  ldc.i4.3
0x8f8d  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::Alloc(object, valuetype [mscorlib]System.Runtime.InteropServices.GCHandleType)
0x8f92  stloc.s  4
0x8f94  ldc.i4   0x10001
0x8f99  ldloca.s 4
0x8f9b  call     instance native int [mscorlib]System.Runtime.InteropServices.GCHandle::AddrOfPinnedObject()
0x8fa0  ldc.i4.3
0x8fa1  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8fa6  ldnull
0x8fa7  ldloca.s 0xD
0x8fa9  ldloca.s 0xC
0x8fab  call     bool NativeMethods::CertStrToNameW([hasfieldmarshal] int32, native int certificateEncodingType, int32 x500, native int strType, unsigned int8[] reserved, [out] [hasfieldmarshal] int32& encoded, native int& encodedLength)
0x8fb0  brtrue.s loc_8FBF
0x8fb2  ldloc.s  0xC
0x8fb4  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x8fb9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x8fbe  throw
0x8fbf  ldloc.s  0xD
0x8fc1  newarr   [mscorlib]System.Byte
0x8fc6  stloc.s  0xE
0x8fc8  ldc.i4   0x10001
0x8fcd  ldloca.s 4
0x8fcf  call     instance native int [mscorlib]System.Runtime.InteropServices.GCHandle::AddrOfPinnedObject()
0x8fd4  ldc.i4.3
0x8fd5  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x8fda  ldloc.s  0xE
0x8fdc  ldloca.s 0xD
0x8fde  ldloca.s 0xC
0x8fe0  call     bool NativeMethods::CertStrToNameW([hasfieldmarshal] int32, native int certificateEncodingType, int32 x500, native int strType, unsigned int8[] reserved, [out] [hasfieldmarshal] int32& encoded, native int& encodedLength)
0x8fe5  brtrue.s loc_8FF4
0x8fe7  ldloc.s  0xC
0x8fe9  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringUni(native int)
0x8fee  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x8ff3  throw
0x8ff4  ldloca.s 4
0x8ff6  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0x8ffb  ldloc.s  0xE
0x8ffd  ldc.i4.3
0x8ffe  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::Alloc(object, valuetype [mscorlib]System.Runtime.InteropServices.GCHandleType)
0x9003  stloc.s  4
0x9005  ldloca.s 0xF
0x9007  ldloc.s  0xE
0x9009  ldlen
0x900a  conv.i4
0x900b  ldloca.s 4
0x900d  call     instance native int [mscorlib]System.Runtime.InteropServices.GCHandle::AddrOfPinnedObject()
0x9012  call     instance void CryptoApiBlob::.ctor(int32 dataLength, native int data)
0x9017  ldloca.s 0x10
0x9019  initobj  CryptKeyProviderInformation
0x901f  ldloca.s 0x10
0x9021  ldloc.3
0x9022  stfld    string CryptKeyProviderInformation::ContainerName
0x9027  ldloca.s 0x10
0x9029  ldc.i4.1
0x902a  stfld    int32 CryptKeyProviderInformation::ProviderType
0x902f  ldloca.s 0x10
0x9031  ldc.i4.1
0x9032  stfld    int32 CryptKeyProviderInformation::KeySpec
0x9037  ldloc.s  5
0x9039  ldloca.s 0xF
0x903b  ldc.i4.0
0x903c  ldloca.s 0x10
0x903e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9043  ldloca.s 1
0x9045  ldloca.s 2
0x9047  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x904c  call     native int NativeMethods::CertCreateSelfSignCertificate(native int providerHandle, [in] valuetype CryptoApiBlob& subjectIssuerBlob, int32 flags, [in] valuetype CryptKeyProviderInformation& keyProviderInformation, native int signatureAlgorithm, [in] valuetype SystemTime& startTime, [in] valuetype SystemTime& endTime, native int extensions)
0x9051  stloc.s  7
0x9053  ldloc.s  7
0x9055  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x905a  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x905f  call     void Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::Check(bool nativeCallSucceeded)
0x9064  ldloca.s 4
0x9066  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0x906b  ldstr    aMemory_0// "Memory"
0x9070  ldc.i4.0
0x9071  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9076  ldc.i4   0x2000
0x907b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9080  call     native int NativeMethods::CertOpenStore([hasfieldmarshal] string storeProvider, int32 messageAndCertificateEncodingType, native int cryptProvHandle, int32 flags, native int parameters)
0x9085  stloc.s  8
0x9087  ldloc.s  8
0x9089  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x908e  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x9093  call     void Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::Check(bool nativeCallSucceeded)
0x9098  ldloc.s  8
0x909a  ldloc.s  7
0x909c  ldc.i4.1
0x909d  ldloca.s 9
0x909f  call     bool NativeMethods::CertAddCertificateContextToStore([hasfieldmarshal] native int, native int certificateStoreHandle, int32 certificateContext, native int& addDisposition)
0x90a4  call     void Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::Check(bool nativeCallSucceeded)
0x90a9  ldloc.s  9
0x90ab  ldc.i4.2
0x90ac  ldc.i4.0
0x90ad  ldloca.s 0x10
0x90af  call     bool NativeMethods::CertSetCertificateContextProperty([hasfieldmarshal] native int, int32 certificateContext, int32 propertyId, valuetype CryptKeyProviderInformation& flags)
0x90b4  pop
0x90b5  ldarg.3
0x90b6  brfalse.s loc_90C0
0x90b8  ldarg.3
0x90b9  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::SecureStringToCoTaskMemUnicode(class [mscorlib]System.Security.SecureString)
0x90be  stloc.s  0xA
0x90c0  ldloca.s 0x11
0x90c2  initobj  CryptoApiBlob
0x90c8  ldloc.s  8
0x90ca  ldloca.s 0x11
0x90cc  ldloc.s  0xA
0x90ce  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x90d3  ldc.i4.7
0x90d4  call     bool NativeMethods::PFXExportCertStoreEx([hasfieldmarshal] native int, valuetype CryptoApiBlob& certificateStoreHandle, native int pfxBlob, native int password, int32 reserved)
0x90d9  call     void Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::Check(bool nativeCallSucceeded)
0x90de  ldloc.s  0x11
0x90e0  ldfld    int32 CryptoApiBlob::DataLength
0x90e5  newarr   [mscorlib]System.Byte
0x90ea  stloc.0
0x90eb  ldloc.0
0x90ec  ldc.i4.3
0x90ed  call     valuetype [mscorlib]System.Runtime.InteropServices.GCHandle [mscorlib]System.Runtime.InteropServices.GCHandle::Alloc(object, valuetype [mscorlib]System.Runtime.InteropServices.GCHandleType)
0x90f2  stloc.s  4
0x90f4  ldloca.s 0x11
0x90f6  ldloca.s 4
0x90f8  call     instance native int [mscorlib]System.Runtime.InteropServices.GCHandle::AddrOfPinnedObject()
0x90fd  stfld    native int CryptoApiBlob::Data
0x9102  ldloc.s  8
0x9104  ldloca.s 0x11
0x9106  ldloc.s  0xA
0x9108  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x910d  ldc.i4.7
0x910e  call     bool NativeMethods::PFXExportCertStoreEx([hasfieldmarshal] native int, valuetype CryptoApiBlob& certificateStoreHandle, native int pfxBlob, native int password, int32 reserved)
0x9113  call     void Microsoft.Crm.Sandbox.X509SelfSignedCertificateUtil::Check(bool nativeCallSucceeded)
0x9118  ldloca.s 4
0x911a  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0x911f  leave    loc_91C7
0x9124  ldloc.s  0xA
0x9126  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x912b  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x9130  brfalse.s loc_9139
0x9132  ldloc.s  0xA
0x9134  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ZeroFreeCoTaskMemUnicode(native int)
0x9139  ldloca.s 4
0x913b  call     instance bool [mscorlib]System.Runtime.InteropServices.GCHandle::get_IsAllocated()
0x9140  brfalse.s loc_9149
0x9142  ldloca.s 4
0x9144  call     instance void [mscorlib]System.Runtime.InteropServices.GCHandle::Free()
0x9149  ldloc.s  7
0x914b  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9150  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x9155  brfalse.s loc_915F
0x9157  ldloc.s  7
0x9159  call     bool NativeMethods::CertFreeCertificateContext([hasfieldmarshal] native int)
0x915e  pop
0x915f  ldloc.s  9
0x9161  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9166  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x916b  brfalse.s loc_9175
0x916d  ldloc.s  9
0x916f  call     bool NativeMethods::CertFreeCertificateContext([hasfieldmarshal] native int)
0x9174  pop
0x9175  ldloc.s  8
0x9177  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x917c  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x9181  brfalse.s loc_918C
0x9183  ldloc.s  8
0x9185  ldc.i4.0
0x9186  call     bool NativeMethods::CertCloseStore([hasfieldmarshal] native int, int32 certificateStoreHandle)
0x918b  pop
0x918c  ldloc.s  6
0x918e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x9193  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x9198  brfalse.s loc_91A2
0x919a  ldloc.s  6
0x919c  call     bool NativeMethods::CryptDestroyKey([hasfieldmarshal] native int)
0x91a1  pop
0x91a2  ldloc.s  5
0x91a4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x91a9  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x91ae  brfalse.s loc_91C6
0x91b0  ldloc.s  5
0x91b2  ldc.i4.0
0x91b3  call     bool NativeMethods::CryptReleaseContext([hasfieldmarshal] native int, int32 providerContext)
0x91b8  pop
0x91b9  ldloca.s 5
0x91bb  ldloc.3
0x91bc  ldnull
0x91bd  ldc.i4.1
0x91be  ldc.i4.s 0x10
0x91c0  call     bool NativeMethods::CryptAcquireContextW([hasfieldmarshal] native int&, [out] string providerContext, [hasfieldmarshal] string container, [hasfieldmarshal] int32 provider, int32 providerType)
0x91c5  pop
0x91c6  endfinally
0x91c7  ldloc.0
0x91c8  ret
```
