# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateFederatedTokenWithOrgIdForCRM

- ea: `0x16520`
- end: `0x16576`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateFederatedTokenWithOrgIdForCRM`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x15540`
- `0x15550`
- `0x155c0`
- `0x155d0`
- `0x155f0`
- `0x15630`
- `0x15680`
- `0x15690`
- `0x156a0`

## string_xrefs

- `0x16531`: `authenticationCredentials.SecurityTokenResponse`

## pseudocode

```c

```

## disassembly

```asm
0x16520  ldarg.1
0x16521  ldstr    aAuthentication_1// "authenticationCredentials"
0x16526  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1652b  ldarg.1
0x1652c  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x16531  ldstr    aAuthentication_2// "authenticationCredentials.SecurityToken"...
0x16536  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1653b  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16540  stloc.0
0x16541  ldloc.0
0x16542  ldarg.1
0x16543  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SupportingCredentials(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials value)
0x16548  ldloc.0
0x16549  ldarg.1
0x1654a  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x1654f  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x16554  ldloc.0
0x16555  ldarg.1
0x16556  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoints()
0x1655b  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x16560  ldloc.0
0x16561  ldc.i4.3
0x16562  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x16567  ldloc.0
0x16568  ldarg.0
0x16569  ldloc.0
0x1656a  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x1656f  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x16574  ldloc.0
0x16575  ret
```
