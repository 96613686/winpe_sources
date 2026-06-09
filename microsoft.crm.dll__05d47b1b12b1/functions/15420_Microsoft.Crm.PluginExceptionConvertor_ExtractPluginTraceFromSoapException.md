# Microsoft.Crm.PluginExceptionConvertor::ExtractPluginTraceFromSoapException

- ea: `0x15420`
- end: `0x15484`
- name: `Microsoft.Crm.PluginExceptionConvertor::ExtractPluginTraceFromSoapException`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x15490`

## callees

- `0x15420`

## string_xrefs

- `0x1544c`: `data/pair[key='PluginTrace']`

## pseudocode

```c

```

## disassembly

```asm
0x15420  ldarg.0
0x15421  brfalse.s loc_1542B
0x15423  ldarg.0
0x15424  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x15429  brtrue.s loc_15431
0x1542b  ldsfld   string [mscorlib]System.String::Empty
0x15430  ret
0x15431  ldsfld   string [mscorlib]System.String::Empty
0x15436  stloc.0
0x15437  ldarg.0
0x15438  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x1543d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x15442  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x15447  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x1544c  ldstr    aDataPairKeyPlu// "data/pair[key='PluginTrace']"
0x15451  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15456  stloc.1
0x15457  ldloc.1
0x15458  brfalse.s loc_15482
0x1545a  ldloc.1
0x1545b  ldstr    aValue// "value"
0x15460  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x15465  stloc.2
0x15466  ldloc.2
0x15467  brfalse.s loc_15482
0x15469  ldloc.2
0x1546a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1546f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15474  brtrue.s loc_15482
0x15476  ldloc.2
0x15477  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x1547c  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::EqualizeLineBreaks(string)
0x15481  stloc.0
0x15482  ldloc.0
0x15483  ret
```
