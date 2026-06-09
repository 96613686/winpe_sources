# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateEncryptionAlgorithmElement

- ea: `0x10a0`
- end: `0x1111`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateEncryptionAlgorithmElement`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf30`

## callees

- `0x10a0`
- `0x1810`

## string_xrefs

- `0x10ce`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512`
- `0x10f3`: `http://schemas.xmlsoap.org/ws/2005/02/trust`

## pseudocode

```c

```

## disassembly

```asm
0x10a0  ldarg.1
0x10a1  brtrue.s loc_10AE
0x10a3  ldstr    aEncryptionalgo// "encryptionAlgorithm"
0x10a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10ad  throw
0x10ae  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x10b3  stloc.0
0x10b4  ldnull
0x10b5  stloc.1
0x10b6  ldarg.0
0x10b7  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x10bc  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrust13()
0x10c1  bne.un.s loc_10DB
0x10c3  ldloc.0
0x10c4  ldstr    aTrust// "trust"
0x10c9  ldstr    aEncryptionalgo_0// "EncryptionAlgorithm"
0x10ce  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x10d3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x10d8  stloc.1
0x10d9  br.s     loc_10FE
0x10db  ldarg.0
0x10dc  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x10e1  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrustFeb2005()
0x10e6  bne.un.s loc_10FE
0x10e8  ldloc.0
0x10e9  ldstr    aT// "t"
0x10ee  ldstr    aEncryptionalgo_0// "EncryptionAlgorithm"
0x10f3  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/02/t"...
0x10f8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x10fd  stloc.1
0x10fe  ldloc.1
0x10ff  brfalse.s loc_110F
0x1101  ldloc.1
0x1102  ldloc.0
0x1103  ldarg.1
0x1104  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x1109  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x110e  pop
0x110f  ldloc.1
0x1110  ret
```
