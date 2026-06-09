# Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuedTokenParameters

- ea: `0x194b0`
- end: `0x195c1`
- name: `Microsoft.Xrm.Sdk.Client.ServiceMetadataUtility::GetIssuedTokenParameters`
- size: `273`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19090`
- `0x19410`
- `0x195d0`

## callees

- `0x194b0`

## pseudocode

```c

```

## disassembly

```asm
0x194b0  ldarg.0
0x194b1  brfalse  loc_195BF
0x194b6  ldarg.0
0x194b7  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x194bc  brfalse  loc_195BF
0x194c1  ldarg.0
0x194c2  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x194c7  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x194cc  brfalse  loc_19588
0x194d1  ldarg.0
0x194d2  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x194d7  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x194dc  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Count()
0x194e1  ldc.i4.0
0x194e2  ble      loc_19588
0x194e7  ldarg.0
0x194e8  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x194ed  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x194f2  ldc.i4.0
0x194f3  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Item(!!T0)
0x194f8  isinst   [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters
0x194fd  stloc.0
0x194fe  ldloc.0
0x194ff  brfalse.s loc_19503
0x19501  ldloc.0
0x19502  ret
0x19503  ldarg.0
0x19504  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x19509  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x1950e  ldc.i4.0
0x1950f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Item(!!T0)
0x19514  isinst   [System.ServiceModel]System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters
0x19519  stloc.1
0x1951a  ldloc.1
0x1951b  brfalse  loc_195BF
0x19520  ldloc.1
0x19521  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement [System.ServiceModel]System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters::get_BootstrapSecurityBindingElement()
0x19526  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x1952b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x19530  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Count()
0x19535  ldc.i4.0
0x19536  ble.s    loc_19554
0x19538  ldloc.1
0x19539  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement [System.ServiceModel]System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters::get_BootstrapSecurityBindingElement()
0x1953e  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x19543  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x19548  ldc.i4.0
0x19549  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Item(!!T0)
0x1954e  isinst   [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters
0x19553  ret
0x19554  ldloc.1
0x19555  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement [System.ServiceModel]System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters::get_BootstrapSecurityBindingElement()
0x1955a  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x1955f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Signed()
0x19564  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Count()
0x19569  ldc.i4.0
0x1956a  ble.s    loc_195BF
0x1956c  ldloc.1
0x1956d  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement [System.ServiceModel]System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters::get_BootstrapSecurityBindingElement()
0x19572  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x19577  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Signed()
0x1957c  ldc.i4.0
0x1957d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Item(!!T0)
0x19582  isinst   [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters
0x19587  ret
0x19588  ldarg.0
0x19589  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x1958e  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Signed()
0x19593  brfalse.s loc_195BF
0x19595  ldarg.0
0x19596  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x1959b  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Signed()
0x195a0  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Count()
0x195a5  ldc.i4.0
0x195a6  ble.s    loc_195BF
0x195a8  ldarg.0
0x195a9  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_EndpointSupportingTokenParameters()
0x195ae  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Signed()
0x195b3  ldc.i4.0
0x195b4  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::get_Item(!!T0)
0x195b9  isinst   [System.ServiceModel]System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters
0x195be  ret
0x195bf  ldnull
0x195c0  ret
```
