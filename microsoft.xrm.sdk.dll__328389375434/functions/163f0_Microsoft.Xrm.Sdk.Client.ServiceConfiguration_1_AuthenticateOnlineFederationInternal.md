# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateOnlineFederationInternal

- ea: `0x163f0`
- end: `0x16514`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateOnlineFederationInternal`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x7d70`
- `0x15550`
- `0x15560`
- `0x15570`
- `0x15580`
- `0x155a0`
- `0x155c0`
- `0x15630`
- `0x15670`
- `0x15690`
- `0x163f0`
- `0x17a30`
- `0x17a50`
- `0x18090`
- `0x18230`
- `0x18430`

## string_xrefs

- `0x1641e`: `liveTrustConfig`
- `0x164e2`: `http://schemas.microsoft.com/idfx/keytype/bearer`

## pseudocode

```c

```

## disassembly

```asm
0x163f0  ldarg.0
0x163f1  call     instance class Microsoft.Xrm.Sdk.Client.PolicyConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_PolicyConfiguration()
0x163f6  isinst   Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration
0x163fb  stloc.0
0x163fc  ldloc.0
0x163fd  ldstr    aOnlinepolicy// "onlinePolicy"
0x16402  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16407  ldloc.0
0x16408  callvirt instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x1640d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Values()
0x16412  call     T0x2B000061
0x16417  call     T0x2B000062
0x1641c  stloc.1
0x1641d  ldloc.1
0x1641e  ldstr    aLivetrustconfi// "liveTrustConfig"
0x16423  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16428  ldarg.1
0x16429  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x1642e  brfalse.s loc_16439
0x16430  ldarg.0
0x16431  ldloc.1
0x16432  ldarg.1
0x16433  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateOnlineFederationTokenInternal(class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration, class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x16438  ret
0x16439  ldc.i4.1
0x1643a  stloc.2
0x1643b  ldarg.1
0x1643c  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_HomeRealm()
0x16441  ldnull
0x16442  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x16447  brfalse.s loc_164C4
0x16449  ldarg.1
0x1644a  callvirt instance string Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_UserPrincipalName()
0x1644f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16454  brfalse.s loc_16464
0x16456  ldarg.0
0x16457  ldarg.1
0x16458  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_ClientCredentials()
0x1645d  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProvider class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::GetIdentityProvider(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x16462  br.s     loc_16470
0x16464  ldarg.0
0x16465  ldarg.1
0x16466  callvirt instance string Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_UserPrincipalName()
0x1646b  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProvider class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::GetIdentityProvider(string)
0x16470  stloc.s  4
0x16472  ldloc.s  4
0x16474  ldstr    aIdentityprovid// "identityProvider"
0x16479  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1647e  ldarg.1
0x1647f  ldloc.s  4
0x16481  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProvider::get_ServiceUrl()
0x16486  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_HomeRealm(class [System]System.Uri value)
0x1648b  ldloc.s  4
0x1648d  callvirt instance valuetype Microsoft.Xrm.Sdk.Client.IdentityProviderType Microsoft.Xrm.Sdk.Client.IdentityProvider::get_IdentityProviderType()
0x16492  ldc.i4.2
0x16493  ceq
0x16495  stloc.2
0x16496  ldloc.2
0x16497  brfalse.s loc_164C4
0x16499  ldloc.0
0x1649a  callvirt instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x1649f  ldarg.1
0x164a0  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_HomeRealm()
0x164a5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::ContainsKey(var<u1>)
0x164aa  ldstr    aOnlineIdentity// "Online Identity Provider NOT found!  {0"...
0x164af  ldc.i4.1
0x164b0  newarr   [mscorlib]System.Object
0x164b5  dup
0x164b6  ldc.i4.0
0x164b7  ldloc.s  4
0x164b9  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProvider::get_ServiceUrl()
0x164be  stelem.ref
0x164bf  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::Assert(bool condition, string message, object[] args)
0x164c4  ldarg.1
0x164c5  ldloc.1
0x164c6  callvirt instance string Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_AppliesTo()
0x164cb  newobj   instance void [System]System.Uri::.ctor(string)
0x164d0  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x164d5  ldarg.1
0x164d6  ldarg.0
0x164d7  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x164dc  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x164e1  ldarg.1
0x164e2  ldstr    aHttpSchemasMic_17// "http://schemas.microsoft.com/idfx/keyty"...
0x164e7  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x164ec  ldarg.1
0x164ed  ldc.i4.1
0x164ee  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x164f3  ldloc.2
0x164f4  brfalse.s loc_164FE
0x164f6  ldarg.0
0x164f7  ldarg.1
0x164f8  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateTokenWithOrgIdForCrm(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x164fd  ret
0x164fe  ldarg.0
0x164ff  ldarg.1
0x16500  ldloc.1
0x16501  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.OrgIdentityProviderTrustConfiguration::get_Identifier()
0x16506  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateWithADFSForOrgId(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials, class [System]System.Uri)
0x1650b  stloc.3
0x1650c  ldarg.0
0x1650d  ldloc.3
0x1650e  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateFederatedTokenWithOrgIdForCRM(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x16513  ret
```
