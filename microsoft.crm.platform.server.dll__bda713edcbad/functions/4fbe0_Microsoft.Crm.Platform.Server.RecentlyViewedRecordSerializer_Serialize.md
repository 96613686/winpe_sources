# Microsoft.Crm.Platform.Server.RecentlyViewedRecordSerializer::Serialize

- ea: `0x4fbe0`
- end: `0x4fd77`
- name: `Microsoft.Crm.Platform.Server.RecentlyViewedRecordSerializer::Serialize`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x4e630`
- `0x4e650`
- `0x4e670`
- `0x4e680`
- `0x4e6c0`
- `0x4e6e0`
- `0x4e700`
- `0x4e720`
- `0x4e740`
- `0x4e760`
- `0x4e780`
- `0x4fbe0`

## string_xrefs

- `0x4fcbb`: `IconPath`
- `0x4fd12`: `ProcessId`
- `0x4fd2f`: `LastAccessed`

## pseudocode

```c

```

## disassembly

```asm
0x4fbe0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4fbe5  stloc.0
0x4fbe6  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x4fbeb  stloc.1
0x4fbec  ldloc.1
0x4fbed  ldc.i4.1
0x4fbee  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x4fbf3  ldloc.0
0x4fbf4  ldloc.1
0x4fbf5  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x4fbfa  stloc.2
0x4fbfb  ldloc.2
0x4fbfc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartDocument()
0x4fc01  ldloc.2
0x4fc02  ldstr    aRecentlyviewed_4// "RecentlyViewedItem"
0x4fc07  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fc0c  ldloc.2
0x4fc0d  ldstr    aType_0// "Type"
0x4fc12  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fc17  ldloc.2
0x4fc18  ldarg.1
0x4fc19  callvirt instance valuetype Microsoft.Crm.Platform.Server.RecentlyViewedRecordType Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_RecordType()
0x4fc1e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(int32)
0x4fc23  ldloc.2
0x4fc24  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fc29  ldloc.2
0x4fc2a  ldstr    aObjectid_0// "ObjectId"
0x4fc2f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fc34  ldloc.2
0x4fc35  ldarg.1
0x4fc36  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ObjectId()
0x4fc3b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fc40  ldloc.2
0x4fc41  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fc46  ldloc.2
0x4fc47  ldstr    aEntitytypecode_0// "EntityTypeCode"
0x4fc4c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fc51  ldloc.2
0x4fc52  ldarg.1
0x4fc53  callvirt instance int32 Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_EntityTypeCode()
0x4fc58  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(int32)
0x4fc5d  ldloc.2
0x4fc5e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fc63  ldloc.2
0x4fc64  ldstr    aDisplayname// "DisplayName"
0x4fc69  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fc6e  ldloc.2
0x4fc6f  ldarg.1
0x4fc70  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_DisplayName()
0x4fc75  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fc7a  ldloc.2
0x4fc7b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fc80  ldloc.2
0x4fc81  ldstr    aTitle_0// "Title"
0x4fc86  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fc8b  ldloc.2
0x4fc8c  ldarg.1
0x4fc8d  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_Title()
0x4fc92  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fc97  ldloc.2
0x4fc98  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fc9d  ldloc.2
0x4fc9e  ldstr    aAction// "Action"
0x4fca3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fca8  ldloc.2
0x4fca9  ldarg.1
0x4fcaa  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_Action()
0x4fcaf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fcb4  ldloc.2
0x4fcb5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fcba  ldloc.2
0x4fcbb  ldstr    aIconpath// "IconPath"
0x4fcc0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fcc5  ldloc.2
0x4fcc6  ldarg.1
0x4fcc7  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_IconPath()
0x4fccc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fcd1  ldloc.2
0x4fcd2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fcd7  ldloc.2
0x4fcd8  ldstr    aPinstatus// "PinStatus"
0x4fcdd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fce2  ldloc.2
0x4fce3  ldarg.1
0x4fce4  callvirt instance bool Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_PinStatus()
0x4fce9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(bool)
0x4fcee  ldloc.2
0x4fcef  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fcf4  ldloc.2
0x4fcf5  ldstr    aProcessinstanc// "ProcessInstanceId"
0x4fcfa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fcff  ldloc.2
0x4fd00  ldarg.1
0x4fd01  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessInstanceId()
0x4fd06  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fd0b  ldloc.2
0x4fd0c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fd11  ldloc.2
0x4fd12  ldstr    aProcessid_0// "ProcessId"
0x4fd17  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fd1c  ldloc.2
0x4fd1d  ldarg.1
0x4fd1e  callvirt instance string Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_ProcessId()
0x4fd23  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fd28  ldloc.2
0x4fd29  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fd2e  ldloc.2
0x4fd2f  ldstr    aLastaccessed// "LastAccessed"
0x4fd34  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4fd39  ldloc.2
0x4fd3a  ldarg.1
0x4fd3b  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Platform.Server.IRecentlyViewedRecord::get_LastAccessed()
0x4fd40  stloc.3
0x4fd41  ldloca.s 3
0x4fd43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4fd48  call     instance string [mscorlib]System.DateTime::ToString(class [mscorlib]System.IFormatProvider)
0x4fd4d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x4fd52  ldloc.2
0x4fd53  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fd58  ldloc.2
0x4fd59  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4fd5e  ldloc.2
0x4fd5f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndDocument()
0x4fd64  leave.s  loc_4FD70
0x4fd66  ldloc.2
0x4fd67  brfalse.s loc_4FD6F
0x4fd69  ldloc.2
0x4fd6a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4fd6f  endfinally
0x4fd70  ldloc.0
0x4fd71  callvirt instance string [mscorlib]System.Object::ToString()
0x4fd76  ret
```
