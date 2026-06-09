# Word2003XmlFileHandler::ProcessForMailMerge

- ea: `0xa44b0`
- end: `0xa44fe`
- name: `Word2003XmlFileHandler::ProcessForMailMerge`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa44b0`

## string_xrefs

- `0xa44b0`: `http://schemas.microsoft.com/office/word/2003/wordml`
- `0xa44b6`: `http://schemas.microsoft.com/office/word/2003/auxHint`

## pseudocode

```c

```

## disassembly

```asm
0xa44b0  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/office/wor"...
0xa44b5  stloc.0
0xa44b6  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/office/wor"...
0xa44bb  stloc.1
0xa44bc  ldarg.1
0xa44bd  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa44c2  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa44c7  stloc.2
0xa44c8  ldloc.2
0xa44c9  ldstr    aW// "w"
0xa44ce  ldloc.0
0xa44cf  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa44d4  ldloc.2
0xa44d5  ldstr    aWx// "wx"
0xa44da  ldloc.1
0xa44db  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa44e0  ldarg.1
0xa44e1  ldstr    aWMailmerge// "//w:mailMerge"
0xa44e6  ldloc.2
0xa44e7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa44ec  stloc.3
0xa44ed  ldloc.3
0xa44ee  brfalse.s loc_A44FD
0xa44f0  ldloc.3
0xa44f1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xa44f6  ldloc.3
0xa44f7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xa44fc  pop
0xa44fd  ret
```
