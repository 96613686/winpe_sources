# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CreateChannelFactory_0

- ea: `0x16c30`
- end: `0x16cc0`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CreateChannelFactory_0`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x16c30`
- `0x17960`
- `0x195d0`

## string_xrefs

- `0x16c36`: `CurrentServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x16c30  ldarg.0
0x16c31  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16c36  ldstr    aCurrentservice// "CurrentServiceEndpoint"
0x16c3b  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16c40  ldarg.0
0x16c41  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ClaimsEnabledService()
0x16c46  brfalse.s loc_16CAD
0x16c48  ldnull
0x16c49  stloc.0
0x16c4a  ldarg.1
0x16c4b  ldc.i4.1
0x16c4c  bne.un.s loc_16C63
0x16c4e  ldarg.0
0x16c4f  call     instance valuetype Microsoft.Xrm.Sdk.Client.AuthenticationProviderType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_AuthenticationType()
0x16c54  ldc.i4.4
0x16c55  beq.s    loc_16C5F
0x16c57  ldarg.0
0x16c58  ldfld    valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_tokenEndpointType
0x16c5d  br.s     loc_16C60
0x16c5f  ldc.i4.3
0x16c60  stloc.1
0x16c61  br.s     loc_16C65
0x16c63  ldc.i4.2
0x16c64  stloc.1
0x16c65  ldarg.0
0x16c66  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x16c6b  ldloc.1
0x16c6c  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::GetIssuerEndpoint(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType credentialType)
0x16c71  stloc.0
0x16c72  ldloc.0
0x16c73  brfalse.s loc_16CAD
0x16c75  ldsfld   object class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_lockObject
0x16c7a  stloc.2
0x16c7b  ldc.i4.0
0x16c7c  stloc.3
0x16c7d  ldloc.2
0x16c7e  ldloca.s 3
0x16c80  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16c85  ldarg.0
0x16c86  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16c8b  ldarg.0
0x16c8c  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16c91  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x16c96  ldloc.0
0x16c97  call     class [System.ServiceModel]System.ServiceModel.Channels.CustomBinding Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::SetIssuer(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint issuerEndpoint)
0x16c9c  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Binding(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x16ca1  leave.s  loc_16CAD
0x16ca3  ldloc.3
0x16ca4  brfalse.s loc_16CAC
0x16ca6  ldloc.2
0x16ca7  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x16cac  endfinally
0x16cad  ldarg.0
0x16cae  call     instance class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::CreateLocalChannelFactory()
0x16cb3  dup
0x16cb4  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Credentials()
0x16cb9  ldc.i4.0
0x16cba  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::set_SupportInteractive(bool)
0x16cbf  ret
```
