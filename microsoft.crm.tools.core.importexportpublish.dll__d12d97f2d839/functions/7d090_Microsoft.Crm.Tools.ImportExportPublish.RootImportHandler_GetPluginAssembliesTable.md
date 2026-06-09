# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetPluginAssembliesTable

- ea: `0x7d090`
- end: `0x7d18e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetPluginAssembliesTable`
- size: `254`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x66e00`

## callees

- `0x4be50`
- `0x7d090`
- `0x80060`

## string_xrefs

- `0x7d117`: `PluginAssemblyId`
- `0x7d129`: `PluginAssemblyId`
- `0x7d14b`: `PluginAssemblyId`
- `0x7d140`: `, PluginAssemblyId=`
- `0x7d0a1`: `SolutionPluginAssemblies/PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x7d090  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x7d095  stloc.0
0x7d096  ldarg.0
0x7d097  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7d09c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7d0a1  ldstr    aSolutionplugin_0// "SolutionPluginAssemblies/PluginAssembly"
0x7d0a6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7d0ab  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7d0b0  stloc.1
0x7d0b1  br       loc_7D16B
0x7d0b6  ldloc.1
0x7d0b7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7d0bc  castclass [System.Xml]System.Xml.XmlNode
0x7d0c1  stloc.2
0x7d0c2  ldloc.2
0x7d0c3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7d0c8  ldstr    aFullname// "FullName"
0x7d0cd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7d0d2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7d0d7  stloc.3
0x7d0d8  ldloc.3
0x7d0d9  ldc.i4.0
0x7d0da  ldloc.3
0x7d0db  ldc.i4.s 0x2C
0x7d0dd  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x7d0e2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x7d0e7  ldsfld   string [mscorlib]System.String::Empty
0x7d0ec  stloc.s  4
0x7d0ee  ldloc.2
0x7d0ef  ldstr    aDescription_0// "Description"
0x7d0f4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7d0f9  stloc.s  5
0x7d0fb  ldloc.s  5
0x7d0fd  brfalse.s loc_7D108
0x7d0ff  ldloc.s  5
0x7d101  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7d106  stloc.s  4
0x7d108  ldloc.s  4
0x7d10a  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyDescription::.ctor(string displayName, string description)
0x7d10f  stloc.s  6
0x7d111  ldloc.2
0x7d112  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7d117  ldstr    aPluginassembly// "PluginAssemblyId"
0x7d11c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7d121  brfalse.s loc_7D160
0x7d123  ldloc.2
0x7d124  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7d129  ldstr    aPluginassembly// "PluginAssemblyId"
0x7d12e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7d133  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7d138  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d13d  brtrue.s loc_7D160
0x7d13f  ldloc.3
0x7d140  ldstr    aPluginassembly_4// ", PluginAssemblyId="
0x7d145  ldloc.2
0x7d146  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7d14b  ldstr    aPluginassembly// "PluginAssemblyId"
0x7d150  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7d155  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7d15a  call     string [mscorlib]System.String::Concat(string, string, string)
0x7d15f  stloc.3
0x7d160  ldloc.0
0x7d161  ldc.i4.s 0x5B
0x7d163  ldloc.3
0x7d164  ldloc.s  6
0x7d166  call     void Microsoft.Crm.Tools.ImportExportPublish.ExtendHashtable::CheckAndAddKey(class [mscorlib]System.Collections.Hashtable htObj, int32 componentType, object key, object value)
0x7d16b  ldloc.1
0x7d16c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7d171  brtrue   loc_7D0B6
0x7d176  leave.s  loc_7D18C
0x7d178  ldloc.1
0x7d179  isinst   [mscorlib]System.IDisposable
0x7d17e  stloc.s  7
0x7d180  ldloc.s  7
0x7d182  brfalse.s loc_7D18B
0x7d184  ldloc.s  7
0x7d186  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d18b  endfinally
0x7d18c  ldloc.0
0x7d18d  ret
```
