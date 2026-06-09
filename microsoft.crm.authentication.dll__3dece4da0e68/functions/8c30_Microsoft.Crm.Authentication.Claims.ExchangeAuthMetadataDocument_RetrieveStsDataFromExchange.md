# Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::RetrieveStsDataFromExchange

- ea: `0x8c30`
- end: `0x8d1b`
- name: `Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::RetrieveStsDataFromExchange`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd20`

## callees

- `0x8aa0`
- `0x8b40`
- `0x8c30`
- `0x8e50`
- `0x8eb0`
- `0xbdc0`
- `0xbe40`
- `0xbe50`
- `0x10950`
- `0x10970`
- `0x10980`
- `0x109a0`

## string_xrefs

- `0x8ccd`: `No certificates found on Exchange Service Endpoint {0}`
- `0x8cff`: `ExchangeTokenService`

## pseudocode

```c

```

## disassembly

```asm
0x8c30  newobj   instance void Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection::.ctor()
0x8c35  stloc.0
0x8c36  ldarg.0
0x8c37  ldloca.s 1
0x8c39  call     bool Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::TryGetMetadataDocument(class [System]System.Uri authMetadataEndpoint, [out] class Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument& metadataDocument)
0x8c3e  brfalse  loc_8D19
0x8c43  ldloc.1
0x8c44  ldfld    class Microsoft.Crm.Authentication.Claims.JsonKey[] Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::Keys
0x8c49  stloc.2
0x8c4a  ldc.i4.0
0x8c4b  stloc.3
0x8c4c  br.s     loc_8CB9
0x8c4e  ldloc.2
0x8c4f  ldloc.3
0x8c50  ldelem.ref
0x8c51  stloc.s  4
0x8c53  ldloc.s  4
0x8c55  brfalse.s loc_8CB5
0x8c57  ldloc.s  4
0x8c59  callvirt instance class Microsoft.Crm.Authentication.Claims.JsonKeyValue Microsoft.Crm.Authentication.Claims.JsonKey::get_KeyValue()
0x8c5e  brfalse.s loc_8CB5
0x8c60  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x8c65  ldloc.s  4
0x8c67  callvirt instance class Microsoft.Crm.Authentication.Claims.JsonKeyValue Microsoft.Crm.Authentication.Claims.JsonKey::get_KeyValue()
0x8c6c  callvirt instance string Microsoft.Crm.Authentication.Claims.JsonKeyValue::get_Value()
0x8c71  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x8c76  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(unsigned int8[])
0x8c7b  stloc.s  5
0x8c7d  ldloc.s  5
0x8c7f  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x8c84  stloc.s  6
0x8c86  ldloc.0
0x8c87  newobj   instance void Microsoft.Crm.Authentication.Claims.TrustedIssuer::.ctor()
0x8c8c  dup
0x8c8d  ldloc.s  5
0x8c8f  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x8c94  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x8c99  callvirt instance void Microsoft.Crm.Authentication.Claims.TrustedIssuer::set_Name(string value)
0x8c9e  dup
0x8c9f  ldloc.s  6
0x8ca1  callvirt instance unsigned int8[] [System.IdentityModel]System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause::GetX509RawData()
0x8ca6  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x8cab  callvirt instance void Microsoft.Crm.Authentication.Claims.TrustedIssuer::set_Certificate(string value)
0x8cb0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::Add(var<u1>)
0x8cb5  ldloc.3
0x8cb6  ldc.i4.1
0x8cb7  add
0x8cb8  stloc.3
0x8cb9  ldloc.3
0x8cba  ldloc.2
0x8cbb  ldlen
0x8cbc  conv.i4
0x8cbd  blt.s    loc_8C4E
0x8cbf  ldloc.0
0x8cc0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::get_Count()
0x8cc5  ldc.i4.0
0x8cc6  bgt.s    loc_8CEC
0x8cc8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8ccd  ldstr    aNoCertificates// "No certificates found on Exchange Servi"...
0x8cd2  ldc.i4.1
0x8cd3  newarr   [mscorlib]System.Object
0x8cd8  dup
0x8cd9  ldc.i4.0
0x8cda  ldloc.1
0x8cdb  callvirt instance string Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::get_ServiceName()
0x8ce0  stelem.ref
0x8ce1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8ce6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8ceb  throw
0x8cec  newobj   instance void Microsoft.Crm.Authentication.Claims.StsData::.ctor()
0x8cf1  dup
0x8cf2  ldloc.1
0x8cf3  callvirt instance string Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::get_ServiceName()
0x8cf8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8cfd  brfalse.s loc_8D06
0x8cff  ldstr    aExchangetokens// "ExchangeTokenService"
0x8d04  br.s     loc_8D0C
0x8d06  ldloc.1
0x8d07  callvirt instance string Microsoft.Crm.Authentication.Claims.ExchangeAuthMetadataDocument::get_ServiceName()
0x8d0c  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_Name(string value)
0x8d11  dup
0x8d12  ldloc.0
0x8d13  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_TrustedIssuers(class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection value)
0x8d18  ret
0x8d19  ldnull
0x8d1a  ret
```
