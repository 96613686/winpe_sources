# Word2007XmlFileHandler::RemoveMailMergeNode

- ea: `0xa4520`
- end: `0xa4584`
- name: `Word2007XmlFileHandler::RemoveMailMergeNode`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa4520`

## string_xrefs

- `0xa4520`: `http://schemas.microsoft.com/office/2006/xmlPackage`
- `0xa4526`: `http://schemas.openxmlformats.org/wordprocessingml/2006/main`
- `0xa452c`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships`

## pseudocode

```c

```

## disassembly

```asm
0xa4520  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/office/200"...
0xa4525  stloc.0
0xa4526  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/wordp"...
0xa452b  stloc.1
0xa452c  ldstr    aHttpSchemasOpe_0// "http://schemas.openxmlformats.org/offic"...
0xa4531  stloc.2
0xa4532  ldarg.1
0xa4533  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa4538  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa453d  stloc.3
0xa453e  ldloc.3
0xa453f  ldstr    aPkg// "pkg"
0xa4544  ldloc.0
0xa4545  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa454a  ldloc.3
0xa454b  ldstr    aW// "w"
0xa4550  ldloc.1
0xa4551  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4556  ldloc.3
0xa4557  ldstr    aR// "r"
0xa455c  ldloc.2
0xa455d  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4562  ldarg.1
0xa4563  ldstr    aWMailmerge// "//w:mailMerge"
0xa4568  ldloc.3
0xa4569  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa456e  stloc.s  4
0xa4570  ldloc.s  4
0xa4572  brfalse.s loc_A4583
0xa4574  ldloc.s  4
0xa4576  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0xa457b  ldloc.s  4
0xa457d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xa4582  pop
0xa4583  ret
```
