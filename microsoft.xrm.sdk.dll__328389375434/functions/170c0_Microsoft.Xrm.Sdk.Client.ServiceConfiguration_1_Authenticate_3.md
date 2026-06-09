# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_3

- ea: `0x170c0`
- end: `0x17128`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_3`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
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
- `0x170c0`
- `0x19ba0`
- `0x19cd0`
- `0x19d20`

## string_xrefs

- `0x170c1`: `securityToken`

## pseudocode

```c

```

## disassembly

```asm
0x170c0  ldarg.1
0x170c1  ldstr    aSecuritytoken// "securityToken"
0x170c6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x170cb  ldarg.2
0x170cc  ldnull
0x170cd  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x170d2  brfalse.s loc_17126
0x170d4  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x170d9  stloc.0
0x170da  ldloc.0
0x170db  ldarg.2
0x170dc  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x170e1  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x170e6  ldloc.0
0x170e7  ldarg.0
0x170e8  ldfld    valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_tokenEndpointType
0x170ed  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x170f2  ldloc.0
0x170f3  ldarg.3
0x170f4  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x170f9  ldloc.0
0x170fa  ldarg.0
0x170fb  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x17100  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x17105  ldloc.0
0x17106  ldnull
0x17107  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_ClientCredentials(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials value)
0x1710c  ldloc.0
0x1710d  newobj   instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::.ctor()
0x17112  dup
0x17113  ldarg.1
0x17114  callvirt instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::set_Token(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken value)
0x17119  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x1711e  ldarg.0
0x1711f  ldloc.0
0x17120  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x17125  ret
0x17126  ldnull
0x17127  ret
```
