# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuer

- ea: `0x19410`
- end: `0x19455`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuer`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x16ac0`
- `0x19390`

## callees

- `0x17860`
- `0x17880`
- `0x178a0`
- `0x178b0`
- `0x19410`
- `0x194b0`

## pseudocode

```c

```

## disassembly

```asm
0x19410  ldarg.0
0x19411  brtrue.s loc_19415
0x19413  ldnull
0x19414  ret
0x19415  ldarg.0
0x19416  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.Binding::CreateBindingElements()
0x1941b  callvirt T0x2B000069
0x19420  call     class [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuedTokenParameters(class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement securityElement)
0x19425  stloc.0
0x19426  ldloc.0
0x19427  brfalse.s loc_19453
0x19429  newobj   instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::.ctor()
0x1942e  dup
0x1942f  ldloc.0
0x19430  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_IssuerAddress()
0x19435  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x1943a  dup
0x1943b  ldloc.0
0x1943c  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_IssuerBinding()
0x19441  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding value)
0x19446  dup
0x19447  ldloc.0
0x19448  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters::get_IssuerMetadataAddress()
0x1944d  callvirt instance void Microsoft.Xrm.Sdk.Client.IssuerEndpoint::set_IssuerMetadataAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x19452  ret
0x19453  ldnull
0x19454  ret
```
