# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_2

- ea: `0x17010`
- end: `0x170b3`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_2`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x15550`
- `0x155b0`
- `0x155d0`
- `0x15630`
- `0x15670`
- `0x15690`
- `0x156a0`
- `0x17010`
- `0x18020`
- `0x18090`
- `0x19ba0`
- `0x19cd0`
- `0x19d20`

## string_xrefs

- `0x17011`: `securityToken`

## pseudocode

```c

```

## disassembly

```asm
0x17010  ldarg.1
0x17011  ldstr    aSecuritytoken// "securityToken"
0x17016  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1701b  ldarg.0
0x1701c  call     instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x17021  ldc.i4.4
0x17022  bne.un.s loc_17049
0x17024  ldarg.0
0x17025  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::TryGetOnlineTrustConfiguration()
0x1702a  stloc.0
0x1702b  ldloc.0
0x1702c  brtrue.s loc_17030
0x1702e  ldnull
0x1702f  ret
0x17030  ldarg.0
0x17031  ldarg.1
0x17032  ldloc.0
0x17033  callvirt instance string Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_AppliesTo()
0x17038  ldloc.0
0x17039  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x1703e  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x17043  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateCrossRealm(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, string, class [System]System.Uri)
0x17048  ret
0x17049  ldarg.0
0x1704a  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x1704f  brfalse.s loc_170B1
0x17051  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x17056  stloc.1
0x17057  ldloc.1
0x17058  ldarg.0
0x17059  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x1705e  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x17063  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x17068  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x1706d  ldloc.1
0x1706e  ldarg.0
0x1706f  ldfld    valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_tokenEndpointType
0x17074  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x17079  ldloc.1
0x1707a  ldsfld   string [mscorlib]System.String::Empty
0x1707f  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x17084  ldloc.1
0x17085  ldarg.0
0x17086  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x1708b  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x17090  ldloc.1
0x17091  ldnull
0x17092  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_ClientCredentials(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials value)
0x17097  ldloc.1
0x17098  newobj   instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::.ctor()
0x1709d  dup
0x1709e  ldarg.1
0x1709f  callvirt instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::set_Token(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken value)
0x170a4  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x170a9  ldarg.0
0x170aa  ldloc.1
0x170ab  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x170b0  ret
0x170b1  ldnull
0x170b2  ret
```
