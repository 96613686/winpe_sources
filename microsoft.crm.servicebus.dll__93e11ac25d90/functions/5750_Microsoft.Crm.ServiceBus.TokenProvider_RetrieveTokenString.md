# Microsoft.Crm.ServiceBus.TokenProvider::RetrieveTokenString

- ea: `0x5750`
- end: `0x5968`
- name: `Microsoft.Crm.ServiceBus.TokenProvider::RetrieveTokenString`
- size: `536`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x3ac0`
- `0x42e0`
- `0x5b90`

## callees

- `0x13f0`
- `0x1410`
- `0x25a0`
- `0x5570`
- `0x5750`
- `0x5970`
- `0x5a60`
- `0x5c50`

## string_xrefs

- `0x57b0`: `StoreName`
- `0x57e8`: `Service integration issuer information not found.`
- `0x58d2`: `Service integration issuer certificate should have private key.`

## pseudocode

```c

```

## disassembly

```asm
0x5750  ldarg.0
0x5751  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5756  ldstr    aEndpointinfo_0// "EndpointInfo"
0x575b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5760  ldarg.0
0x5761  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5766  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SolutionName()
0x576b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5770  brfalse.s loc_5785
0x5772  ldarg.0
0x5773  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x5778  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Path()
0x577d  newobj   instance void [System]System.Uri::.ctor(string)
0x5782  stloc.0
0x5783  br.s     loc_5798
0x5785  ldarg.0
0x5786  ldarg.0
0x5787  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x578c  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SolutionName()
0x5791  ldarg.1
0x5792  call     instance class [System]System.Uri Microsoft.Crm.ServiceBus.TokenProvider::AccessControlPath(string solutionName, bool isServiceBusScope)
0x5797  stloc.0
0x5798  ldc.i4.5
0x5799  newarr   [mscorlib]System.String
0x579e  dup
0x579f  ldc.i4.0
0x57a0  ldstr    aName_0// "Name"
0x57a5  stelem.ref
0x57a6  dup
0x57a7  ldc.i4.1
0x57a8  ldstr    aCertificatedat// "CertificateData"
0x57ad  stelem.ref
0x57ae  dup
0x57af  ldc.i4.2
0x57b0  ldstr    aStorename// "StoreName"
0x57b5  stelem.ref
0x57b6  dup
0x57b7  ldc.i4.3
0x57b8  ldstr    aStorelocation// "StoreLocation"
0x57bd  stelem.ref
0x57be  dup
0x57bf  ldc.i4.4
0x57c0  ldstr    aStorefindtype// "StoreFindType"
0x57c5  stelem.ref
0x57c6  stloc.1
0x57c7  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.AuthManagementInfoProvider::get_Instance()
0x57cc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x57d1  ldstr    aAppfabricissue// "AppFabricIssuer"
0x57d6  ldloc.1
0x57d7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider::GetCertificates(valuetype [mscorlib]System.Guid, string, string[])
0x57dc  stloc.2
0x57dd  ldloc.2
0x57de  brfalse.s loc_57E8
0x57e0  ldloc.2
0x57e1  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x57e6  brtrue.s loc_57F8
0x57e8  ldstr    aServiceIntegra_0// "Service integration issuer information "...
0x57ed  ldc.i4   0x80044176
0x57f2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x57f7  throw
0x57f8  ldnull
0x57f9  stloc.3
0x57fa  ldloc.2
0x57fb  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x5800  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x5805  stloc.s  9
0x5807  br.s     loc_5818
0x5809  ldloca.s 9
0x580b  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x5810  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag)
0x5815  stloc.3
0x5816  leave.s  loc_5831
0x5818  ldloca.s 9
0x581a  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x581f  brtrue.s loc_5809
0x5821  leave.s  loc_5831
0x5823  ldloca.s 9
0x5825  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x582b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5830  endfinally
0x5831  ldloc.3
0x5832  ldstr    aCertificatedat_0// "certificateData"
0x5837  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x583c  ldloc.3
0x583d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::get_Name()
0x5842  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2NameIdentifier::.ctor(string)
0x5847  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2NameIdentifier)
0x584c  stloc.s  4
0x584e  ldloc.s  4
0x5850  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions::.ctor()
0x5855  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::set_Conditions(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions)
0x585a  ldloc.s  4
0x585c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Conditions()
0x5861  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2AudienceRestriction> [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions::get_AudienceRestrictions()
0x5866  ldloc.0
0x5867  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2AudienceRestriction::.ctor(class [System]System.Uri)
0x586c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.IdentityModel]System.IdentityModel.Tokens.Saml2AudienceRestriction>::Add(var<u1>)
0x5871  ldloc.s  4
0x5873  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Conditions()
0x5878  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x587d  stloc.s  0xA
0x587f  ldloca.s 0xA
0x5881  ldc.r8   1.0
0x588a  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x588f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x5894  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions::set_NotOnOrAfter(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x5899  ldloc.s  4
0x589b  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::get_Conditions()
0x58a0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x58a5  stloc.s  0xA
0x58a7  ldloca.s 0xA
0x58a9  ldc.r8   -1.0
0x58b2  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddHours(float64)
0x58b7  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x58bc  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Conditions::set_NotBefore(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0x58c1  ldloc.3
0x58c2  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveCertificate(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData certificateData)
0x58c7  stloc.s  5
0x58c9  ldloc.s  5
0x58cb  callvirt instance bool [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_HasPrivateKey()
0x58d0  brtrue.s loc_58E2
0x58d2  ldstr    aServiceIntegra_1// "Service integration issuer certificate "...
0x58d7  ldc.i4   0x80044177
0x58dc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x58e1  throw
0x58e2  ldloc.s  4
0x58e4  ldloc.s  5
0x58e6  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x58eb  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::set_SigningCredentials(class [System.IdentityModel]System.IdentityModel.Tokens.SigningCredentials)
0x58f0  ldarg.0
0x58f1  ldloc.s  4
0x58f3  call     instance void Microsoft.Crm.ServiceBus.TokenProvider::AddSystemClaims(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion saml2Assertion)
0x58f8  ldarg.0
0x58f9  ldloc.s  4
0x58fb  call     instance void Microsoft.Crm.ServiceBus.TokenProvider::AddCustomClaims(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion saml2Assertion)
0x5900  ldloc.s  4
0x5902  ldsfld   class [System]System.Uri Microsoft.Crm.ServiceBus.ConfirmationMethods::Bearer
0x5907  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2SubjectConfirmation::.ctor(class [System]System.Uri)
0x590c  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Subject::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2SubjectConfirmation)
0x5911  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion::set_Subject(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Subject)
0x5916  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2SecurityTokenHandler::.ctor()
0x591b  stloc.s  6
0x591d  ldloc.s  4
0x591f  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.Saml2SecurityToken::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.Saml2Assertion)
0x5924  stloc.s  7
0x5926  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x592b  stloc.s  8
0x592d  ldloc.s  8
0x592f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5934  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x5939  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter)
0x593e  stloc.s  0xB
0x5940  ldloc.s  6
0x5942  ldloc.s  0xB
0x5944  ldloc.s  7
0x5946  callvirt instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenHandler::WriteToken(class [System.Xml]System.Xml.XmlWriter, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x594b  ldloc.s  0xB
0x594d  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x5952  leave.s  loc_5960
0x5954  ldloc.s  0xB
0x5956  brfalse.s loc_595F
0x5958  ldloc.s  0xB
0x595a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x595f  endfinally
0x5960  ldloc.s  8
0x5962  callvirt instance string [mscorlib]System.Object::ToString()
0x5967  ret
```
