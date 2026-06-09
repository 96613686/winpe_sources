# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateOnlineFederationTokenInternal

- ea: `0x16650`
- end: `0x166ae`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateOnlineFederationTokenInternal`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15540`
- `0x15560`
- `0x155c0`
- `0x155d0`
- `0x155f0`
- `0x156a0`
- `0x16650`
- `0x18020`
- `0x18090`
- `0x19ba0`
- `0x19cc0`

## pseudocode

```c

```

## disassembly

```asm
0x16650  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16655  dup
0x16656  ldarg.2
0x16657  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SupportingCredentials(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials value)
0x1665c  ldarg.2
0x1665d  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x16662  ldnull
0x16663  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x16668  brtrue.s loc_16672
0x1666a  ldarg.1
0x1666b  callvirt instance string Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_AppliesTo()
0x16670  br.s     loc_1667D
0x16672  ldarg.2
0x16673  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x16678  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x1667d  stloc.0
0x1667e  ldarg.2
0x1667f  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_HomeRealm()
0x16684  dup
0x16685  brtrue.s loc_16693
0x16687  pop
0x16688  ldarg.1
0x16689  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x1668e  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x16693  stloc.1
0x16694  dup
0x16695  ldarg.0
0x16696  ldarg.2
0x16697  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x1669c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::get_Token()
0x166a1  ldloc.0
0x166a2  ldloc.1
0x166a3  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateCrossRealm(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, string, class [System]System.Uri)
0x166a8  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x166ad  ret
```
