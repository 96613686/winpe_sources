# Microsoft.Crm.Workflow.ObjectModel.MetadataSourceConverter::Deserialize

- ea: `0x394a0`
- end: `0x3955b`
- name: `Microsoft.Crm.Workflow.ObjectModel.MetadataSourceConverter::Deserialize`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39470`
- `0x39d90`

## callees

- `0x39280`
- `0x392a0`
- `0x394a0`

## string_xrefs

- `0x394a4`: `Xml Reader not specified`
- `0x394be`: `Unexpected metadata information XML`
- `0x3951c`: `Unexpected tag in the metadata source XML: `

## pseudocode

```c

```

## disassembly

```asm
0x394a0  ldarg.0
0x394a1  ldnull
0x394a2  cgt.un
0x394a4  ldstr    aXmlReaderNotSp// "Xml Reader not specified"
0x394a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x394ae  ldarg.0
0x394af  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x394b4  ldstr    aMetadatasource// "MetadataSource"
0x394b9  call     bool [mscorlib]System.String::Equals(string, string)
0x394be  ldstr    aUnexpectedMeta// "Unexpected metadata information XML"
0x394c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x394c8  ldloca.s 0
0x394ca  initobj  Microsoft.Crm.Workflow.ObjectModel.MetadataSource
0x394d0  br.s     loc_3954E
0x394d2  ldarg.0
0x394d3  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x394d8  ldc.i4.1
0x394d9  bne.un.s loc_39532
0x394db  ldarg.0
0x394dc  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x394e1  stloc.1
0x394e2  ldloc.1
0x394e3  ldstr    aEntityname_0// "EntityName"
0x394e8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x394ed  brtrue.s loc_394FE
0x394ef  ldloc.1
0x394f0  ldstr    aAttributename_0// "AttributeName"
0x394f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x394fa  brtrue.s loc_3950D
0x394fc  br.s     loc_3951C
0x394fe  ldloca.s 0
0x39500  ldarg.0
0x39501  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x39506  call     instance void Microsoft.Crm.Workflow.ObjectModel.MetadataSource::set_EntityName(string value)
0x3950b  br.s     loc_3954E
0x3950d  ldloca.s 0
0x3950f  ldarg.0
0x39510  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x39515  call     instance void Microsoft.Crm.Workflow.ObjectModel.MetadataSource::set_AttributeName(string value)
0x3951a  br.s     loc_3954E
0x3951c  ldstr    aUnexpectedTagI// "Unexpected tag in the metadata source X"...
0x39521  ldarg.0
0x39522  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x39527  call     string [mscorlib]System.String::Concat(string, string)
0x3952c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x39531  throw
0x39532  ldarg.0
0x39533  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x39538  ldc.i4.s 0xF
0x3953a  bne.un.s loc_3954E
0x3953c  ldarg.0
0x3953d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x39542  ldstr    aMetadatasource// "MetadataSource"
0x39547  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3954c  brtrue.s loc_39559
0x3954e  ldarg.0
0x3954f  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x39554  brtrue   loc_394D2
0x39559  ldloc.0
0x3955a  ret
```
