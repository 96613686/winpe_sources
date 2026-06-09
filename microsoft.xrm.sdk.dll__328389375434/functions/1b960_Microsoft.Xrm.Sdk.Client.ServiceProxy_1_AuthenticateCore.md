# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::AuthenticateCore

- ea: `0x1b960`
- end: `0x1b9f5`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::AuthenticateCore`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x7d90`
- `0x19cc0`
- `0x1b960`

## string_xrefs

- `0x1b9b2`: `Authentication to MSA services is not supported.`
- `0x1b966`: `ServiceConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x1b960  ldarg.0
0x1b961  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b966  ldstr    aServiceconfigu_0// "ServiceConfiguration"
0x1b96b  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b970  ldarg.0
0x1b971  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b976  callvirt instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x1b97b  ldc.i4.1
0x1b97c  bne.un.s loc_1B986
0x1b97e  ldarg.0
0x1b97f  ldc.i4.1
0x1b980  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_IsAuthenticated(bool)
0x1b985  ret
0x1b986  ldarg.0
0x1b987  call     instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ClientCredentials()
0x1b98c  brfalse.s loc_1B9F4
0x1b98e  ldnull
0x1b98f  stloc.0
0x1b990  ldarg.0
0x1b991  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b996  callvirt instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x1b99b  stloc.1
0x1b99c  ldloc.1
0x1b99d  ldc.i4.2
0x1b99e  sub
0x1b99f  switch   loc_1B9C6, loc_1B9B2, loc_1B9BD
0x1b9b0  br.s     loc_1B9CD
0x1b9b2  ldstr    aAuthentication_3// "Authentication to MSA services is not s"...
0x1b9b7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1b9bc  throw
0x1b9bd  ldarg.0
0x1b9be  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::AuthenticateOnlineFederation()
0x1b9c3  stloc.0
0x1b9c4  br.s     loc_1B9CD
0x1b9c6  ldarg.0
0x1b9c7  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::AuthenticateClaims()
0x1b9cc  stloc.0
0x1b9cd  ldloc.0
0x1b9ce  brfalse.s loc_1B9DB
0x1b9d0  ldloc.0
0x1b9d1  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::get_Token()
0x1b9d6  ldnull
0x1b9d7  cgt.un
0x1b9d9  br.s     loc_1B9DC
0x1b9db  ldc.i4.0
0x1b9dc  ldstr    aTheUserAuthent// "The user authentication failed!"
0x1b9e1  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::Assert(bool condition, string message)
0x1b9e6  ldarg.0
0x1b9e7  ldloc.0
0x1b9e8  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse)
0x1b9ed  ldarg.0
0x1b9ee  ldc.i4.1
0x1b9ef  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_IsAuthenticated(bool)
0x1b9f4  ret
```
