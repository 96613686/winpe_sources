# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::UpdateSigningCertificates

- ea: `0xb9e0`
- end: `0xbb92`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::UpdateSigningCertificates`
- size: `434`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x7670`
- `0xb9e0`
- `0xbd20`
- `0xbe30`
- `0x10940`
- `0x10960`
- `0x14b80`

## pseudocode

```c

```

## disassembly

```asm
0xb9e0  newobj   instance void <>c__DisplayClass13_0::.ctor()
0xb9e5  stloc.0
0xb9e6  ldarg.0
0xb9e7  ldstr    aFederationprov// "federationProviderId"
0xb9ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xb9f1  ldarg.0
0xb9f2  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::.ctor(valuetype [mscorlib]System.Guid)
0xb9f7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmFederationProviderService::GetFederationProviderData()
0xb9fc  stloc.1
0xb9fd  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::.ctor()
0xba02  stloc.2
0xba03  ldloc.1
0xba04  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_MetadataUrl()
0xba09  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xba0e  brfalse.s loc_BA34
0xba10  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xba15  ldstr    aNoFederationMe// "No federation metadata URL was found in"...
0xba1a  ldc.i4.1
0xba1b  newarr   [mscorlib]System.Object
0xba20  dup
0xba21  ldc.i4.0
0xba22  ldarg.0
0xba23  box      [mscorlib]System.Guid
0xba28  stelem.ref
0xba29  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xba2e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xba33  throw
0xba34  ldloc.0
0xba35  ldarg.0
0xba36  ldloc.1
0xba37  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.FederationProviderData::get_MetadataUrl()
0xba3c  newobj   instance void [System]System.Uri::.ctor(string)
0xba41  call     class Microsoft.Crm.Authentication.Claims.StsData Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::GetStsData(valuetype [mscorlib]System.Guid federationProviderId, class [System]System.Uri stsUrl)
0xba46  callvirt instance class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.Claims.StsData::get_TrustedIssuers()
0xba4b  stfld    class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection <>c__DisplayClass13_0::metadataCertificates
0xba50  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter::.ctor()
0xba55  dup
0xba56  ldarga.s 0
0xba58  constrained. [mscorlib]System.Guid
0xba5e  callvirt instance string [mscorlib]System.Object::ToString()
0xba63  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter::set_ParentId(string)
0xba68  dup
0xba69  ldstr    aTrustedissuer// "TrustedIssuer"
0xba6e  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter::set_CertificateType(string)
0xba73  stloc.3
0xba74  ldloc.0
0xba75  ldloc.2
0xba76  ldloc.3
0xba77  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::RetrieveMultiple(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter)
0xba7c  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData[] <>c__DisplayClass13_0::configDBCertificates
0xba81  ldloc.0
0xba82  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData[] <>c__DisplayClass13_0::configDBCertificates
0xba87  ldloc.0
0xba88  ldftn    instance bool <>c__DisplayClass13_0::<UpdateSigningCertificates>b__0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData c)
0xba8e  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData, bool>::.ctor(object, native int)
0xba93  call     T0x2B00001C
0xba98  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData>::GetEnumerator()
0xba9d  stloc.s  4
0xba9f  br.s     loc_BAED
0xbaa1  ldloc.s  4
0xbaa3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData>::get_Current()
0xbaa8  stloc.s  5
0xbaaa  ldloc.2
0xbaab  ldloc.s  5
0xbaad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::get_Id()
0xbab2  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::Delete(valuetype [mscorlib]System.Guid)
0xbab7  ldc.i4.2
0xbab8  ldc.i4   0x80006202
0xbabd  conv.u8
0xbabe  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbac3  ldstr    aType0Certname1// "Type: {0}, CertName: {1}"
0xbac8  ldc.i4.2
0xbac9  newarr   [mscorlib]System.Object
0xbace  dup
0xbacf  ldc.i4.0
0xbad0  ldloc.s  5
0xbad2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xbad7  stelem.ref
0xbad8  dup
0xbad9  ldc.i4.1
0xbada  ldloc.s  5
0xbadc  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::get_Name()
0xbae1  stelem.ref
0xbae2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbae7  ldnull
0xbae8  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0xbaed  ldloc.s  4
0xbaef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbaf4  brtrue.s loc_BAA1
0xbaf6  leave.s  loc_BB04
0xbaf8  ldloc.s  4
0xbafa  brfalse.s loc_BB03
0xbafc  ldloc.s  4
0xbafe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbb03  endfinally
0xbb04  ldloc.0
0xbb05  ldfld    class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection <>c__DisplayClass13_0::metadataCertificates
0xbb0a  ldloc.0
0xbb0b  ldftn    instance bool <>c__DisplayClass13_0::<UpdateSigningCertificates>b__1(class Microsoft.Crm.Authentication.Claims.TrustedIssuer m)
0xbb11  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Authentication.Claims.TrustedIssuer, bool>::.ctor(object, native int)
0xbb16  call     T0x2B00001D
0xbb1b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::GetEnumerator()
0xbb20  stloc.s  6
0xbb22  br.s     loc_BB7A
0xbb24  ldloc.s  6
0xbb26  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::get_Current()
0xbb2b  stloc.s  7
0xbb2d  ldloc.2
0xbb2e  ldloc.s  7
0xbb30  callvirt instance string Microsoft.Crm.Authentication.Claims.TrustedIssuer::get_Name()
0xbb35  ldarg.0
0xbb36  ldloc.s  7
0xbb38  callvirt instance string Microsoft.Crm.Authentication.Claims.TrustedIssuer::get_Certificate()
0xbb3d  ldc.i4.1
0xbb3e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::CreateTrustedIssuerCertificate(string, valuetype [mscorlib]System.Guid, string, bool)
0xbb43  pop
0xbb44  ldc.i4.2
0xbb45  ldc.i4   0x80006203
0xbb4a  conv.u8
0xbb4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb50  ldstr    aType0Certname1// "Type: {0}, CertName: {1}"
0xbb55  ldc.i4.2
0xbb56  newarr   [mscorlib]System.Object
0xbb5b  dup
0xbb5c  ldc.i4.0
0xbb5d  ldloc.s  7
0xbb5f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xbb64  stelem.ref
0xbb65  dup
0xbb66  ldc.i4.1
0xbb67  ldloc.s  7
0xbb69  callvirt instance string Microsoft.Crm.Authentication.Claims.TrustedIssuer::get_Name()
0xbb6e  stelem.ref
0xbb6f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbb74  ldnull
0xbb75  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0xbb7a  ldloc.s  6
0xbb7c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbb81  brtrue.s loc_BB24
0xbb83  leave.s  loc_BB91
0xbb85  ldloc.s  6
0xbb87  brfalse.s loc_BB90
0xbb89  ldloc.s  6
0xbb8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbb90  endfinally
0xbb91  ret
```
