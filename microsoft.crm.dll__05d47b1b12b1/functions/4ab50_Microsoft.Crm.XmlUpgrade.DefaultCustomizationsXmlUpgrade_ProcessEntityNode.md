# Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessEntityNode

- ea: `0x4ab50`
- end: `0x4ab86`
- name: `Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade::ProcessEntityNode`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4ab10`

## callees

- `0x4ace0`
- `0x509f0`

## string_xrefs

- `0x4ab6a`: `ImportExportXml/Entities/Entity`

## pseudocode

```c

```

## disassembly

```asm
0x4ab50  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x4ab55  stloc.0
0x4ab56  ldloc.0
0x4ab57  ldarg.0
0x4ab58  stfld    class Microsoft.Crm.XmlUpgrade.DefaultCustomizationsXmlUpgrade <>c__DisplayClass4_0::<>4__this
0x4ab5d  ldloc.0
0x4ab5e  ldarg.1
0x4ab5f  stfld    class [System.Xml]System.Xml.XmlDocument <>c__DisplayClass4_0::xmlDoc
0x4ab64  ldloc.0
0x4ab65  ldfld    class [System.Xml]System.Xml.XmlDocument <>c__DisplayClass4_0::xmlDoc
0x4ab6a  ldstr    aImportexportxm_2// "ImportExportXml/Entities/Entity"
0x4ab6f  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x4ab74  ldloc.0
0x4ab75  ldftn    instance void <>c__DisplayClass4_0::<ProcessEntityNode>b__0(class [System.Xml]System.Xml.XmlNode entityNode)
0x4ab7b  newobj   instance void class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode>::.ctor(object, native int)
0x4ab80  call     void Microsoft.Crm.XmlUpgrade.ParserExtensions::ForEach(class [System.Xml]System.Xml.XmlNodeList xmlNodeList, class [mscorlib]System.Action`1<class [System.Xml]System.Xml.XmlNode> action)
0x4ab85  ret
```
