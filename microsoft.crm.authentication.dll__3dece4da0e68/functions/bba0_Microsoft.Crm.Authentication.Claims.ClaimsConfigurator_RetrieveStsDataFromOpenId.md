# Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::RetrieveStsDataFromOpenId

- ea: `0xbba0`
- end: `0xbcc4`
- name: `Microsoft.Crm.Authentication.Claims.ClaimsConfigurator::RetrieveStsDataFromOpenId`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xbd20`

## callees

- `0x6c00`
- `0x6d70`
- `0x6e20`
- `0x6e60`
- `0x6ea0`
- `0x6f60`
- `0x6f90`
- `0x7060`
- `0x7110`
- `0xbba0`
- `0xbdc0`
- `0xbe20`
- `0xbe40`
- `0xbe50`
- `0x109a0`

## string_xrefs

- `0xbc94`: `Windows Azure Active Directory Security Token Service`

## pseudocode

```c

```

## disassembly

```asm
0xbba0  newobj   instance void Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection::.ctor()
0xbba5  stloc.0
0xbba6  call     class Microsoft.Crm.Authentication.OpenId.OpenIdParser Microsoft.Crm.Authentication.OpenId.OpenIdParser::get_Instance()
0xbbab  ldarg.0
0xbbac  callvirt instance class Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetOpenIdProvider(class [System]System.Uri uri)
0xbbb1  stloc.1
0xbbb2  ldloc.1
0xbbb3  callvirt instance string Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse::get_JwksEndpoint()
0xbbb8  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xbbbd  brtrue   loc_BC66
0xbbc2  call     class Microsoft.Crm.Authentication.OpenId.OpenIdParser Microsoft.Crm.Authentication.OpenId.OpenIdParser::get_Instance()
0xbbc7  ldloc.1
0xbbc8  callvirt instance string Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse::get_JwksEndpoint()
0xbbcd  newobj   instance void [System]System.Uri::.ctor(string)
0xbbd2  callvirt instance class Microsoft.Crm.Authentication.OpenId.JsonWebKeys Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetOpenIdProviderKeys(class [System]System.Uri uri)
0xbbd7  stloc.2
0xbbd8  ldloc.2
0xbbd9  brfalse.s loc_BC39
0xbbdb  ldloc.2
0xbbdc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Authentication.OpenId.JsonWebKey> Microsoft.Crm.Authentication.OpenId.JsonWebKeys::get_Keys()
0xbbe1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Authentication.OpenId.JsonWebKey>::GetEnumerator()
0xbbe6  stloc.3
0xbbe7  br.s     loc_BC25
0xbbe9  ldloc.3
0xbbea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.OpenId.JsonWebKey>::get_Current()
0xbbef  callvirt instance class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.OpenId.JsonWebKey::get_TrustedIssuers()
0xbbf4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::GetEnumerator()
0xbbf9  stloc.s  4
0xbbfb  br.s     loc_BC0E
0xbbfd  ldloc.s  4
0xbbff  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::get_Current()
0xbc04  stloc.s  5
0xbc06  ldloc.0
0xbc07  ldloc.s  5
0xbc09  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::Add(var<u1>)
0xbc0e  ldloc.s  4
0xbc10  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbc15  brtrue.s loc_BBFD
0xbc17  leave.s  loc_BC25
0xbc19  ldloc.s  4
0xbc1b  brfalse.s loc_BC24
0xbc1d  ldloc.s  4
0xbc1f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc24  endfinally
0xbc25  ldloc.3
0xbc26  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xbc2b  brtrue.s loc_BBE9
0xbc2d  leave.s  loc_BC39
0xbc2f  ldloc.3
0xbc30  brfalse.s loc_BC38
0xbc32  ldloc.3
0xbc33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xbc38  endfinally
0xbc39  ldloc.0
0xbc3a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::get_Count()
0xbc3f  ldc.i4.0
0xbc40  bgt.s    loc_BC81
0xbc42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc47  ldstr    aNoCertificates_0// "No certificates found on JwksEndpoint {"...
0xbc4c  ldc.i4.1
0xbc4d  newarr   [mscorlib]System.Object
0xbc52  dup
0xbc53  ldc.i4.0
0xbc54  ldloc.1
0xbc55  callvirt instance string Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse::get_JwksEndpoint()
0xbc5a  stelem.ref
0xbc5b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbc60  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xbc65  throw
0xbc66  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc6b  ldstr    aJwksendpointIs// "JwksEndpoint is null or empty"
0xbc70  ldc.i4.0
0xbc71  newarr   [mscorlib]System.Object
0xbc76  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbc7b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0xbc80  throw
0xbc81  newobj   instance void Microsoft.Crm.Authentication.Claims.StsData::.ctor()
0xbc86  dup
0xbc87  ldloc.1
0xbc88  callvirt instance string Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse::get_Issuer()
0xbc8d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xbc92  brfalse.s loc_BC9B
0xbc94  ldstr    aWindowsAzureAc// "Windows Azure Active Directory Security"...
0xbc99  br.s     loc_BCA1
0xbc9b  ldloc.1
0xbc9c  callvirt instance string Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse::get_Issuer()
0xbca1  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_Name(string value)
0xbca6  dup
0xbca7  call     class Microsoft.Crm.Authentication.OpenId.OpenIdParser Microsoft.Crm.Authentication.OpenId.OpenIdParser::get_Instance()
0xbcac  ldloc.1
0xbcad  callvirt instance string Microsoft.Crm.Authentication.OpenId.OpenIdConfigurationResponse::get_TokenEndpoint()
0xbcb2  callvirt instance class [System]System.Uri Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetPassiveUriFromTokenEndpoint(string tokenEndpoint)
0xbcb7  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_PassiveUri(class [System]System.Uri value)
0xbcbc  dup
0xbcbd  ldloc.0
0xbcbe  callvirt instance void Microsoft.Crm.Authentication.Claims.StsData::set_TrustedIssuers(class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection value)
0xbcc3  ret
```
