# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::SetAuthenticationConfiguration

- ea: `0x16900`
- end: `0x169f6`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::SetAuthenticationConfiguration`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15c60`
- `0x16900`
- `0x183f0`
- `0x18410`
- `0x18430`
- `0x184b0`
- `0x19270`
- `0x19390`

## pseudocode

```c

```

## disassembly

```asm
0x16900  ldarg.0
0x16901  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16906  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x1690b  brtrue.s loc_1690E
0x1690d  ret
0x1690e  ldarg.0
0x1690f  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16914  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x16919  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x1691e  callvirt T0x2B00005C
0x16923  stloc.0
0x16924  ldloc.0
0x16925  brfalse  loc_169F5
0x1692a  ldloc.0
0x1692b  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x16930  ldstr    aAuthentication_0// "AuthenticationType"
0x16935  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1693a  brfalse  loc_169F5
0x1693f  ldloc.0
0x16940  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x16945  ldstr    aAuthentication_0// "AuthenticationType"
0x1694a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1694f  stloc.1
0x16950  ldloc.1
0x16951  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16956  brtrue   loc_169F5
0x1695b  ldloc.1
0x1695c  ldloca.s 2
0x1695e  call     T0x2B00005E
0x16963  brfalse  loc_169F5
0x16968  ldloc.2
0x16969  ldc.i4.2
0x1696a  beq.s    loc_169C8
0x1696c  ldloc.2
0x1696d  ldc.i4.4
0x1696e  bne.un.s loc_169E8
0x16970  ldarg.0
0x16971  ldloc.0
0x16972  newobj   instance void Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x16977  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_PolicyConfiguration(class Microsoft.Xrm.Sdk.Client.PolicyConfiguration)
0x1697c  ldarg.0
0x1697d  call     instance class Microsoft.Xrm.Sdk.Client.PolicyConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_PolicyConfiguration()
0x16982  castclass Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration
0x16987  callvirt instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x1698c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Values()
0x16991  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::GetEnumerator()
0x16996  stloc.3
0x16997  br.s     loc_169AF
0x16999  ldloca.s 3
0x1699b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Current()
0x169a0  stloc.s  4
0x169a2  ldarg.0
0x169a3  ldloc.s  4
0x169a5  call     class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveLiveIdIssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration identityProviderTrustConfiguration)
0x169aa  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary)
0x169af  ldloca.s 3
0x169b1  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::MoveNext()
0x169b6  brtrue.s loc_16999
0x169b8  leave.s  loc_169F4
0x169ba  ldloca.s 3
0x169bc  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>
0x169c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x169c7  endfinally
0x169c8  ldarg.0
0x169c9  ldc.i4.2
0x169ca  ldarg.0
0x169cb  call     instance class Microsoft.Xrm.Sdk.Client.ServiceEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ServiceEndpoints()
0x169d0  ldc.i4.1
0x169d1  call     class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::RetrieveIssuerEndpoints(valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType authenticationProviderType, class Microsoft.Xrm.Sdk.Client.ServiceEndpointDictionary endpoints, bool queryMetadata)
0x169d6  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_IssuerEndpoints(class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary)
0x169db  ldarg.0
0x169dc  ldloc.0
0x169dd  newobj   instance void Microsoft.Xrm.Sdk.Client.ClaimsPolicyConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x169e2  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_PolicyConfiguration(class Microsoft.Xrm.Sdk.Client.PolicyConfiguration)
0x169e7  ret
0x169e8  ldarg.0
0x169e9  ldloc.0
0x169ea  newobj   instance void Microsoft.Xrm.Sdk.Client.WindowsPolicyConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x169ef  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::set_PolicyConfiguration(class Microsoft.Xrm.Sdk.Client.PolicyConfiguration)
0x169f4  ret
0x169f5  ret
```
