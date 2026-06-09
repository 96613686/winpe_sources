# Microsoft.Crm.Entities.CommunicationActivity::OldStyleSerialize

- ea: `0x3a0`
- end: `0x6e7`
- name: `Microsoft.Crm.Entities.CommunicationActivity::OldStyleSerialize`
- size: `839`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x100`
- `0x3a0`
- `0xc50`
- `0xc90`

## string_xrefs

- `0x5a4`: `Cannot create activity party for email: either partyid or addressused field should be present`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a5  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x3aa  stloc.0
0x3ab  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x3b0  stloc.1
0x3b1  ldloc.1
0x3b2  ldc.i4.1
0x3b3  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x3b8  ldloc.0
0x3b9  ldloc.1
0x3ba  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0x3bf  stloc.2
0x3c0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.V1EntitySerializationStrategy::.ctor()
0x3c5  stloc.3
0x3c6  ldloc.2
0x3c7  ldarg.0
0x3c8  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x3cd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x3d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3d7  ldarg.3
0x3d8  brfalse  loc_499
0x3dd  ldarg.0
0x3de  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Clone()
0x3e3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3e8  stloc.s  4
0x3ea  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x3ef  stloc.s  5
0x3f1  ldloc.s  4
0x3f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x3f8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x3fd  stloc.s  7
0x3ff  br.s     loc_437
0x401  ldloc.s  7
0x403  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x408  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfo
0x40d  stloc.s  8
0x40f  ldarg.0
0x410  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x415  ldloc.s  8
0x417  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x41c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x421  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForUpdate()
0x426  brtrue.s loc_437
0x428  ldloc.s  5
0x42a  ldloc.s  8
0x42c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Name()
0x431  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x436  pop
0x437  ldloc.s  7
0x439  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x43e  brtrue.s loc_401
0x440  leave.s  loc_457
0x442  ldloc.s  7
0x444  isinst   [mscorlib]System.IDisposable
0x449  stloc.s  9
0x44b  ldloc.s  9
0x44d  brfalse.s loc_456
0x44f  ldloc.s  9
0x451  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x456  endfinally
0x457  ldc.i4.0
0x458  stloc.s  0xA
0x45a  br.s     loc_477
0x45c  ldloc.s  4
0x45e  ldloc.s  5
0x460  ldloc.s  0xA
0x462  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x467  castclass [mscorlib]System.String
0x46c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::ClearAttribute(string)
0x471  ldloc.s  0xA
0x473  ldc.i4.1
0x474  add
0x475  stloc.s  0xA
0x477  ldloc.s  0xA
0x479  ldloc.s  5
0x47b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x480  blt.s    loc_45C
0x482  ldloc.s  4
0x484  ldc.i4.0
0x485  ldloc.2
0x486  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, bool, class [System.Xml]System.Xml.XmlWriter)
0x48b  stloc.s  6
0x48d  ldloc.s  4
0x48f  ldloc.s  6
0x491  ldloc.3
0x492  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SerializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x497  br.s     loc_4AC
0x499  ldarg.0
0x49a  ldc.i4.0
0x49b  ldloc.2
0x49c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, bool, class [System.Xml]System.Xml.XmlWriter)
0x4a1  stloc.s  0xB
0x4a3  ldarg.0
0x4a4  ldloc.s  0xB
0x4a6  ldloc.3
0x4a7  call     instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SerializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x4ac  ldarg.0
0x4ad  ldstr    aRegardingobjec// "regardingobjecttypecode"
0x4b2  call     instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x4b7  brtrue.s loc_4FF
0x4b9  ldarg.0
0x4ba  ldstr    aRegardingobjec// "regardingobjecttypecode"
0x4bf  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4c4  unbox.any [mscorlib]System.Int32
0x4c9  brfalse.s loc_4FF
0x4cb  ldarg.0
0x4cc  ldstr    aRegardingobjec_0// "regardingobjectid"
0x4d1  call     instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x4d6  brtrue.s loc_4FF
0x4d8  ldloc.2
0x4d9  ldstr    aRegardingobjec// "regardingobjecttypecode"
0x4de  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4e3  ldloc.2
0x4e4  ldarg.0
0x4e5  ldstr    aRegardingobjec// "regardingobjecttypecode"
0x4ea  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4ef  callvirt instance string [mscorlib]System.Object::ToString()
0x4f4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x4f9  ldloc.2
0x4fa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4ff  ldloc.2
0x500  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x505  ldloc.2
0x506  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x50b  ldarg.1
0x50c  ldloc.0
0x50d  callvirt instance string [mscorlib]System.Object::ToString()
0x512  stind.ref
0x513  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x518  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x51d  stloc.s  0xC
0x51f  ldloc.s  0xC
0x521  ldloc.1
0x522  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.IO.TextWriter, class [System.Xml]System.Xml.XmlWriterSettings)
0x527  stloc.s  0xD
0x529  ldc.i4.0
0x52a  stloc.s  0xE
0x52c  ldloc.s  0xD
0x52e  ldstr    aActivitypartie// "activityparties"
0x533  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x538  ldarg.0
0x539  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x53e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x543  stloc.s  7
0x545  br       loc_671
0x54a  ldloc.s  7
0x54c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x551  castclass Microsoft.Crm.Entities.PartyMappingItem
0x556  stloc.s  0xF
0x558  ldloc.s  0xF
0x55a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x55f  brfalse  loc_671
0x564  ldc.i4.1
0x565  stloc.s  0xE
0x567  ldloc.s  0xF
0x569  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x56e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x573  stloc.s  0x10
0x575  br       loc_64E
0x57a  ldloc.s  0x10
0x57c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x581  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x586  stloc.s  0x11
0x588  ldloc.s  0x11
0x58a  ldstr    aPartyid// "partyid"
0x58f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x594  brtrue.s loc_5AF
0x596  ldloc.s  0x11
0x598  ldstr    aAddressused// "addressused"
0x59d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a2  brtrue.s loc_5AF
0x5a4  ldstr    aCannotCreateAc// "Cannot create activity party for email:"...
0x5a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5ae  throw
0x5af  ldloc.s  0x11
0x5b1  ldstr    aParticipationt// "participationtypemask"
0x5b6  ldloc.s  0xF
0x5b8  callvirt instance valuetype Microsoft.Crm.Entities.ParticipationType Microsoft.Crm.Entities.PartyMappingItem::get_Type()
0x5bd  box      [mscorlib]System.Int32
0x5c2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5c7  ldloc.s  0x11
0x5c9  ldstr    aActivityid// "activityid"
0x5ce  ldarg.0
0x5cf  ldstr    aActivityid// "activityid"
0x5d4  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5de  ldloc.s  0xD
0x5e0  ldstr    aActivityparty_0// "activityparty"
0x5e5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x5ea  ldloc.s  0x11
0x5ec  ldc.i4.0
0x5ed  ldloc.s  0xD
0x5ef  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, bool, class [System.Xml]System.Xml.XmlWriter)
0x5f4  stloc.s  0x12
0x5f6  ldloc.s  0x11
0x5f8  ldloc.s  0x12
0x5fa  ldloc.3
0x5fb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SerializeAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntitySerializationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x600  ldloc.s  0xD
0x602  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x607  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x60c  ldloc.s  0x11
0x60e  ldstr    aPartyid// "partyid"
0x613  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x618  brtrue.s loc_628
0x61a  ldloc.s  0xD
0x61c  ldstr    a0// "0"
0x621  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x626  br.s     loc_640
0x628  ldloc.s  0xD
0x62a  ldloc.s  0x11
0x62c  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x631  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x636  callvirt instance string [mscorlib]System.Object::ToString()
0x63b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x640  ldloc.s  0xD
0x642  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x647  ldloc.s  0xD
0x649  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x64e  ldloc.s  0x10
0x650  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x655  brtrue   loc_57A
0x65a  leave.s  loc_671
0x65c  ldloc.s  0x10
0x65e  isinst   [mscorlib]System.IDisposable
0x663  stloc.s  9
0x665  ldloc.s  9
0x667  brfalse.s loc_670
0x669  ldloc.s  9
0x66b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x670  endfinally
0x671  ldloc.s  7
0x673  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x678  brtrue   loc_54A
0x67d  leave.s  loc_694
0x67f  ldloc.s  7
0x681  isinst   [mscorlib]System.IDisposable
0x686  stloc.s  9
0x688  ldloc.s  9
0x68a  brfalse.s loc_693
0x68c  ldloc.s  9
0x68e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x693  endfinally
0x694  ldloc.s  0xD
0x696  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x69b  ldloc.s  0xD
0x69d  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x6a2  ldloc.s  0xE
0x6a4  brfalse.s loc_6B1
0x6a6  ldarg.2
0x6a7  ldloc.s  0xC
0x6a9  callvirt instance string [mscorlib]System.Object::ToString()
0x6ae  stind.ref
0x6af  leave.s  loc_6E6
0x6b1  ldarg.2
0x6b2  ldsfld   string [mscorlib]System.String::Empty
0x6b7  stind.ref
0x6b8  leave.s  loc_6E6
0x6ba  ldloc.s  0xD
0x6bc  brfalse.s loc_6C5
0x6be  ldloc.s  0xD
0x6c0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6c5  endfinally
0x6c6  ldloc.s  0xC
0x6c8  brfalse.s loc_6D1
0x6ca  ldloc.s  0xC
0x6cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6d1  endfinally
0x6d2  ldloc.2
0x6d3  brfalse.s loc_6DB
0x6d5  ldloc.2
0x6d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6db  endfinally
0x6dc  ldloc.0
0x6dd  brfalse.s loc_6E5
0x6df  ldloc.0
0x6e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6e5  endfinally
0x6e6  ret
```
