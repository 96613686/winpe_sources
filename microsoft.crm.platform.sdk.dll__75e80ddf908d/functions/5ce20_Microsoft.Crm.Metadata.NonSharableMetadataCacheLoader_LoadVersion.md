# Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadVersion

- ea: `0x5ce20`
- end: `0x5ceb5`
- name: `Microsoft.Crm.Metadata.NonSharableMetadataCacheLoader::LoadVersion`
- size: `149`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x5c6f0`

## callees

- `0x523d0`
- `0x52880`
- `0x5ce20`

## string_xrefs

- `0x5ce57`: `Version tag for Metadata expected but not found. This is not an issue during upgrade or setup`
- `0x5ce98`: `MetadataXml cannot have more than one /metadata/version xml nodes.`

## pseudocode

```c

```

## disassembly

```asm
0x5ce20  ldstr    aLoadversion// "LoadVersion"
0x5ce25  ldarg.2
0x5ce26  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5ce2b  dup
0x5ce2c  starg.s  2
0x5ce2e  stloc.0
0x5ce2f  ldarg.3
0x5ce30  ldstr    aMetadataVersio// "/metadata/version"
0x5ce35  callvirt instance class [System.Xml]System.Xml.XPath.XPathNodeIterator [System.Xml]System.Xml.XPath.XPathNavigator::Select(string)
0x5ce3a  stloc.1
0x5ce3b  ldloc.1
0x5ce3c  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5ce41  brtrue.s loc_5CE64
0x5ce43  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x5ce48  ldc.i4.s 0x19
0x5ce4a  ldstr    a0// "{0}"
0x5ce4f  ldc.i4.1
0x5ce50  newarr   [mscorlib]System.Object
0x5ce55  dup
0x5ce56  ldc.i4.0
0x5ce57  ldstr    aVersionTagForM// "Version tag for Metadata expected but n"...
0x5ce5c  stelem.ref
0x5ce5d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5ce62  leave.s  loc_5CEB4
0x5ce64  ldloc.1
0x5ce65  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XPath.XPathNodeIterator::get_Current()
0x5ce6a  castclass [System.Xml]System.Xml.IHasXmlNode
0x5ce6f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.IHasXmlNode::GetNode()
0x5ce74  stloc.2
0x5ce75  ldarg.1
0x5ce76  ldloc.2
0x5ce77  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5ce7c  ldstr    aTimestamp_0// "timestamp"
0x5ce81  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5ce86  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5ce8b  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::set_Timestamp(string value)
0x5ce90  ldloc.1
0x5ce91  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNodeIterator::MoveNext()
0x5ce96  brfalse.s loc_5CEA8
0x5ce98  ldstr    aMetadataxmlCan_0// "MetadataXml cannot have more than one /"...
0x5ce9d  ldc.i4   0x8004023A
0x5cea2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5cea7  throw
0x5cea8  leave.s  loc_5CEB4
0x5ceaa  ldloc.0
0x5ceab  brfalse.s loc_5CEB3
0x5cead  ldloc.0
0x5ceae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ceb3  endfinally
0x5ceb4  ret
```
