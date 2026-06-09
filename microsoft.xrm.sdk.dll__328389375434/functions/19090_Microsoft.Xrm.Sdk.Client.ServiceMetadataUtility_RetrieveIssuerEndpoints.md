# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveIssuerEndpoints

- ea: `0x19090`
- end: `0x19268`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveIssuerEndpoints`
- size: `472`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x178e0`
- `0x19390`

## callees

- `0x17820`
- `0x17840`
- `0x17860`
- `0x17880`
- `0x178a0`
- `0x178b0`
- `0x17940`
- `0x19090`
- `0x19460`
- `0x194b0`
- `0x199d0`

## pseudocode

```c

```

## disassembly

```asm
0x19090  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::.ctor()
0x19095  stloc.0
0x19096  ldarg.0
0x19097  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x1909c  callvirt instance string [System]System.Uri::get_Scheme()
0x190a1  call     class [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::CreateMetadataClient(string scheme)
0x190a6  ldarg.0
0x190a7  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x190ac  ldc.i4.1
0x190ad  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.MetadataSet [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClient::GetMetadata(class [System]System.Uri, valuetype [System.ServiceModel]System.ServiceModel.Description.MetadataExchangeClientMode)
0x190b2  stloc.1
0x190b3  ldloc.1
0x190b4  brfalse  loc_19266
0x190b9  ldloc.1
0x190ba  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.WsdlImporter::.ctor(class [System.ServiceModel]System.ServiceModel.Description.MetadataSet)
0x190bf  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpointCollection [System.ServiceModel]System.ServiceModel.Description.MetadataImporter::ImportAllEndpoints()
0x190c4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::GetEnumerator()
0x190c9  stloc.2
0x190ca  br       loc_1924F
0x190cf  ldloc.2
0x190d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint>::get_Current()
0x190d5  stloc.3
0x190d6  ldloc.3
0x190d7  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x190dc  isinst   [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x190e1  brtrue   loc_1924F
0x190e6  ldc.i4.0
0x190e7  stloc.s  4
0x190e9  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_Default()
0x190ee  stloc.s  5
0x190f0  ldloc.3
0x190f1  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x190f6  isinst   [System.ServiceModel]System.ServiceModel.WS2007HttpBinding
0x190fb  stloc.s  6
0x190fd  ldloc.s  6
0x190ff  brfalse  loc_19184
0x19104  ldloc.s  6
0x19106  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x1910b  callvirt T0x2B000069
0x19110  stloc.s  7
0x19112  ldloc.s  7
0x19114  brfalse  loc_191F6
0x19119  ldloc.s  7
0x1911b  callvirt instance class [System.ServiceModel]System.ServiceModel.MessageSecurityVersion [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_MessageSecurityVersion()
0x19120  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.MessageSecurityVersion::get_TrustVersion()
0x19125  stloc.s  5
0x19127  ldloc.s  5
0x19129  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrust13()
0x1912e  bne.un   loc_191F6
0x19133  ldloc.s  6
0x19135  callvirt instance class [System.ServiceModel]System.ServiceModel.WSHttpSecurity [System.ServiceModel]System.ServiceModel.WSHttpBinding::get_Security()
0x1913a  callvirt instance class [System.ServiceModel]System.ServiceModel.NonDualMessageSecurityOverHttp [System.ServiceModel]System.ServiceModel.WSHttpSecurity::get_Message()
0x1913f  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.MessageCredentialType [System.ServiceModel]System.ServiceModel.MessageSecurityOverHttp::get_ClientCredentialType()
0x19144  ldc.i4.2
0x19145  bne.un.s loc_1914F
0x19147  ldc.i4.1
0x19148  stloc.s  4
0x1914a  br       loc_191F6
0x1914f  ldloc.s  6
0x19151  callvirt instance class [System.ServiceModel]System.ServiceModel.WSHttpSecurity [System.ServiceModel]System.ServiceModel.WSHttpBinding::get_Security()
0x19156  callvirt instance class [System.ServiceModel]System.ServiceModel.NonDualMessageSecurityOverHttp [System.ServiceModel]System.ServiceModel.WSHttpSecurity::get_Message()
0x1915b  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.MessageCredentialType [System.ServiceModel]System.ServiceModel.MessageSecurityOverHttp::get_ClientCredentialType()
0x19160  ldc.i4.3
0x19161  bne.un.s loc_1916B
0x19163  ldc.i4.5
0x19164  stloc.s  4
0x19166  br       loc_191F6
0x1916b  ldloc.s  6
0x1916d  callvirt instance class [System.ServiceModel]System.ServiceModel.WSHttpSecurity [System.ServiceModel]System.ServiceModel.WSHttpBinding::get_Security()
0x19172  callvirt instance class [System.ServiceModel]System.ServiceModel.NonDualMessageSecurityOverHttp [System.ServiceModel]System.ServiceModel.WSHttpSecurity::get_Message()
0x19177  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.MessageCredentialType [System.ServiceModel]System.ServiceModel.MessageSecurityOverHttp::get_ClientCredentialType()
0x1917c  ldc.i4.1
0x1917d  bne.un.s loc_191F6
0x1917f  ldc.i4.6
0x19180  stloc.s  4
0x19182  br.s     loc_191F6
0x19184  ldloc.3
0x19185  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x1918a  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x1918f  callvirt T0x2B000069
0x19194  stloc.s  8
0x19196  ldloc.s  8
0x19198  brfalse.s loc_191F6
0x1919a  ldloc.s  8
0x1919c  callvirt instance class [System.ServiceModel]System.ServiceModel.MessageSecurityVersion [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_MessageSecurityVersion()
0x191a1  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.MessageSecurityVersion::get_TrustVersion()
0x191a6  stloc.s  5
0x191a8  ldloc.s  5
0x191aa  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrust13()
0x191af  bne.un.s loc_191F6
0x191b1  ldloc.s  8
0x191b3  call     class [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuedTokenParameters(class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement securityElement)
0x191b8  stloc.s  9
0x191ba  ldloc.s  9
0x191bc  brfalse.s loc_191EA
0x191be  ldloc.s  9
0x191c0  callvirt instance valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_KeyType()
0x191c5  brtrue.s loc_191CC
0x191c7  ldc.i4.3
0x191c8  stloc.s  4
0x191ca  br.s     loc_191F6
0x191cc  ldloc.s  9
0x191ce  callvirt instance valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_KeyType()
0x191d3  ldc.i4.1
0x191d4  bne.un.s loc_191DB
0x191d6  ldc.i4.4
0x191d7  stloc.s  4
0x191d9  br.s     loc_191F6
0x191db  ldloc.s  9
0x191dd  callvirt instance valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_KeyType()
0x191e2  ldc.i4.2
0x191e3  bne.un.s loc_191F6
0x191e5  ldc.i4.7
0x191e6  stloc.s  4
0x191e8  br.s     loc_191F6
0x191ea  ldloc.s  8
0x191ec  call     class [System.ServiceModel]System.ServiceModel.Security.Tokens.KerberosSecurityTokenParameters Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetKerberosTokenParameters(class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement securityElement)
0x191f1  brfalse.s loc_191F6
0x191f3  ldc.i4.2
0x191f4  stloc.s  4
0x191f6  ldloc.s  4
0x191f8  brfalse.s loc_1924F
0x191fa  ldloca.s 4
0x191fc  constrained. Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType
0x19202  callvirt instance string [mscorlib]System.Object::ToString()
0x19207  stloc.s  0xA
0x19209  ldloc.0
0x1920a  ldloc.s  0xA
0x1920c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::ContainsKey(var<u1>)
0x19211  brtrue.s loc_1924F
0x19213  ldloc.0
0x19214  ldloc.s  0xA
0x19216  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::.ctor()
0x1921b  dup
0x1921c  ldloc.3
0x1921d  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x19222  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x19227  dup
0x19228  ldloc.3
0x19229  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x1922e  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding value)
0x19233  dup
0x19234  ldarg.0
0x19235  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerMetadataAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x1923a  dup
0x1923b  ldloc.s  4
0x1923d  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_CredentialType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x19242  dup
0x19243  ldloc.s  5
0x19245  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_TrustVersion(class [System.ServiceModel]System.ServiceModel.Security.TrustVersion value)
0x1924a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::Add(var<u1>, !!T0)
0x1924f  ldloc.2
0x19250  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19255  brtrue   loc_190CF
0x1925a  leave.s  loc_19266
0x1925c  ldloc.2
0x1925d  brfalse.s loc_19265
0x1925f  ldloc.2
0x19260  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19265  endfinally
0x19266  ldloc.0
0x19267  ret
```
