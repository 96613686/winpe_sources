# Microsoft.Crm.Sdk.Messages.RecentItem::ToXml

- ea: `0xe90`
- end: `0x1035`
- name: `Microsoft.Crm.Sdk.Messages.RecentItem::ToXml`
- size: `421`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0xc30`
- `0xc50`
- `0xc70`
- `0xc90`
- `0xcd0`
- `0xd10`
- `0xd40`
- `0xd60`
- `0xd80`
- `0xda0`
- `0xde0`
- `0xe90`

## string_xrefs

- `0xf73`: `IconPath`
- `0xfcf`: `ProcessId`
- `0xfec`: `LastAccessed`

## pseudocode

```c

```

## disassembly

```asm
0xe90  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xe95  stloc.0
0xe96  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0xe9b  dup
0xe9c  ldc.i4.1
0xe9d  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0xea2  stloc.1
0xea3  ldloc.0
0xea4  ldloc.1
0xea5  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0xeaa  stloc.2
0xeab  ldloc.2
0xeac  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartDocument()
0xeb1  ldloc.2
0xeb2  ldstr    aRecentlyviewed// "RecentlyViewedItem"
0xeb7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xebc  ldloc.2
0xebd  ldstr    aType// "Type"
0xec2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xec7  ldloc.2
0xec8  ldarg.0
0xec9  call     instance valuetype [mscorlib]System.Nullable`1<valuetype RecentlyViewedRecordType> Microsoft.Crm.Sdk.Messages.RecentItem::get_RecordType()
0xece  stloc.3
0xecf  ldloca.s 3
0xed1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype RecentlyViewedRecordType>::GetValueOrDefault()
0xed6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(int32)
0xedb  ldloc.2
0xedc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xee1  ldloc.2
0xee2  ldstr    aObjectid// "ObjectId"
0xee7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xeec  ldloc.2
0xeed  ldarg.0
0xeee  call     instance string Microsoft.Crm.Sdk.Messages.RecentItem::get_ObjectId()
0xef3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xef8  ldloc.2
0xef9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xefe  ldloc.2
0xeff  ldstr    aEntitytypecode// "EntityTypeCode"
0xf04  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf09  ldloc.2
0xf0a  ldarg.0
0xf0b  call     instance int32 Microsoft.Crm.Sdk.Messages.RecentItem::get_EntityTypeCode()
0xf10  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(int32)
0xf15  ldloc.2
0xf16  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf1b  ldloc.2
0xf1c  ldstr    aDisplayname// "DisplayName"
0xf21  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf26  ldloc.2
0xf27  ldarg.0
0xf28  call     instance string Microsoft.Crm.Sdk.Messages.RecentItem::get_DisplayName()
0xf2d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xf32  ldloc.2
0xf33  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf38  ldloc.2
0xf39  ldstr    aTitle// "Title"
0xf3e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf43  ldloc.2
0xf44  ldarg.0
0xf45  call     instance string Microsoft.Crm.Sdk.Messages.RecentItem::get_Title()
0xf4a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xf4f  ldloc.2
0xf50  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf55  ldloc.2
0xf56  ldstr    aAction// "Action"
0xf5b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf60  ldloc.2
0xf61  ldarg.0
0xf62  call     instance string Microsoft.Crm.Sdk.Messages.RecentItem::get_Action()
0xf67  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xf6c  ldloc.2
0xf6d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf72  ldloc.2
0xf73  ldstr    aIconpath// "IconPath"
0xf78  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf7d  ldloc.2
0xf7e  ldarg.0
0xf7f  call     instance string Microsoft.Crm.Sdk.Messages.RecentItem::get_IconPath()
0xf84  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xf89  ldloc.2
0xf8a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xf8f  ldloc.2
0xf90  ldstr    aPinstatus// "PinStatus"
0xf95  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xf9a  ldloc.2
0xf9b  ldarg.0
0xf9c  call     instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Sdk.Messages.RecentItem::get_PinStatus()
0xfa1  box      valuetype [mscorlib]System.Nullable`1<bool>
0xfa6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(object)
0xfab  ldloc.2
0xfac  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xfb1  ldloc.2
0xfb2  ldstr    aProcessinstanc// "ProcessInstanceId"
0xfb7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xfbc  ldloc.2
0xfbd  ldarg.0
0xfbe  call     instance string Microsoft.Crm.Sdk.Messages.RecentItem::get_ProcessInstanceId()
0xfc3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xfc8  ldloc.2
0xfc9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xfce  ldloc.2
0xfcf  ldstr    aProcessid// "ProcessId"
0xfd4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xfd9  ldloc.2
0xfda  ldarg.0
0xfdb  call     instance string Microsoft.Crm.Sdk.Messages.RecentItem::get_ProcessId()
0xfe0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0xfe5  ldloc.2
0xfe6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xfeb  ldloc.2
0xfec  ldstr    aLastaccessed// "LastAccessed"
0xff1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xff6  ldloc.2
0xff7  ldarg.0
0xff8  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Sdk.Messages.RecentItem::get_LastAccessed()
0xffd  stloc.s  4
0xfff  ldloca.s 4
0x1001  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1006  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x100b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x1010  ldloc.2
0x1011  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1016  ldloc.2
0x1017  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x101c  ldloc.2
0x101d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndDocument()
0x1022  leave.s  loc_102E
0x1024  ldloc.2
0x1025  brfalse.s loc_102D
0x1027  ldloc.2
0x1028  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x102d  endfinally
0x102e  ldloc.0
0x102f  callvirt instance string [mscorlib]System.Object::ToString()
0x1034  ret
```
