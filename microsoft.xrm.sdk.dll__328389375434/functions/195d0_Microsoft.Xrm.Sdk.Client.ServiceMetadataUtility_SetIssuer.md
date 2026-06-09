# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::SetIssuer

- ea: `0x195d0`
- end: `0x1961d`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::SetIssuer`
- size: `77`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x16ae0`
- `0x16bb0`
- `0x16c30`
- `0x16cc0`

## callees

- `0x17850`
- `0x17870`
- `0x17890`
- `0x194b0`
- `0x195d0`

## pseudocode

```c

```

## disassembly

```asm
0x195d0  ldarg.0
0x195d1  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x195d6  dup
0x195d7  callvirt T0x2B000069
0x195dc  call     class [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuedTokenParameters(class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement securityElement)
0x195e1  stloc.0
0x195e2  ldloc.0
0x195e3  brfalse.s loc_19617
0x195e5  ldloc.0
0x195e6  ldarg.1
0x195e7  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerAddress()
0x195ec  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::set_IssuerAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x195f1  ldloc.0
0x195f2  ldarg.1
0x195f3  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerBinding()
0x195f8  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::set_IssuerBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x195fd  ldarg.1
0x195fe  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerMetadataAddress()
0x19603  ldnull
0x19604  call     bool [System.ServiceModel]System.ServiceModel.EndpointAddress::op_Inequality(class [System.ServiceModel]System.ServiceModel.EndpointAddress, class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x19609  brfalse.s loc_19617
0x1960b  ldloc.0
0x1960c  ldarg.1
0x1960d  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Xrm.Sdk.Client.IssuerEndpoint::get_IssuerMetadataAddress()
0x19612  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::set_IssuerMetadataAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x19617  newobj   instance void [System.ServiceModel]System.ServiceModel.Channels.CustomBinding::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>)
0x1961c  ret
```
