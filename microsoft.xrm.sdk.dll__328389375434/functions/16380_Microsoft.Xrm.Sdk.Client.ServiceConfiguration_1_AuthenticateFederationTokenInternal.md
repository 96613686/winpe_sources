# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateFederationTokenInternal

- ea: `0x16380`
- end: `0x163e1`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateFederationTokenInternal`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15540`
- `0x15550`
- `0x155d0`
- `0x155f0`
- `0x15630`
- `0x15670`
- `0x15690`
- `0x156a0`
- `0x16380`

## pseudocode

```c

```

## disassembly

```asm
0x16380  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16385  dup
0x16386  ldarg.1
0x16387  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SupportingCredentials(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials value)
0x1638c  ldarg.1
0x1638d  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x16392  ldnull
0x16393  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x16398  brfalse.s loc_163B0
0x1639a  ldarg.1
0x1639b  ldarg.0
0x1639c  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x163a1  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x163a6  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x163ab  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x163b0  ldarg.1
0x163b1  ldarg.0
0x163b2  ldfld    valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_tokenEndpointType
0x163b7  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x163bc  ldarg.1
0x163bd  ldsfld   string [mscorlib]System.String::Empty
0x163c2  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x163c7  ldarg.1
0x163c8  ldarg.0
0x163c9  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x163ce  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x163d3  dup
0x163d4  ldarg.0
0x163d5  ldarg.1
0x163d6  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x163db  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x163e0  ret
```
