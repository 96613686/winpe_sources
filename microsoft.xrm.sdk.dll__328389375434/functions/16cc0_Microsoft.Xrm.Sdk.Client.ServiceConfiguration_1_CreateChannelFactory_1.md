# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CreateChannelFactory_1

- ea: `0x16cc0`
- end: `0x16d52`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CreateChannelFactory_1`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x16cc0`
- `0x17960`
- `0x195d0`

## string_xrefs

- `0x16cc6`: `CurrentServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x16cc0  ldarg.0
0x16cc1  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16cc6  ldstr    aCurrentservice// "CurrentServiceEndpoint"
0x16ccb  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16cd0  ldarg.0
0x16cd1  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ClaimsEnabledService()
0x16cd6  brfalse.s loc_16D2A
0x16cd8  ldarg.0
0x16cd9  ldarg.1
0x16cda  call     instance valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::GetCredentialsEndpointType(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x16cdf  stloc.1
0x16ce0  ldarg.0
0x16ce1  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x16ce6  ldloc.1
0x16ce7  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::GetIssuerEndpoint(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType credentialType)
0x16cec  stloc.2
0x16ced  ldloc.2
0x16cee  brfalse.s loc_16D2A
0x16cf0  ldsfld   object class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_lockObject
0x16cf5  stloc.3
0x16cf6  ldc.i4.0
0x16cf7  stloc.s  4
0x16cf9  ldloc.3
0x16cfa  ldloca.s 4
0x16cfc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16d01  ldarg.0
0x16d02  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16d07  ldarg.0
0x16d08  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16d0d  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x16d12  ldloc.2
0x16d13  call     class [System.ServiceModel]System.ServiceModel.Channels.CustomBinding Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::SetIssuer(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint issuerEndpoint)
0x16d18  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Binding(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x16d1d  leave.s  loc_16D2A
0x16d1f  ldloc.s  4
0x16d21  brfalse.s loc_16D29
0x16d23  ldloc.3
0x16d24  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x16d29  endfinally
0x16d2a  ldarg.0
0x16d2b  call     instance class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::CreateLocalChannelFactory()
0x16d30  stloc.0
0x16d31  ldarg.0
0x16d32  ldloc.0
0x16d33  ldarg.1
0x16d34  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::ConfigureCredentials(class [System.ServiceModel]System.ServiceModel.ChannelFactory, class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x16d39  ldloc.0
0x16d3a  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Credentials()
0x16d3f  ldarg.1
0x16d40  brtrue.s loc_16D45
0x16d42  ldc.i4.0
0x16d43  br.s     loc_16D4B
0x16d45  ldarg.1
0x16d46  callvirt instance bool [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_SupportInteractive()
0x16d4b  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::set_SupportInteractive(bool)
0x16d50  ldloc.0
0x16d51  ret
```
