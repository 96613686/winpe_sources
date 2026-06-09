# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_1

- ea: `0x16fc0`
- end: `0x17003`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Authenticate_1`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15550`
- `0x155b0`
- `0x155d0`
- `0x15630`
- `0x15670`
- `0x15690`
- `0x156a0`

## pseudocode

```c

```

## disassembly

```asm
0x16fc0  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16fc5  stloc.0
0x16fc6  ldloc.0
0x16fc7  ldarg.2
0x16fc8  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x16fcd  ldloc.0
0x16fce  ldarg.0
0x16fcf  ldarg.1
0x16fd0  call     instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::GetCredentialsEndpointType(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x16fd5  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x16fda  ldloc.0
0x16fdb  ldarg.3
0x16fdc  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x16fe1  ldloc.0
0x16fe2  ldarg.0
0x16fe3  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x16fe8  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x16fed  ldloc.0
0x16fee  ldarg.1
0x16fef  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_ClientCredentials(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials value)
0x16ff4  ldloc.0
0x16ff5  ldnull
0x16ff6  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x16ffb  ldarg.0
0x16ffc  ldloc.0
0x16ffd  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x17002  ret
```
