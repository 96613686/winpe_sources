# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateCanonicalizationAlgorithmElement

- ea: `0x1020`
- end: `0x1091`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateCanonicalizationAlgorithmElement`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf30`

## callees

- `0x1020`
- `0x1810`

## string_xrefs

- `0x104e`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512`
- `0x1073`: `http://schemas.xmlsoap.org/ws/2005/02/trust`

## pseudocode

```c

```

## disassembly

```asm
0x1020  ldarg.1
0x1021  brtrue.s loc_102E
0x1023  ldstr    aCanonicalizati// "canonicalizationAlgorithm"
0x1028  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x102d  throw
0x102e  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1033  stloc.0
0x1034  ldnull
0x1035  stloc.1
0x1036  ldarg.0
0x1037  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x103c  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrust13()
0x1041  bne.un.s loc_105B
0x1043  ldloc.0
0x1044  ldstr    aTrust// "trust"
0x1049  ldstr    aCanonicalizati_0// "CanonicalizationAlgorithm"
0x104e  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x1053  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x1058  stloc.1
0x1059  br.s     loc_107E
0x105b  ldarg.0
0x105c  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x1061  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrustFeb2005()
0x1066  bne.un.s loc_107E
0x1068  ldloc.0
0x1069  ldstr    aT// "t"
0x106e  ldstr    aCanonicalizati_0// "CanonicalizationAlgorithm"
0x1073  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/02/t"...
0x1078  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x107d  stloc.1
0x107e  ldloc.1
0x107f  brfalse.s loc_108F
0x1081  ldloc.1
0x1082  ldloc.0
0x1083  ldarg.1
0x1084  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x1089  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x108e  pop
0x108f  ldloc.1
0x1090  ret
```
