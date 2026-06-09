# Microsoft.Crm.Workflow.ObjectModel.MetadataSourceConverter::Serialize

- ea: `0x39560`
- end: `0x395a4`
- name: `Microsoft.Crm.Workflow.ObjectModel.MetadataSourceConverter::Serialize`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39420`
- `0x39cb0`

## callees

- `0x39270`
- `0x39290`

## string_xrefs

- `0x39564`: `Xml Writer not specified`

## pseudocode

```c

```

## disassembly

```asm
0x39560  ldarg.0
0x39561  ldnull
0x39562  cgt.un
0x39564  ldstr    aXmlWriterNotSp// "Xml Writer not specified"
0x39569  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3956e  ldarg.0
0x3956f  ldstr    aMetadatasource// "MetadataSource"
0x39574  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x39579  ldarg.0
0x3957a  ldstr    aEntityname_0// "EntityName"
0x3957f  ldarga.s 1
0x39581  call     instance string Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_EntityName()
0x39586  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x3958b  ldarg.0
0x3958c  ldstr    aAttributename_0// "AttributeName"
0x39591  ldarga.s 1
0x39593  call     instance string Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_AttributeName()
0x39598  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x3959d  ldarg.0
0x3959e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x395a3  ret
```
