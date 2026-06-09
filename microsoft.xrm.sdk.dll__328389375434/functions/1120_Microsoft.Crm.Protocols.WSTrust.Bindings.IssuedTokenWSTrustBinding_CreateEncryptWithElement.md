# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateEncryptWithElement

- ea: `0x1120`
- end: `0x1191`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateEncryptWithElement`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf30`

## callees

- `0x1120`
- `0x1810`

## string_xrefs

- `0x114e`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512`
- `0x1173`: `http://schemas.xmlsoap.org/ws/2005/02/trust`

## pseudocode

```c

```

## disassembly

```asm
0x1120  ldarg.1
0x1121  brtrue.s loc_112E
0x1123  ldstr    aEncryptionalgo// "encryptionAlgorithm"
0x1128  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x112d  throw
0x112e  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1133  stloc.0
0x1134  ldnull
0x1135  stloc.1
0x1136  ldarg.0
0x1137  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x113c  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrust13()
0x1141  bne.un.s loc_115B
0x1143  ldloc.0
0x1144  ldstr    aTrust// "trust"
0x1149  ldstr    aEncryptwith// "EncryptWith"
0x114e  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x1153  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x1158  stloc.1
0x1159  br.s     loc_117E
0x115b  ldarg.0
0x115c  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x1161  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrustFeb2005()
0x1166  bne.un.s loc_117E
0x1168  ldloc.0
0x1169  ldstr    aT// "t"
0x116e  ldstr    aEncryptwith// "EncryptWith"
0x1173  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/02/t"...
0x1178  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x117d  stloc.1
0x117e  ldloc.1
0x117f  brfalse.s loc_118F
0x1181  ldloc.1
0x1182  ldloc.0
0x1183  ldarg.1
0x1184  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x1189  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x118e  pop
0x118f  ldloc.1
0x1190  ret
```
