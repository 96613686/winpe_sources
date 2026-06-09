# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateCrossRealm_0

- ea: `0x16df0`
- end: `0x16e9a`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateCrossRealm_0`
- size: `170`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15550`
- `0x155b0`
- `0x155d0`
- `0x15630`
- `0x15670`
- `0x15690`
- `0x156a0`
- `0x16df0`
- `0x18020`
- `0x19ba0`
- `0x19cd0`
- `0x19d20`

## pseudocode

```c

```

## disassembly

```asm
0x16df0  ldarg.3
0x16df1  ldnull
0x16df2  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x16df7  brfalse  loc_16E98
0x16dfc  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16e01  stloc.0
0x16e02  ldloc.0
0x16e03  ldarg.2
0x16e04  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x16e09  brfalse.s loc_16E0E
0x16e0b  ldnull
0x16e0c  br.s     loc_16E14
0x16e0e  ldarg.2
0x16e0f  newobj   instance void [System]System.Uri::.ctor(string)
0x16e14  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x16e19  ldloc.0
0x16e1a  ldsfld   string [mscorlib]System.String::Empty
0x16e1f  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x16e24  ldloc.0
0x16e25  ldnull
0x16e26  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_ClientCredentials(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials value)
0x16e2b  ldloc.0
0x16e2c  newobj   instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::.ctor()
0x16e31  dup
0x16e32  ldarg.1
0x16e33  callvirt instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::set_Token(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken value)
0x16e38  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x16e3d  ldc.i4.1
0x16e3e  stloc.1
0x16e3f  ldarg.0
0x16e40  call     instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x16e45  ldc.i4.4
0x16e46  bne.un.s loc_16E6F
0x16e48  ldarg.0
0x16e49  ldarg.3
0x16e4a  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::TryGetOnlineTrustConfiguration(class [System]System.Uri)
0x16e4f  stloc.2
0x16e50  ldloc.2
0x16e51  brfalse.s loc_16E6F
0x16e53  ldloc.2
0x16e54  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x16e59  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x16e5e  ldarg.3
0x16e5f  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x16e64  brfalse.s loc_16E6F
0x16e66  ldloc.0
0x16e67  ldc.i4.3
0x16e68  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x16e6d  ldc.i4.0
0x16e6e  stloc.1
0x16e6f  ldloc.1
0x16e70  brfalse.s loc_16E7E
0x16e72  ldloc.0
0x16e73  ldarg.0
0x16e74  ldfld    valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_tokenEndpointType
0x16e79  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x16e7e  ldloc.0
0x16e7f  ldarg.0
0x16e80  call     instance class Microsoft.Xrm.Sdk.Client.CrossRealmIssuerEndpointCollection class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CrossRealmIssuerEndpoints()
0x16e85  ldarg.3
0x16e86  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary>::get_Item(void)
0x16e8b  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x16e90  ldarg.0
0x16e91  ldloc.0
0x16e92  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x16e97  ret
0x16e98  ldnull
0x16e99  ret
```
