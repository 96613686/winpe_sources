# Microsoft.Crm.Authentication.Claims.MetadataParser::GetMexAddress

- ea: `0x10800`
- end: `0x10871`
- name: `Microsoft.Crm.Authentication.Claims.MetadataParser::GetMexAddress`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10580`

## callees

- `0x10800`

## string_xrefs

- `0x1082e`: `http://schemas.xmlsoap.org/ws/2004/09/mex`

## pseudocode

```c

```

## disassembly

```asm
0x10800  ldarg.0
0x10801  brtrue.s loc_1080E
0x10803  ldstr    aAddress// "address"
0x10808  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1080d  throw
0x1080e  ldarg.0
0x1080f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Xml]System.Xml.XmlElement> [System.IdentityModel]System.IdentityModel.Protocols.WSTrust.EndpointReference::get_Details()
0x10814  call     T0x2B000026
0x10819  stloc.0
0x1081a  ldloc.0
0x1081b  brfalse.s loc_1086F
0x1081d  newobj   instance void [System.Xml]System.Xml.NameTable::.ctor()
0x10822  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x10827  stloc.1
0x10828  ldloc.1
0x10829  ldstr    aWsx// "wsx"
0x1082e  ldstr    aHttpSchemasXml_1// "http://schemas.xmlsoap.org/ws/2004/09/m"...
0x10833  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x10838  ldloc.1
0x10839  ldstr    aAddr// "addr"
0x1083e  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2005/08/addressing"
0x10843  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x10848  ldloc.0
0x10849  ldstr    aWsxMetadataref// "//wsx:MetadataReference"
0x1084e  ldloc.1
0x1084f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x10854  stloc.2
0x10855  ldloc.2
0x10856  brfalse.s loc_1086F
0x10858  ldloc.2
0x10859  ldstr    aAddrAddress// "addr:Address"
0x1085e  ldloc.1
0x1085f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x10864  stloc.3
0x10865  ldloc.3
0x10866  brfalse.s loc_1086F
0x10868  ldloc.3
0x10869  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1086e  ret
0x1086f  ldnull
0x10870  ret
```
