# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateTokenWithOrgIdForCrm

- ea: `0x16600`
- end: `0x1664f`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateTokenWithOrgIdForCrm`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x15540`
- `0x15550`
- `0x155d0`
- `0x155f0`
- `0x15630`
- `0x15670`
- `0x15680`
- `0x15690`
- `0x156a0`

## string_xrefs

- `0x16630`: `http://schemas.microsoft.com/idfx/keytype/bearer`

## pseudocode

```c

```

## disassembly

```asm
0x16600  ldarg.1
0x16601  ldstr    aAuthentication_1// "authenticationCredentials"
0x16606  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1660b  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16610  dup
0x16611  ldarg.1
0x16612  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SupportingCredentials(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials value)
0x16617  dup
0x16618  ldarg.1
0x16619  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x1661e  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x16623  dup
0x16624  ldarg.1
0x16625  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoints()
0x1662a  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x1662f  dup
0x16630  ldstr    aHttpSchemasMic_17// "http://schemas.microsoft.com/idfx/keyty"...
0x16635  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x1663a  dup
0x1663b  ldc.i4.1
0x1663c  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x16641  dup
0x16642  ldarg.0
0x16643  ldarg.1
0x16644  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x16649  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x1664e  ret
```
