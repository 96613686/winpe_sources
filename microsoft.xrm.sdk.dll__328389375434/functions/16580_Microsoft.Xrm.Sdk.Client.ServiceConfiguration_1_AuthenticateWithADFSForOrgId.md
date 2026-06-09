# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateWithADFSForOrgId

- ea: `0x16580`
- end: `0x16600`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::AuthenticateWithADFSForOrgId`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15540`
- `0x15550`
- `0x15560`
- `0x155a0`
- `0x155d0`
- `0x155f0`
- `0x15630`
- `0x15670`
- `0x15680`
- `0x15690`
- `0x156a0`

## string_xrefs

- `0x165bf`: `http://schemas.microsoft.com/idfx/keytype/bearer`

## pseudocode

```c

```

## disassembly

```asm
0x16580  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::.ctor()
0x16585  dup
0x16586  ldarg.1
0x16587  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x1658c  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x16591  dup
0x16592  ldarg.1
0x16593  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SupportingCredentials(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials value)
0x16598  dup
0x16599  ldarg.1
0x1659a  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_AppliesTo()
0x1659f  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x165a4  dup
0x165a5  ldarg.1
0x165a6  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_IssuerEndpoints()
0x165ab  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x165b0  dup
0x165b1  ldc.i4.3
0x165b2  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x165b7  ldarg.1
0x165b8  ldarg.2
0x165b9  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_AppliesTo(class [System]System.Uri value)
0x165be  ldarg.1
0x165bf  ldstr    aHttpSchemasMic_17// "http://schemas.microsoft.com/idfx/keyty"...
0x165c4  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_KeyType(string value)
0x165c9  ldarg.1
0x165ca  ldarg.0
0x165cb  ldarg.1
0x165cc  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_ClientCredentials()
0x165d1  call     instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::GetCredentialsEndpointType(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x165d6  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_EndpointType(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType value)
0x165db  ldarg.1
0x165dc  ldarg.0
0x165dd  call     instance class Microsoft.Xrm.Sdk.Client.CrossRealmIssuerEndpointCollection class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CrossRealmIssuerEndpoints()
0x165e2  ldarg.1
0x165e3  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::get_HomeRealm()
0x165e8  callvirt instance var<u1> class Microsoft.Xrm.Sdk.DataCollection`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary>::get_Item(void)
0x165ed  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary value)
0x165f2  dup
0x165f3  ldarg.0
0x165f4  ldarg.1
0x165f5  call     instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::AuthenticateInternal(class Microsoft.Xrm.Sdk.Client.AuthenticationCredentials)
0x165fa  callvirt instance void Microsoft.Xrm.Sdk.Client.AuthenticationCredentials::set_SecurityTokenResponse(class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse value)
0x165ff  ret
```
