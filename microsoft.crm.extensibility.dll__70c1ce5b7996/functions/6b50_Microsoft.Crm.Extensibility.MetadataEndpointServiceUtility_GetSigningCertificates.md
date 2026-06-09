# Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::GetSigningCertificates

- ea: `0x6b50`
- end: `0x6c69`
- name: `Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::GetSigningCertificates`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6aa0`

## callees

- `0x6b50`

## string_xrefs

- `0x6b8f`: `S2STokenIssuer`
- `0x6bee`: `S2STokenIssuer`
- `0x6b97`: `AlternativeS2STokenIssuer`
- `0x6bfd`: `More than one S2STokenIssuer certificate present in config database.`
- `0x6c0f`: `More than one AlternativeS2STokenIssuer certificate present in config database.`
- `0x6c35`: `No S2STokenIssuer certificate present in config database.`

## pseudocode

```c

```

## disassembly

```asm
0x6b50  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6b55  stloc.1
0x6b56  ldloca.s 1
0x6b58  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x6b5d  ldsflda  int64 Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::_lastCertificateCacheUpdated
0x6b62  call     int64 [mscorlib]System.Threading.Interlocked::Read(int64&)
0x6b67  sub
0x6b68  ldc.i4   0x23C34600
0x6b6d  conv.i8
0x6b6e  cgt
0x6b70  stloc.0
0x6b71  ldsfld   class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificateStore[] Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::_cachedCertificateStore
0x6b76  ldnull
0x6b77  ceq
0x6b79  ldloc.0
0x6b7a  or
0x6b7b  brfalse  loc_6C63
0x6b80  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter::.ctor()
0x6b85  stloc.2
0x6b86  ldloc.2
0x6b87  ldc.i4.2
0x6b88  newarr   [mscorlib]System.String
0x6b8d  dup
0x6b8e  ldc.i4.0
0x6b8f  ldstr    aS2stokenissuer// "S2STokenIssuer"
0x6b94  stelem.ref
0x6b95  dup
0x6b96  ldc.i4.1
0x6b97  ldstr    aAlternatives2s// "AlternativeS2STokenIssuer"
0x6b9c  stelem.ref
0x6b9d  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter::set_CertificateTypes(string[])
0x6ba2  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::.ctor()
0x6ba7  ldloc.2
0x6ba8  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::RetrieveMultiple(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter)
0x6bad  ldc.i4.0
0x6bae  stloc.3
0x6baf  dup
0x6bb0  ldlen
0x6bb1  conv.i4
0x6bb2  newarr   [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificateStore
0x6bb7  stloc.s  4
0x6bb9  ldc.i4.0
0x6bba  stloc.s  5
0x6bbc  stloc.s  6
0x6bbe  ldc.i4.0
0x6bbf  stloc.s  7
0x6bc1  br.s     loc_6C2C
0x6bc3  ldloc.s  6
0x6bc5  ldloc.s  7
0x6bc7  ldelem.ref
0x6bc8  stloc.s  8
0x6bca  ldstr    aX509certificat// "x509certificate"
0x6bcf  ldloc.s  8
0x6bd1  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::get_Certificate()
0x6bd6  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificate::.ctor(string, string)
0x6bdb  ldstr    aSigning// "Signing"
0x6be0  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificateStore::.ctor(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificate, string)
0x6be5  stloc.s  9
0x6be7  ldloc.s  8
0x6be9  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::get_CertificateType()
0x6bee  ldstr    aS2stokenissuer// "S2STokenIssuer"
0x6bf3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6bf8  brfalse.s loc_6C0A
0x6bfa  ldloc.3
0x6bfb  brfalse.s loc_6C08
0x6bfd  ldstr    aMoreThanOneS2s// "More than one S2STokenIssuer certificat"...
0x6c02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6c07  throw
0x6c08  ldc.i4.1
0x6c09  stloc.3
0x6c0a  ldloc.s  5
0x6c0c  ldc.i4.1
0x6c0d  ble.s    loc_6C1A
0x6c0f  ldstr    aMoreThanOneAlt// "More than one AlternativeS2STokenIssuer"...
0x6c14  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6c19  throw
0x6c1a  ldloc.s  4
0x6c1c  ldloc.s  5
0x6c1e  dup
0x6c1f  ldc.i4.1
0x6c20  add
0x6c21  stloc.s  5
0x6c23  ldloc.s  9
0x6c25  stelem.ref
0x6c26  ldloc.s  7
0x6c28  ldc.i4.1
0x6c29  add
0x6c2a  stloc.s  7
0x6c2c  ldloc.s  7
0x6c2e  ldloc.s  6
0x6c30  ldlen
0x6c31  conv.i4
0x6c32  blt.s    loc_6BC3
0x6c34  ldloc.3
0x6c35  ldstr    aNoS2stokenissu// "No S2STokenIssuer certificate present i"...
0x6c3a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x6c3f  ldloc.s  4
0x6c41  call     T0x2B000034
0x6c46  stsfld   class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificateStore[] Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::_cachedCertificateStore
0x6c4b  ldsflda  int64 Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::_lastCertificateCacheUpdated
0x6c50  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6c55  stloc.1
0x6c56  ldloca.s 1
0x6c58  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x6c5d  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x6c62  pop
0x6c63  ldsfld   class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.MetadataCertificateStore[] Microsoft.Crm.Extensibility.MetadataEndpointServiceUtility::_cachedCertificateStore
0x6c68  ret
```
