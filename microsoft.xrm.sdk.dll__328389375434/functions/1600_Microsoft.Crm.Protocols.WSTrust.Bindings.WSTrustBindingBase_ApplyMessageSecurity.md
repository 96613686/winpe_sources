# Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ApplyMessageSecurity

- ea: `0x1600`
- end: `0x1662`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ApplyMessageSecurity`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1680`

## callees

- `0x1600`

## string_xrefs

- `0x1603`: `securityBindingElement`

## pseudocode

```c

```

## disassembly

```asm
0x1600  ldarg.1
0x1601  brtrue.s loc_160E
0x1603  ldstr    aSecuritybindin// "securityBindingElement"
0x1608  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x160d  throw
0x160e  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrustFeb2005()
0x1613  ldarg.0
0x1614  ldfld    class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_trustVersion
0x1619  bne.un.s loc_1628
0x161b  ldarg.1
0x161c  call     class [System.ServiceModel]System.ServiceModel.MessageSecurityVersion [System.ServiceModel]System.ServiceModel.MessageSecurityVersion::get_WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10()
0x1621  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::set_MessageSecurityVersion(class [System.ServiceModel]System.ServiceModel.MessageSecurityVersion)
0x1626  br.s     loc_1633
0x1628  ldarg.1
0x1629  call     class [System.ServiceModel]System.ServiceModel.MessageSecurityVersion [System.ServiceModel]System.ServiceModel.MessageSecurityVersion::get_WSSecurity11WSTrust13WSSecureConversation13WSSecurityPolicy12BasicSecurityProfile10()
0x162e  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::set_MessageSecurityVersion(class [System.ServiceModel]System.ServiceModel.MessageSecurityVersion)
0x1633  ldarg.0
0x1634  ldfld    bool Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_enableRsaProofKeys
0x1639  brfalse.s loc_1660
0x163b  newobj   instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.RsaSecurityTokenParameters::.ctor()
0x1640  dup
0x1641  ldc.i4.1
0x1642  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters::set_InclusionMode(valuetype [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode)
0x1647  dup
0x1648  ldc.i4.0
0x1649  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters::set_RequireDerivedKeys(bool)
0x164e  stloc.0
0x164f  ldarg.1
0x1650  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement::get_OptionalEndpointSupportingTokenParameters()
0x1655  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters> [System.ServiceModel]System.ServiceModel.Security.Tokens.SupportingTokenParameters::get_Endorsing()
0x165a  ldloc.0
0x165b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Security.Tokens.SecurityTokenParameters>::Add(var<u1>)
0x1660  ldarg.1
0x1661  ret
```
