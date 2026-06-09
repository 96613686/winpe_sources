# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Issue

- ea: `0x172b0`
- end: `0x1742c`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::Issue`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x15540`
- `0x155a0`
- `0x155c0`
- `0x155e0`
- `0x15600`
- `0x15620`
- `0x15640`
- `0x15650`
- `0x15660`
- `0x172b0`
- `0x17850`
- `0x17870`
- `0x19cc0`
- `0x19cd0`
- `0x19cf0`
- `0x19d10`
- `0x19d20`
- `0x1b320`

## string_xrefs

- `0x172e0`: `http://schemas.microsoft.com/idfx/requesttype/issue`

## pseudocode

```c

```

## disassembly

```asm
0x172b0  ldarg.1
0x172b1  ldstr    aAuthentication_1// "authenticationCredentials"
0x172b6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x172bb  ldarg.1
0x172bc  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoint()
0x172c1  ldstr    aAuthentication_4// "authenticationCredentials.IssuerEndpoin"...
0x172c6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x172cb  ldarg.1
0x172cc  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x172d1  ldstr    aAuthentication_5// "authenticationCredentials.AppliesTo"
0x172d6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x172db  ldnull
0x172dc  stloc.0
0x172dd  ldnull
0x172de  stloc.1
0x172df  ldarg.1
0x172e0  ldstr    aHttpSchemasMic_18// "http://schemas.microsoft.com/idfx/reque"...
0x172e5  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_RequestType(string value)
0x172ea  ldarg.1
0x172eb  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoint()
0x172f0  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerBinding()
0x172f5  ldarg.1
0x172f6  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoint()
0x172fb  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerAddress()
0x17300  newobj   instance void [System.ServiceModel]System.ServiceModel.Security.WSTrustChannelFactory::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding, class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x17305  stloc.0
0x17306  ldarg.1
0x17307  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x1730c  brfalse.s loc_1731B
0x1730e  ldarg.1
0x1730f  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x17314  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::get_Token()
0x17319  brtrue.s loc_17357
0x1731b  ldarg.1
0x1731c  callvirt instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SupportingCredentials()
0x17321  brfalse.s loc_17342
0x17323  ldarg.1
0x17324  callvirt instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SupportingCredentials()
0x17329  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x1732e  brfalse.s loc_17342
0x17330  ldarg.1
0x17331  callvirt instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SupportingCredentials()
0x17336  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x1733b  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::get_Token()
0x17340  brtrue.s loc_17345
0x17342  ldnull
0x17343  br.s     loc_17362
0x17345  ldarg.1
0x17346  callvirt instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SupportingCredentials()
0x1734b  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x17350  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::get_Token()
0x17355  br.s     loc_17362
0x17357  ldarg.1
0x17358  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x1735d  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::get_Token()
0x17362  stloc.2
0x17363  ldloc.2
0x17364  brfalse.s loc_17374
0x17366  ldloc.0
0x17367  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Credentials()
0x1736c  ldc.i4.0
0x1736d  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::set_SupportInteractive(bool)
0x17372  br.s     loc_17381
0x17374  ldarg.0
0x17375  ldloc.0
0x17376  ldarg.1
0x17377  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_ClientCredentials()
0x1737c  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::ConfigureCredentials(class [System.ServiceModel]System.ServiceModel.ChannelFactory, class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x17381  ldloc.2
0x17382  brtrue.s loc_17391
0x17384  ldloc.0
0x17385  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class [System.ServiceModel]System.ServiceModel.Security.IWSTrustChannelContract>::CreateChannel()
0x1738a  castclass [System.ServiceModel]System.ServiceModel.Security.WSTrustChannel
0x1738f  br.s     loc_1739D
0x17391  ldloc.0
0x17392  ldloc.2
0x17393  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<class [System.ServiceModel]System.ServiceModel.Security.IWSTrustChannelContract>::CreateChannelWithIssuedToken(!!T0)
0x17398  castclass [System.ServiceModel]System.ServiceModel.Security.WSTrustChannel
0x1739d  stloc.1
0x1739e  ldloc.1
0x1739f  brfalse.s loc_1740C
0x173a1  ldarg.1
0x173a2  callvirt instance string Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_RequestType()
0x173a7  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.RequestSecurityToken::.ctor(string)
0x173ac  dup
0x173ad  ldarg.1
0x173ae  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x173b3  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x173b8  newobj   instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::.ctor(string)
0x173bd  callvirt instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.WSTrustMessage::set_AppliesTo(class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference)
0x173c2  stloc.3
0x173c3  ldarg.1
0x173c4  callvirt instance string Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_KeyType()
0x173c9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x173ce  brtrue.s loc_173DC
0x173d0  ldloc.3
0x173d1  ldarg.1
0x173d2  callvirt instance string Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_KeyType()
0x173d7  callvirt instance void [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.WSTrustMessage::set_KeyType(string)
0x173dc  ldloc.1
0x173dd  ldloc.3
0x173de  ldloca.s 4
0x173e0  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [System.ServiceModel]System.ServiceModel.Security.WSTrustChannel::Issue(class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.RequestSecurityToken, class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.RequestSecurityTokenResponse&)
0x173e5  stloc.s  5
0x173e7  newobj   instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::.ctor()
0x173ec  dup
0x173ed  ldloc.s  5
0x173ef  callvirt instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::set_Token(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken value)
0x173f4  dup
0x173f5  ldloc.s  4
0x173f7  callvirt instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::set_Response(class [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.RequestSecurityTokenResponse value)
0x173fc  dup
0x173fd  ldarg.1
0x173fe  callvirt instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_EndpointType()
0x17403  callvirt instance void Microsoft.Xrm.Sdk.Client.SecurityTokenResponse::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x17408  stloc.s  6
0x1740a  leave.s  loc_17429
0x1740c  leave.s  loc_17427
0x1740e  ldloc.1
0x1740f  brfalse.s loc_17418
0x17411  ldloc.1
0x17412  ldc.i4.1
0x17413  call     void Microsoft.Xrm.Sdk.Client.ChannelExtensions::Close(class [System.ServiceModel]System.ServiceModel.ICommunicationObject communicationObject, [opt] bool throwOnException)
0x17418  ldnull
0x17419  stloc.1
0x1741a  ldloc.0
0x1741b  brfalse.s loc_17424
0x1741d  ldloc.0
0x1741e  ldc.i4.1
0x1741f  call     void Microsoft.Xrm.Sdk.Client.ChannelExtensions::Close(class [System.ServiceModel]System.ServiceModel.ICommunicationObject communicationObject, [opt] bool throwOnException)
0x17424  ldnull
0x17425  stloc.0
0x17426  endfinally
0x17427  ldnull
0x17428  ret
0x17429  ldloc.s  6
0x1742b  ret
```
