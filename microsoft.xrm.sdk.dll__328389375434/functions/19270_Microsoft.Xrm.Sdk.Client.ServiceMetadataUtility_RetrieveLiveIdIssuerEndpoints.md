# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveLiveIdIssuerEndpoints

- ea: `0x19270`
- end: `0x1931c`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveLiveIdIssuerEndpoints`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x16900`

## callees

- `0xdd0`
- `0x1410`
- `0x1800`
- `0x1820`
- `0x17820`
- `0x17860`
- `0x17880`
- `0x178b0`
- `0x17940`
- `0x18020`
- `0x18030`
- `0x180b0`
- `0x180d0`

## pseudocode

```c

```

## disassembly

```asm
0x19270  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::.ctor()
0x19275  dup
0x19276  ldc.i4.1
0x19277  stloc.1
0x19278  ldloca.s 1
0x1927a  constrained. Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType
0x19280  callvirt instance string [mscorlib]System.Object::ToString()
0x19285  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::.ctor()
0x1928a  dup
0x1928b  ldc.i4.1
0x1928c  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_CredentialType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x19291  dup
0x19292  ldarg.0
0x19293  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x19298  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1929d  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(string)
0x192a2  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x192a7  dup
0x192a8  ldarg.0
0x192a9  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Binding()
0x192ae  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding value)
0x192b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::Add(var<u1>, !!T0)
0x192b8  newobj   instance void Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::.ctor()
0x192bd  dup
0x192be  ldarg.0
0x192bf  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_TrustVersion()
0x192c4  callvirt instance void Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::set_TrustVersion(class [System.ServiceModel]System.ServiceModel.Security.TrustVersion value)
0x192c9  dup
0x192ca  ldarg.0
0x192cb  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_SecurityMode()
0x192d0  callvirt instance void Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::set_SecurityMode(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode value)
0x192d5  stloc.0
0x192d6  ldloc.0
0x192d7  ldc.i4.2
0x192d8  callvirt instance void Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::set_KeyType(valuetype [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyType value)
0x192dd  dup
0x192de  ldc.i4.3
0x192df  stloc.1
0x192e0  ldloca.s 1
0x192e2  constrained. Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType
0x192e8  callvirt instance string [mscorlib]System.Object::ToString()
0x192ed  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::.ctor()
0x192f2  dup
0x192f3  ldc.i4.3
0x192f4  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_CredentialType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x192f9  dup
0x192fa  ldarg.0
0x192fb  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x19300  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x19305  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(string)
0x1930a  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x1930f  dup
0x19310  ldloc.0
0x19311  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding value)
0x19316  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint>::Add(var<u1>, !!T0)
0x1931b  ret
```
