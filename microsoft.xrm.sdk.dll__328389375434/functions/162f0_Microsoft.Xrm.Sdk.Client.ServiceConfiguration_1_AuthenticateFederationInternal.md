# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateFederationInternal

- ea: `0x162f0`
- end: `0x16372`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateFederationInternal`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15540`
- `0x15550`
- `0x15560`
- `0x155a0`
- `0x155c0`
- `0x155d0`
- `0x15630`
- `0x15690`
- `0x162f0`

## pseudocode

```c

```

## disassembly

```asm
0x162f0  ldarg.1
0x162f1  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_SecurityTokenResponse()
0x162f6  brfalse.s loc_16300
0x162f8  ldarg.0
0x162f9  ldarg.1
0x162fa  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateFederationTokenInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x162ff  ret
0x16300  ldarg.1
0x16301  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x16306  ldnull
0x16307  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1630c  brfalse.s loc_16324
0x1630e  ldarg.1
0x1630f  ldarg.0
0x16310  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16315  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x1631a  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x1631f  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x16324  ldarg.1
0x16325  ldarg.0
0x16326  ldarg.1
0x16327  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_ClientCredentials()
0x1632c  call     instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::GetCredentialsEndpointType(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x16331  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x16336  ldarg.1
0x16337  ldarg.1
0x16338  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_HomeRealm()
0x1633d  ldnull
0x1633e  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x16343  brtrue.s loc_1634D
0x16345  ldarg.0
0x16346  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x1634b  br.s     loc_1635E
0x1634d  ldarg.0
0x1634e  call     instance class Microsoft.Xrm.Sdk.Client.CrossRealmIssuerEndpointCollection class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CrossRealmIssuerEndpoints()
0x16353  ldarg.1
0x16354  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_HomeRealm()
0x16359  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary>::get_Item(void)
0x1635e  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x16363  ldarg.1
0x16364  ldarg.0
0x16365  ldarg.1
0x16366  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x1636b  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x16370  ldarg.1
0x16371  ret
```
