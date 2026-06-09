# Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateOrUpdateCertificate

- ea: `0x18860`
- end: `0x18a98`
- name: `Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateOrUpdateCertificate`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18840`

## callees

- `0x18860`
- `0x18aa0`
- `0x18de0`
- `0x19100`
- `0x19470`
- `0x19580`
- `0x195a0`
- `0x195c0`
- `0x195e0`
- `0x19600`
- `0x19670`
- `0x19690`
- `0x196b0`
- `0x196d0`
- `0x196f0`
- `0x19710`
- `0x19730`
- `0x19750`
- `0x19790`
- `0x19850`
- `0x19880`

## string_xrefs

- `0x1896e`: `Skip certificate update. Type={0}`
- `0x189a8`: `Updating Certificate, Type={0}, IssuerName={1}, storeLocation={2}, storeName={3}, findType={4}, findValue={5}`
- `0x189eb`: `Creating Certificate, Type={0}, IssuerName={1}, storeLocation={2}, storeName={3}, findType={4}, findValue={5}`
- `0x18a26`: `Creating Certificate, Type={0}, IssuerName={1}, storeLocation={2}, storeName={3}, findType={4}, findValue={5}`
- `0x18a65`: `Exception for Certificate, Type={0}, IssuerName={1}, storeLocation={2}, storeName={3}, findType={4}, findValue={5}, Exception:{6}`

## pseudocode

```c

