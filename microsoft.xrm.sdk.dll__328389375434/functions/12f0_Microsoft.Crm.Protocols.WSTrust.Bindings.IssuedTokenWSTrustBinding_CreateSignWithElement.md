# Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateSignWithElement

- ea: `0x12f0`
- end: `0x1361`
- name: `Microsoft.Crm.Protocols.WSTrust.Bindings.IssuedTokenWSTrustBinding::CreateSignWithElement`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf30`

## callees

- `0x12f0`
- `0x1810`

## string_xrefs

- `0x131e`: `http://docs.oasis-open.org/ws-sx/ws-trust/200512`
- `0x1343`: `http://schemas.xmlsoap.org/ws/2005/02/trust`

## pseudocode

```c

```

## disassembly

```asm
0x12f0  ldarg.1
0x12f1  brtrue.s loc_12FE
0x12f3  ldstr    aSignaturealgor// "signatureAlgorithm"
0x12f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12fd  throw
0x12fe  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x1303  stloc.0
0x1304  ldnull
0x1305  stloc.1
0x1306  ldarg.0
0x1307  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x130c  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrust13()
0x1311  bne.un.s loc_132B
0x1313  ldloc.0
0x1314  ldstr    aTrust// "trust"
0x1319  ldstr    aSignaturealgor_0// "SignatureAlgorithm"
0x131e  ldstr    aHttpDocsOasisO// "http://docs.oasis-open.org/ws-sx/ws-tru"...
0x1323  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x1328  stloc.1
0x1329  br.s     loc_134E
0x132b  ldarg.0
0x132c  call     instance class [System.ServiceModel]System.ServiceModel.Security.TrustVersion Microsoft.Crm.Protocols.WSTrust.Bindings.WSTrustBindingBase::get_TrustVersion()
0x1331  call     class [System.ServiceModel]System.ServiceModel.Security.TrustVersion [System.ServiceModel]System.ServiceModel.Security.TrustVersion::get_WSTrustFeb2005()
0x1336  bne.un.s loc_134E
0x1338  ldloc.0
0x1339  ldstr    aT// "t"
0x133e  ldstr    aSignaturealgor_0// "SignatureAlgorithm"
0x1343  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/ws/2005/02/t"...
0x1348  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string, string)
0x134d  stloc.1
0x134e  ldloc.1
0x134f  brfalse.s loc_135F
0x1351  ldloc.1
0x1352  ldloc.0
0x1353  ldarg.1
0x1354  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x1359  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x135e  pop
0x135f  ldloc.1
0x1360  ret
```
