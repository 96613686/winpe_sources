# Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::CreateBindingElements

- ea: `0x1680`
- end: `0x16cf`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::CreateBindingElements`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1600`
- `0x1680`
- `0x16d0`
- `0x1700`
- `0x1710`

## pseudocode

```c

```

## disassembly

```asm
0x1680  newobj   instance void [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection::.ctor()
0x1685  stloc.0
0x1686  ldloc.0
0x1687  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Clear()
0x168c  ldc.i4.2
0x168d  ldarg.0
0x168e  ldfld    valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_securityMode
0x1693  beq.s    loc_169E
0x1695  ldc.i4.3
0x1696  ldarg.0
0x1697  ldfld    valuetype [System.ServiceModel]System.ServiceModel.SecurityMode Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::_securityMode
0x169c  bne.un.s loc_16B0
0x169e  ldloc.0
0x169f  ldarg.0
0x16a0  ldarg.0
0x16a1  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::CreateSecurityBindingElement()
0x16a6  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::ApplyMessageSecurity(class [System.ServiceModel]System.ServiceModel.Channels.SecurityBindingElement securityBindingElement)
0x16ab  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Add(var<u1>)
0x16b0  ldloc.0
0x16b1  ldarg.0
0x16b2  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageEncodingBindingElement Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::CreateEncodingBindingElement()
0x16b7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Add(var<u1>)
0x16bc  ldloc.0
0x16bd  ldarg.0
0x16be  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.HttpTransportBindingElement Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::CreateTransportBindingElement()
0x16c3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Channels.BindingElement>::Add(var<u1>)
0x16c8  ldloc.0
0x16c9  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection [System.ServiceModel]System.ServiceModel.Channels.BindingElementCollection::Clone()
0x16ce  ret
```
