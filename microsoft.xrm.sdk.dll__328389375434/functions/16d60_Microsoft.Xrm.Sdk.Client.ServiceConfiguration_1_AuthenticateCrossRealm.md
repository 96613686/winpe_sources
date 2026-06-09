# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateCrossRealm

- ea: `0x16d60`
- end: `0x16df0`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateCrossRealm`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15550`
- `0x155b0`
- `0x155d0`
- `0x15630`
- `0x15670`
- `0x15690`
- `0x156a0`
- `0x16d60`

## string_xrefs

- `0x16ddc`: `http://schemas.microsoft.com/idfx/keytype/bearer`

## pseudocode

```c

```

## disassembly

```asm
0x16d60  ldarg.3
0x16d61  ldnull
0x16d62  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x16d67  brfalse  loc_16DEE
0x16d6c  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16d71  stloc.0
0x16d72  ldloc.0
0x16d73  ldarg.2
0x16d74  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x16d79  brfalse.s loc_16D7E
0x16d7b  ldnull
0x16d7c  br.s     loc_16D84
0x16d7e  ldarg.2
0x16d7f  newobj   instance void [System]System.Uri::.ctor(string)
0x16d84  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x16d89  ldloc.0
0x16d8a  ldsfld   string [mscorlib]System.String::Empty
0x16d8f  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x16d94  ldloc.0
0x16d95  ldarg.1
0x16d96  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_ClientCredentials(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials value)
0x16d9b  ldloc.0
0x16d9c  ldnull
0x16d9d  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x16da2  ldarg.0
0x16da3  ldarg.3
0x16da4  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::TryGetOnlineTrustConfiguration(class [System]System.Uri)
0x16da9  stloc.1
0x16daa  ldloc.0
0x16dab  ldloc.1
0x16dac  brtrue.s loc_16DB7
0x16dae  ldarg.0
0x16daf  ldarg.1
0x16db0  call     instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::GetCredentialsEndpointType(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x16db5  br.s     loc_16DB8
0x16db7  ldc.i4.1
0x16db8  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x16dbd  ldloc.0
0x16dbe  ldarg.0
0x16dbf  call     instance class Microsoft.Xrm.Sdk.Client.CrossRealmIssuerEndpointCollection class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CrossRealmIssuerEndpoints()
0x16dc4  ldarg.3
0x16dc5  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary>::get_Item(void)
0x16dca  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x16dcf  ldarg.0
0x16dd0  call     instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x16dd5  ldc.i4.4
0x16dd6  bne.un.s loc_16DE6
0x16dd8  ldloc.1
0x16dd9  brtrue.s loc_16DE6
0x16ddb  ldloc.0
0x16ddc  ldstr    aHttpSchemasMic_17// "http://schemas.microsoft.com/idfx/keyty"...
0x16de1  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x16de6  ldarg.0
0x16de7  ldloc.0
0x16de8  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x16ded  ret
0x16dee  ldnull
0x16def  ret
```
