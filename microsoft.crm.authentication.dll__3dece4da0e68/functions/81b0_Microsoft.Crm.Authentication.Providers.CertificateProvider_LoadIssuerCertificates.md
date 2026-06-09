# Microsoft.Crm.Authentication.Providers.CertificateProvider::LoadIssuerCertificates

- ea: `0x81b0`
- end: `0x82e1`
- name: `Microsoft.Crm.Authentication.Providers.CertificateProvider::LoadIssuerCertificates`
- size: `305`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x8100`
- `0x8170`

## callees

- `0x7670`
- `0x81b0`
- `0x82f0`
- `0x8440`
- `0x8460`
- `0x8470`

## string_xrefs

- `0x81bb`: `CertificateProvider.LoadIssuerCertificates - Signing certificates for token resolution:\n`

## pseudocode

```c

```

## disassembly

```asm
0x81b0  ldarg.0
0x81b1  ldfld    class Microsoft.Crm.Authentication.Providers.CertificateCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::_trustedIssuerCertificates
0x81b6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::Clear()
0x81bb  ldstr    aCertificatepro// "CertificateProvider.LoadIssuerCertifica"...
0x81c0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x81c5  stloc.0
0x81c6  ldloc.0
0x81c7  ldstr    aHost0// "Host: {0}\n"
0x81cc  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x81d1  call     string [Microsoft.Crm.Core]Microsoft.Crm.AuthenticationContextExtensions::CurrentHost(class [System.Web]System.Web.HttpContext)
0x81d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x81db  pop
0x81dc  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::RetrieveAllSigningCertificates()
0x81e1  stloc.1
0x81e2  ldloc.1
0x81e3  brfalse  loc_82B5
0x81e8  ldloc.1
0x81e9  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x81ee  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x81f3  stloc.2
0x81f4  br       loc_8285
0x81f9  ldloca.s 2
0x81fb  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x8200  stloc.3
0x8201  ldloc.3
0x8202  ldstr    aCertificatedat// "CertificateData"
0x8207  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x820c  callvirt instance string [mscorlib]System.Object::ToString()
0x8211  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x8216  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(unsigned int8[])
0x821b  stloc.s  4
0x821d  ldarg.0
0x821e  ldfld    class Microsoft.Crm.Authentication.Providers.CertificateCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::_trustedIssuerCertificates
0x8223  newobj   instance void Microsoft.Crm.Authentication.Providers.CertificateInformation::.ctor()
0x8228  dup
0x8229  ldloc.s  4
0x822b  callvirt instance void Microsoft.Crm.Authentication.Providers.CertificateInformation::set_Certificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 value)
0x8230  dup
0x8231  ldloc.3
0x8232  callvirt instance void Microsoft.Crm.Authentication.Providers.CertificateInformation::set_Properties(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag value)
0x8237  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::Add(var<u1>)
0x823c  ldloc.0
0x823d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8242  ldstr    aSubject0Thumbp// "Subject: {0}, Thumbprint: {1}, Valid On"...
0x8247  ldc.i4.4
0x8248  newarr   [mscorlib]System.Object
0x824d  dup
0x824e  ldc.i4.0
0x824f  ldloc.s  4
0x8251  callvirt instance string [mscorlib]System.Security.Cryptography.X509Certificates.X509Certificate::get_Subject()
0x8256  stelem.ref
0x8257  dup
0x8258  ldc.i4.1
0x8259  ldloc.s  4
0x825b  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x8260  stelem.ref
0x8261  dup
0x8262  ldc.i4.2
0x8263  ldloc.s  4
0x8265  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotBefore()
0x826a  box      [mscorlib]System.DateTime
0x826f  stelem.ref
0x8270  dup
0x8271  ldc.i4.3
0x8272  ldloc.s  4
0x8274  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotAfter()
0x8279  box      [mscorlib]System.DateTime
0x827e  stelem.ref
0x827f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x8284  pop
0x8285  ldloca.s 2
0x8287  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x828c  brtrue   loc_81F9
0x8291  leave.s  loc_82A1
0x8293  ldloca.s 2
0x8295  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x829b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x82a0  endfinally
0x82a1  ldc.i4.8
0x82a2  ldc.i4   0x4000433A
0x82a7  conv.i8
0x82a8  ldloc.0
0x82a9  callvirt instance string [mscorlib]System.Object::ToString()
0x82ae  ldnull
0x82af  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0x82b4  ret
0x82b5  ldloc.0
0x82b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x82bb  ldstr    aCertificatepro_0// "CertificateProvider.LoadIssuerCertifica"...
0x82c0  ldc.i4.0
0x82c1  newarr   [mscorlib]System.Object
0x82c6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x82cb  pop
0x82cc  ldc.i4.s 0x10
0x82ce  ldc.i4   0x4000433A
0x82d3  conv.i8
0x82d4  ldloc.0
0x82d5  callvirt instance string [mscorlib]System.Object::ToString()
0x82da  ldnull
0x82db  call     void Microsoft.Crm.Authentication.Telemetry.AuthenticationTelemetryUtilities::WriteEventLog(valuetype [System]System.Diagnostics.EventLogEntryType errorLevel, int64 eventId, string context, [opt] class [mscorlib]System.Exception exception)
0x82e0  ret
```
