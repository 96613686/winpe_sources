# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OrganizationServiceExtensions::CreatePagingFetchXml_0

- ea: `0x11aa0`
- end: `0x11b36`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.OrganizationServiceExtensions::CreatePagingFetchXml_0`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x11a70`

## callees

- `0x11aa0`

## pseudocode

```c

```

## disassembly

```asm
0x11aa0  ldarg.0
0x11aa1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x11aa6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x11aab  stloc.0
0x11aac  ldarg.1
0x11aad  brfalse.s loc_11ACD
0x11aaf  ldarg.0
0x11ab0  ldstr    aPagingCookie// "paging-cookie"
0x11ab5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x11aba  stloc.s  4
0x11abc  ldloc.s  4
0x11abe  ldarg.1
0x11abf  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x11ac4  ldloc.0
0x11ac5  ldloc.s  4
0x11ac7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x11acc  pop
0x11acd  ldarg.0
0x11ace  ldstr    aPage// "page"
0x11ad3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x11ad8  stloc.1
0x11ad9  ldloc.1
0x11ada  ldarg.2
0x11adb  call     string [mscorlib]System.Convert::ToString(int32)
0x11ae0  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x11ae5  ldloc.0
0x11ae6  ldloc.1
0x11ae7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x11aec  pop
0x11aed  ldarg.0
0x11aee  ldstr    aCount// "count"
0x11af3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x11af8  stloc.2
0x11af9  ldloc.2
0x11afa  ldarg.3
0x11afb  call     string [mscorlib]System.Convert::ToString(int32)
0x11b00  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x11b05  ldloc.0
0x11b06  ldloc.2
0x11b07  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x11b0c  pop
0x11b0d  ldc.i4   0x400
0x11b12  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x11b17  dup
0x11b18  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder)
0x11b1d  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x11b22  stloc.3
0x11b23  ldarg.0
0x11b24  ldloc.3
0x11b25  callvirt instance void [System.Xml]System.Xml.XmlNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0x11b2a  ldloc.3
0x11b2b  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x11b30  callvirt instance string [mscorlib]System.Object::ToString()
0x11b35  ret
```
