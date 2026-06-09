# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::.ctor_1

- ea: `0x1b4f0`
- end: `0x1b553`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::.ctor_1`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x19cc0`

## string_xrefs

- `0x1b502`: `serviceConfiguration`
- `0x1b512`: `serviceConfiguration.CurrentServiceEndpoint`
- `0x1b51d`: `securityTokenResponse`
- `0x1b52d`: `securityTokenResponse.Token`

## pseudocode

```c

```

## disassembly

```asm
0x1b4f0  ldarg.0
0x1b4f1  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Xrm.Sdk.Client.ServiceDefaults::DefaultTimeout
0x1b4f6  stfld    valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::_timeout
0x1b4fb  ldarg.0
0x1b4fc  call     instance void [mscorlib]System.Object::.ctor()
0x1b501  ldarg.1
0x1b502  ldstr    aServiceconfigu// "serviceConfiguration"
0x1b507  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b50c  ldarg.1
0x1b50d  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x1b512  ldstr    aServiceconfigu_1// "serviceConfiguration.CurrentServiceEndp"...
0x1b517  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b51c  ldarg.2
0x1b51d  ldstr    aSecuritytokenr// "securityTokenResponse"
0x1b522  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b527  ldarg.2
0x1b528  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::get_Token()
0x1b52d  ldstr    aSecuritytokenr_0// "securityTokenResponse.Token"
0x1b532  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b537  ldarg.0
0x1b538  ldarg.1
0x1b539  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_ServiceConfiguration(class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>)
0x1b53e  ldarg.0
0x1b53f  ldarg.2
0x1b540  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse)
0x1b545  ldarg.0
0x1b546  ldc.i4.1
0x1b547  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_IsAuthenticated(bool)
0x1b54c  ldarg.0
0x1b54d  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::SetDefaultEndpointSwitchBehavior()
0x1b552  ret
```