```

## disassembly

```asm
0x18860  ldarg.2
0x18861  ldstr    aIssuerName// "Issuer name"
0x18866  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1886b  ldarg.3
0x1886c  ldstr    aCertificateSto// "Certificate store location"
0x18871  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x18876  ldarg.s  4
0x18878  ldstr    aCertificateSto_0// "Certificate store name"
0x1887d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x18882  ldarg.s  5
0x18884  ldstr    aCertificateFin// "Certificate find type"
0x18889  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1888e  ldarg.s  6
0x18890  ldstr    aCertificateFin_0// "Certificate find value"
0x18895  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1889a  newobj   instance void Microsoft.Crm.Admin.AdminService.CertificateData::.ctor()
0x1889f  stloc.0
0x188a0  ldloc.0
0x188a1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x188a6  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateData::set_Id(valuetype [mscorlib]System.Guid value)
0x188ab  ldloc.0
0x188ac  ldarg.2
0x188ad  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateData::set_Name(string value)
0x188b2  ldloc.0
0x188b3  ldarg.1
0x188b4  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateData::set_CertificateType(string value)
0x188b9  ldloc.0
0x188ba  ldarg.3
0x188bb  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateData::set_StoreLocation(string value)
0x188c0  ldloc.0
0x188c1  ldarg.s  4
0x188c3  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateData::set_StoreName(string value)
0x188c8  ldloc.0
0x188c9  ldarg.s  5
0x188cb  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateData::set_StoreFindType(string value)
0x188d0  ldarg.s  6
0x188d2  call     void Microsoft.Crm.Admin.AdminService.CrmCertificateService::ValidateCertificateData(string certificateData)
0x188d7  ldloc.0
0x188d8  ldarg.s  6
0x188da  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateData::set_Certificate(string value)
0x188df  newobj   instance void Microsoft.Crm.Admin.AdminService.CertificateFilter::.ctor()
0x188e4  stloc.1
0x188e5  ldloc.1
0x188e6  ldc.i4.1
0x188e7  newarr   [mscorlib]System.String
0x188ec  dup
0x188ed  ldc.i4.0
0x188ee  ldarg.1
0x188ef  stelem.ref
0x188f0  callvirt instance void Microsoft.Crm.Admin.AdminService.CertificateFilter::set_CertificateTypes(string[] value)
0x188f5  ldarg.0
0x188f6  ldloc.1
0x188f7  call     instance class Microsoft.Crm.Admin.AdminService.CertificateData[] Microsoft.Crm.Admin.AdminService.CrmCertificateService::RetrieveMultiple(class Microsoft.Crm.Admin.AdminService.CertificateFilter filter)
0x188fc  stloc.2
0x188fd  ldloc.2
0x188fe  ldlen
0x188ff  brfalse  loc_18A1F
0x18904  ldloc.2
0x18905  ldc.i4.0
0x18906  ldelem.ref
0x18907  stloc.3
0x18908  ldloc.3
0x18909  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_StoreLocation()
0x1890e  ldloc.0
0x1890f  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_StoreLocation()
0x18914  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18919  brfalse.s loc_18987
0x1891b  ldloc.3
0x1891c  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_StoreName()
0x18921  ldloc.0
0x18922  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_StoreName()
0x18927  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1892c  brfalse.s loc_18987
0x1892e  ldloc.3
0x1892f  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_StoreFindType()
0x18934  ldloc.0
0x18935  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_StoreFindType()
0x1893a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1893f  brfalse.s loc_18987
0x18941  ldloc.3
0x18942  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_Certificate()
0x18947  ldloc.0
0x18948  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_Certificate()
0x1894d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18952  brfalse.s loc_18987
0x18954  ldloc.3
0x18955  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_Name()
0x1895a  ldloc.0
0x1895b  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_Name()
0x18960  call     bool [mscorlib]System.String::op_Equality(string, string)
0x18965  brfalse.s loc_18987
0x18967  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1896c  ldc.i4.s 0x14
0x1896e  ldstr    aSkipCertificat// "Skip certificate update. Type={0}"
0x18973  ldc.i4.1
0x18974  newarr   [mscorlib]System.Object
0x18979  dup
0x1897a  ldc.i4.0
0x1897b  ldarg.1
0x1897c  stelem.ref
0x1897d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18982  br       loc_18A58
0x18987  ldarg.1
0x18988  ldstr    aAlternativeiss// "AlternativeIssuer"
0x1898d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x18992  brfalse.s loc_189E4
0x18994  ldarg.1
0x18995  ldstr    aAlternativeenc// "AlternativeEncrypting"
0x1899a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1899f  brfalse.s loc_189E4
0x189a1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x189a6  ldc.i4.s 0x14
0x189a8  ldstr    aUpdatingCertif// "Updating Certificate, Type={0}, IssuerN"...
0x189ad  ldc.i4.6
0x189ae  newarr   [mscorlib]System.Object
0x189b3  dup
0x189b4  ldc.i4.0
0x189b5  ldarg.1
0x189b6  stelem.ref
0x189b7  dup
0x189b8  ldc.i4.1
0x189b9  ldarg.2
0x189ba  stelem.ref
0x189bb  dup
0x189bc  ldc.i4.2
0x189bd  ldarg.3
0x189be  stelem.ref
0x189bf  dup
0x189c0  ldc.i4.3
0x189c1  ldarg.s  4
0x189c3  stelem.ref
0x189c4  dup
0x189c5  ldc.i4.4
0x189c6  ldarg.s  5
0x189c8  stelem.ref
0x189c9  dup
0x189ca  ldc.i4.5
0x189cb  ldarg.s  6
0x189cd  stelem.ref
0x189ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x189d3  ldarg.0
0x189d4  ldloc.2
0x189d5  ldc.i4.0
0x189d6  ldelem.ref
0x189d7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CertificateData::get_Id()
0x189dc  ldloc.0
0x189dd  call     instance void Microsoft.Crm.Admin.AdminService.CrmCertificateService::Update(valuetype [mscorlib]System.Guid certificateId, class Microsoft.Crm.Admin.AdminService.CertificateData certificateData)
0x189e2  br.s     loc_18A58
0x189e4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x189e9  ldc.i4.s 0x14
0x189eb  ldstr    aCreatingCertif_0// "Creating Certificate, Type={0}, IssuerN"...
0x189f0  ldc.i4.6
0x189f1  newarr   [mscorlib]System.Object
0x189f6  dup
0x189f7  ldc.i4.0
0x189f8  ldarg.1
0x189f9  stelem.ref
0x189fa  dup
0x189fb  ldc.i4.1
0x189fc  ldarg.2
0x189fd  stelem.ref
0x189fe  dup
0x189ff  ldc.i4.2
0x18a00  ldarg.3
0x18a01  stelem.ref
0x18a02  dup
0x18a03  ldc.i4.3
0x18a04  ldarg.s  4
0x18a06  stelem.ref
0x18a07  dup
0x18a08  ldc.i4.4
0x18a09  ldarg.s  5
0x18a0b  stelem.ref
0x18a0c  dup
0x18a0d  ldc.i4.5
0x18a0e  ldarg.s  6
0x18a10  stelem.ref
0x18a11  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18a16  ldloc.0
0x18a17  call     class Microsoft.Crm.Admin.AdminService.CertificateData Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateInternal(class Microsoft.Crm.Admin.AdminService.CertificateData certificateData)
0x18a1c  pop
0x18a1d  br.s     loc_18A58
0x18a1f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18a24  ldc.i4.s 0x14
0x18a26  ldstr    aCreatingCertif_0// "Creating Certificate, Type={0}, IssuerN"...
0x18a2b  ldc.i4.6
0x18a2c  newarr   [mscorlib]System.Object
0x18a31  dup
0x18a32  ldc.i4.0
0x18a33  ldarg.1
0x18a34  stelem.ref
0x18a35  dup
0x18a36  ldc.i4.1
0x18a37  ldarg.2
0x18a38  stelem.ref
0x18a39  dup
0x18a3a  ldc.i4.2
0x18a3b  ldarg.3
0x18a3c  stelem.ref
0x18a3d  dup
0x18a3e  ldc.i4.3
0x18a3f  ldarg.s  4
0x18a41  stelem.ref
0x18a42  dup
0x18a43  ldc.i4.4
0x18a44  ldarg.s  5
0x18a46  stelem.ref
0x18a47  dup
0x18a48  ldc.i4.5
0x18a49  ldarg.s  6
0x18a4b  stelem.ref
0x18a4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18a51  ldloc.0
0x18a52  call     class Microsoft.Crm.Admin.AdminService.CertificateData Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateInternal(class Microsoft.Crm.Admin.AdminService.CertificateData certificateData)
0x18a57  pop
0x18a58  leave.s  loc_18A97
0x18a5a  stloc.s  4
0x18a5c  ldloc.s  4
0x18a5e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x18a63  ldc.i4.s 0x14
0x18a65  ldstr    aExceptionForCe// "Exception for Certificate, Type={0}, Is"...
0x18a6a  ldc.i4.7
0x18a6b  newarr   [mscorlib]System.Object
0x18a70  dup
0x18a71  ldc.i4.0
0x18a72  ldarg.1
0x18a73  stelem.ref
0x18a74  dup
0x18a75  ldc.i4.1
0x18a76  ldarg.2
0x18a77  stelem.ref
0x18a78  dup
0x18a79  ldc.i4.2
0x18a7a  ldarg.3
0x18a7b  stelem.ref
0x18a7c  dup
0x18a7d  ldc.i4.3
0x18a7e  ldarg.s  4
0x18a80  stelem.ref
0x18a81  dup
0x18a82  ldc.i4.4
0x18a83  ldarg.s  5
0x18a85  stelem.ref
0x18a86  dup
0x18a87  ldc.i4.5
0x18a88  ldarg.s  6
0x18a8a  stelem.ref
0x18a8b  dup
0x18a8c  ldc.i4.6
0x18a8d  ldloc.s  4
0x18a8f  stelem.ref
0x18a90  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18a95  rethrow
0x18a97  ret
```
