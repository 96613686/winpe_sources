# Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetServiceEndpointsTable

- ea: `0x7d320`
- end: `0x7d403`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::GetServiceEndpointsTable`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x66e00`

## callees

- `0x4bf70`
- `0x7d320`
- `0x80060`

## string_xrefs

- `0x7d35a`: `ServiceEndpointId`
- `0x7d386`: `ServiceEndpointId`
- `0x7d331`: `ServiceEndpoints/ServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x7d320  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x7d325  stloc.0
0x7d326  ldarg.0
0x7d327  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::importDocument
0x7d32c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x7d331  ldstr    aServiceendpoin_5// "ServiceEndpoints/ServiceEndpoint"
0x7d336  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7d33b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7d340  stloc.1
0x7d341  br       loc_7D3E0
0x7d346  ldloc.1
0x7d347  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7d34c  castclass [System.Xml]System.Xml.XmlNode
0x7d351  stloc.2
0x7d352  ldloca.s 3
0x7d354  ldloc.2
0x7d355  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7d35a  ldstr    aServiceendpoin_2// "ServiceEndpointId"
0x7d35f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7d364  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7d369  call     instance void [mscorlib]System.Guid::.ctor(string)
0x7d36e  ldloc.2
0x7d36f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7d374  ldstr    aName_1// "Name"
0x7d379  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7d37e  stloc.s  4
0x7d380  ldloc.2
0x7d381  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7d386  ldstr    aServiceendpoin_2// "ServiceEndpointId"
0x7d38b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7d390  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7d395  stloc.s  5
0x7d397  ldsfld   string [mscorlib]System.String::Empty
0x7d39c  stloc.s  6
0x7d39e  ldloc.s  4
0x7d3a0  brfalse.s loc_7D3AB
0x7d3a2  ldloc.s  4
0x7d3a4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7d3a9  stloc.s  5
0x7d3ab  ldloc.2
0x7d3ac  ldstr    aDescription_0// "Description"
0x7d3b1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7d3b6  stloc.s  7
0x7d3b8  ldloc.s  7
0x7d3ba  brfalse.s loc_7D3C5
0x7d3bc  ldloc.s  7
0x7d3be  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7d3c3  stloc.s  6
0x7d3c5  ldloc.s  5
0x7d3c7  ldloc.s  6
0x7d3c9  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportServiceEndpointDescription::.ctor(string displayName, string description)
0x7d3ce  stloc.s  8
0x7d3d0  ldloc.0
0x7d3d1  ldc.i4.s 0x5F
0x7d3d3  ldloc.3
0x7d3d4  box      [mscorlib]System.Guid
0x7d3d9  ldloc.s  8
0x7d3db  call     void Microsoft.Crm.Tools.ImportExportPublish.ExtendHashtable::CheckAndAddKey(class [mscorlib]System.Collections.Hashtable htObj, int32 componentType, object key, object value)
0x7d3e0  ldloc.1
0x7d3e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7d3e6  brtrue   loc_7D346
0x7d3eb  leave.s  loc_7D401
0x7d3ed  ldloc.1
0x7d3ee  isinst   [mscorlib]System.IDisposable
0x7d3f3  stloc.s  9
0x7d3f5  ldloc.s  9
0x7d3f7  brfalse.s loc_7D400
0x7d3f9  ldloc.s  9
0x7d3fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d400  endfinally
0x7d401  ldloc.0
0x7d402  ret
```
