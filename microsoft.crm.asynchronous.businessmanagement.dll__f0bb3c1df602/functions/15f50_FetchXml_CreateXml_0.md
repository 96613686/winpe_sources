# FetchXml::CreateXml_0

- ea: `0x15f50`
- end: `0x15fe6`
- name: `FetchXml::CreateXml_0`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x15f20`

## callees

- `0x15f50`

## pseudocode

```c

```

## disassembly

```asm
0x15f50  ldarg.0
0x15f51  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x15f56  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x15f5b  stloc.0
0x15f5c  ldarg.1
0x15f5d  brfalse.s loc_15F7D
0x15f5f  ldarg.0
0x15f60  ldstr    aPagingCookie// "paging-cookie"
0x15f65  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x15f6a  stloc.s  4
0x15f6c  ldloc.s  4
0x15f6e  ldarg.1
0x15f6f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x15f74  ldloc.0
0x15f75  ldloc.s  4
0x15f77  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x15f7c  pop
0x15f7d  ldarg.0
0x15f7e  ldstr    aPage// "page"
0x15f83  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x15f88  stloc.1
0x15f89  ldloc.1
0x15f8a  ldarg.2
0x15f8b  call     string [mscorlib]System.Convert::ToString(int32)
0x15f90  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x15f95  ldloc.0
0x15f96  ldloc.1
0x15f97  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x15f9c  pop
0x15f9d  ldarg.0
0x15f9e  ldstr    aCount// "count"
0x15fa3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x15fa8  stloc.2
0x15fa9  ldloc.2
0x15faa  ldarg.3
0x15fab  call     string [mscorlib]System.Convert::ToString(int32)
0x15fb0  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x15fb5  ldloc.0
0x15fb6  ldloc.2
0x15fb7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x15fbc  pop
0x15fbd  ldc.i4   0x400
0x15fc2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x15fc7  dup
0x15fc8  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder)
0x15fcd  newobj   instance void [System.Xml]System.Xml.XmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x15fd2  stloc.3
0x15fd3  ldarg.0
0x15fd4  ldloc.3
0x15fd5  callvirt instance void [System.Xml]System.Xml.XmlNode::WriteTo(class [System.Xml]System.Xml.XmlWriter)
0x15fda  ldloc.3
0x15fdb  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x15fe0  callvirt instance string [mscorlib]System.Object::ToString()
0x15fe5  ret
```
