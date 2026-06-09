# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CreateChannelFactory

- ea: `0x16bb0`
- end: `0x16c25`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CreateChannelFactory`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x16bb0`
- `0x17960`
- `0x195d0`

## string_xrefs

- `0x16bb6`: `CurrentServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x16bb0  ldarg.0
0x16bb1  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16bb6  ldstr    aCurrentservice// "CurrentServiceEndpoint"
0x16bbb  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16bc0  ldarg.0
0x16bc1  call     instance bool class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_ClaimsEnabledService()
0x16bc6  brfalse.s loc_16C12
0x16bc8  ldnull
0x16bc9  stloc.0
0x16bca  ldarg.0
0x16bcb  call     instance class Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_IssuerEndpoints()
0x16bd0  ldarg.1
0x16bd1  callvirt instance class Microsoft.Xrm.Sdk.Client.IssuerEndpoint Microsoft.Xrm.Sdk.Client.IssuerEndpointDictionary::GetIssuerEndpoint(valuetype Microsoft.Xrm.Sdk.Client.TokenServiceCredentialType credentialType)
0x16bd6  stloc.0
0x16bd7  ldloc.0
0x16bd8  brfalse.s loc_16C12
0x16bda  ldsfld   object class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_lockObject
0x16bdf  stloc.1
0x16be0  ldc.i4.0
0x16be1  stloc.2
0x16be2  ldloc.1
0x16be3  ldloca.s 2
0x16be5  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x16bea  ldarg.0
0x16beb  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16bf0  ldarg.0
0x16bf1  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x16bf6  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x16bfb  ldloc.0
0x16bfc  call     class [System.ServiceModel]System.ServiceModel.Channels.CustomBinding Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::SetIssuer(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding, class Microsoft.Xrm.Sdk.Client.IssuerEndpoint issuerEndpoint)
0x16c01  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Binding(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x16c06  leave.s  loc_16C12
0x16c08  ldloc.2
0x16c09  brfalse.s loc_16C11
0x16c0b  ldloc.1
0x16c0c  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x16c11  endfinally
0x16c12  ldarg.0
0x16c13  call     instance class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::CreateLocalChannelFactory()
0x16c18  dup
0x16c19  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Credentials()
0x16c1e  ldc.i4.0
0x16c1f  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::set_SupportInteractive(bool)
0x16c24  ret
```
