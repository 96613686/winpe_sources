# Word2003XmlFileHandler::RemoveMailMergeNode

- ea: `0xa3fd0`
- end: `0xa401e`
- name: `Word2003XmlFileHandler::RemoveMailMergeNode`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa3fd0`

## string_xrefs

- `0xa3fd0`: `http://schemas.microsoft.com/office/word/2003/wordml`
- `0xa3fd6`: `http://schemas.microsoft.com/office/word/2003/auxHint`

## pseudocode

```c

```

## disassembly

```asm
0xa3fd0  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/office/wor"...
0xa3fd5  stloc.0
0xa3fd6  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/office/wor"...
0xa3fdb  stloc.1
0xa3fdc  ldarg.1
0xa3fdd  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa3fe2  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa3fe7  stloc.2
0xa3fe8  ldloc.2
0xa3fe9  ldstr    aW// "w"
0xa3fee  ldloc.0
0xa3fef  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa3ff4  ldloc.2
0xa3ff5  ldstr    aWx// "wx"
0xa3ffa  ldloc.1
0xa3ffb  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4000  ldarg.1
0xa4001  ldstr    aWMailmerge// "//w:mailMerge"
0xa4006  ldloc.2
0xa4007  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa400c  stloc.3
0xa400d  ldloc.3
0xa400e  brfalse.s loc_A401D
0xa4010  ldloc.3
0xa4011  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xa4016  ldloc.3
0xa4017  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xa401c  pop
0xa401d  ret
```
