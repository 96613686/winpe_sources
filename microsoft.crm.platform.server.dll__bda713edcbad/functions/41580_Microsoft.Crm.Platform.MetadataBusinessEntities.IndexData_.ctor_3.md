# Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::.ctor_3

- ea: `0x41580`
- end: `0x41877`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::.ctor_3`
- size: `759`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x40b70`
- `0x41580`
- `0x41d70`
- `0x42050`
- `0x420b0`
- `0x85d00`

## string_xrefs

- `0x4183f`: `Index {0} cannot be parsed because no entity id was provided in the XML definition and no entity metadata was provided`
- `0x4186b`: `Index cannot be created without any index attributes`

## pseudocode

```c

```

## disassembly

```asm
0x41580  ldarg.0
0x41581  ldc.i4.6
0x41582  stfld    int32 Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexType
0x41587  ldarg.0
0x41588  ldc.i4.s 0x50
0x4158a  stfld    int32 Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_fillFactor
0x4158f  ldarg.0
0x41590  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute>::.ctor()
0x41595  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute> Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexAttributes
0x4159a  ldarg.0
0x4159b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexFilter>::.ctor()
0x415a0  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexFilter> Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexFilters
0x415a5  ldarg.0
0x415a6  ldsfld   string [mscorlib]System.String::Empty
0x415ab  stfld    string Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexFilterString
0x415b0  ldarg.0
0x415b1  call     instance void [mscorlib]System.Object::.ctor()
0x415b6  ldarg.0
0x415b7  ldarg.1
0x415b8  ldstr    aName_2// "Name"
0x415bd  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x415c2  stfld    string Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexName
0x415c7  ldarg.1
0x415c8  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x415cd  br       loc_41806
0x415d2  ldarg.1
0x415d3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x415d8  stloc.0
0x415d9  ldloc.0
0x415da  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x415df  stloc.1
0x415e0  ldloc.1
0x415e1  ldc.i4   0xABD6BE4C
0x415e6  bgt.un.s loc_41620
0x415e8  ldloc.1
0x415e9  ldc.i4   0x93ADC516
0x415ee  bgt.un.s loc_41608
0x415f0  ldloc.1
0x415f1  ldc.i4   0xC857DC4
0x415f6  beq.s    loc_41663
0x415f8  ldloc.1
0x415f9  ldc.i4   0x93ADC516
0x415fe  beq      loc_4168D
0x41603  br       loc_41806
0x41608  ldloc.1
0x41609  ldc.i4   0xA1A85091
0x4160e  beq.s    loc_41678
0x41610  ldloc.1
0x41611  ldc.i4   0xABD6BE4C
0x41616  beq      loc_4170B
0x4161b  br       loc_41806
0x41620  ldloc.1
0x41621  ldc.i4   0xD136ED57
0x41626  bgt.un.s loc_41643
0x41628  ldloc.1
0x41629  ldc.i4   0xB0A2CC2D
0x4162e  beq      loc_416B7
0x41633  ldloc.1
0x41634  ldc.i4   0xD136ED57
0x41639  beq      loc_416E1
0x4163e  br       loc_41806
0x41643  ldloc.1
0x41644  ldc.i4   0xE1B8ADC0
0x41649  beq.s    loc_416A2
0x4164b  ldloc.1
0x4164c  ldc.i4   0xE1FFDB94
0x41651  beq      loc_416F6
0x41656  ldloc.1
0x41657  ldc.i4   0xF47183F3
0x4165c  beq.s    loc_416CC
0x4165e  br       loc_41806
0x41663  ldloc.0
0x41664  ldstr    aIsclustered// "IsClustered"
0x41669  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4166e  brtrue   loc_41720
0x41673  br       loc_41806
0x41678  ldloc.0
0x41679  ldstr    aSqlfillfactor// "SqlFillFactor"
0x4167e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x41683  brtrue   loc_41736
0x41688  br       loc_41806
0x4168d  ldloc.0
0x4168e  ldstr    aIsunique// "IsUnique"
0x41693  call     bool [mscorlib]System.String::op_Equality(string, string)
0x41698  brtrue   loc_4174E
0x4169d  br       loc_41806
0x416a2  ldloc.0
0x416a3  ldstr    aIsprimarykey// "IsPrimaryKey"
0x416a8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x416ad  brtrue   loc_41764
0x416b2  br       loc_41806
0x416b7  ldloc.0
0x416b8  ldstr    aIsuniqueconstr// "IsUniqueConstraint"
0x416bd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x416c2  brtrue   loc_4177A
0x416c7  br       loc_41806
0x416cc  ldloc.0
0x416cd  ldstr    aIndextype_0// "IndexType"
0x416d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x416d7  brtrue   loc_4178D
0x416dc  br       loc_41806
0x416e1  ldloc.0
0x416e2  ldstr    aEntityid_2// "EntityId"
0x416e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x416ec  brtrue   loc_417A1
0x416f1  br       loc_41806
0x416f6  ldloc.0
0x416f7  ldstr    aAttributes// "attributes"
0x416fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x41701  brtrue   loc_417B4
0x41706  br       loc_41806
0x4170b  ldloc.0
0x4170c  ldstr    aFilters// "filters"
0x41711  call     bool [mscorlib]System.String::op_Equality(string, string)
0x41716  brtrue   loc_417DE
0x4171b  br       loc_41806
0x41720  ldarg.0
0x41721  ldarg.1
0x41722  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x41727  call     bool Microsoft.Crm.Platform.MetadataBusinessEntities.ConversionHelper::ParseBool(string boolVal)
0x4172c  stfld    bool Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_isClustered
0x41731  br       loc_41806
0x41736  ldarg.0
0x41737  ldarg.1
0x41738  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x4173d  ldc.i4.s 0x50
0x4173f  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.ConversionHelper::ParseInt(string intVal, int32 defaultValue)
0x41744  stfld    int32 Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_fillFactor
0x41749  br       loc_41806
0x4174e  ldarg.0
0x4174f  ldarg.1
0x41750  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x41755  call     bool Microsoft.Crm.Platform.MetadataBusinessEntities.ConversionHelper::ParseBool(string boolVal)
0x4175a  stfld    bool Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_isUnique
0x4175f  br       loc_41806
0x41764  ldarg.0
0x41765  ldarg.1
0x41766  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x4176b  call     bool Microsoft.Crm.Platform.MetadataBusinessEntities.ConversionHelper::ParseBool(string boolVal)
0x41770  stfld    bool Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_isPrimaryKey
0x41775  br       loc_41806
0x4177a  ldarg.0
0x4177b  ldarg.1
0x4177c  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x41781  call     bool Microsoft.Crm.Platform.MetadataBusinessEntities.ConversionHelper::ParseBool(string boolVal)
0x41786  stfld    bool Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_isUniqueConstraint
0x4178b  br.s     loc_41806
0x4178d  ldarg.0
0x4178e  ldarg.1
0x4178f  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x41794  ldc.i4.6
0x41795  call     int32 Microsoft.Crm.Platform.MetadataBusinessEntities.ConversionHelper::ParseInt(string intVal, int32 defaultValue)
0x4179a  stfld    int32 Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexType
0x4179f  br.s     loc_41806
0x417a1  ldarg.0
0x417a2  ldarg.1
0x417a3  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x417a8  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x417ad  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_entityId
0x417b2  br.s     loc_41806
0x417b4  ldarg.1
0x417b5  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x417ba  br.s     loc_417CE
0x417bc  ldarg.0
0x417bd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute> Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexAttributes
0x417c2  ldarg.1
0x417c3  ldarg.2
0x417c4  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute::.ctor(class [System.Xml]System.Xml.XmlReader reader, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x417c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute>::Add(var<u1>)
0x417ce  ldarg.1
0x417cf  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x417d4  brtrue.s loc_417BC
0x417d6  ldarg.1
0x417d7  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x417dc  br.s     loc_41806
0x417de  ldarg.1
0x417df  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x417e4  br.s     loc_417F8
0x417e6  ldarg.0
0x417e7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexFilter> Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexFilters
0x417ec  ldarg.1
0x417ed  ldarg.2
0x417ee  newobj   instance void Microsoft.Crm.Platform.MetadataBusinessEntities.IndexFilter::.ctor(class [System.Xml]System.Xml.XmlReader reader, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x417f3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexFilter>::Add(var<u1>)
0x417f8  ldarg.1
0x417f9  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x417fe  brtrue.s loc_417E6
0x41800  ldarg.1
0x41801  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x41806  ldarg.1
0x41807  callvirt instance bool [System.Xml]System.Xml.XmlReader::IsStartElement()
0x4180c  brtrue   loc_415D2
0x41811  ldarg.1
0x41812  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x41817  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4181c  ldarg.0
0x4181d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_entityId
0x41822  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x41827  brfalse.s loc_4185E
0x41829  ldarg.2
0x4182a  brfalse.s loc_4183A
0x4182c  ldarg.0
0x4182d  ldarg.2
0x4182e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x41833  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_entityId
0x41838  br.s     loc_4185E
0x4183a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4183f  ldstr    aIndex0CannotBe// "Index {0} cannot be parsed because no e"...
0x41844  ldc.i4.1
0x41845  newarr   [mscorlib]System.Object
0x4184a  dup
0x4184b  ldc.i4.0
0x4184c  ldarg.0
0x4184d  ldfld    string Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexName
0x41852  stelem.ref
0x41853  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x41858  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4185d  throw
0x4185e  ldarg.0
0x4185f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute> Microsoft.Crm.Platform.MetadataBusinessEntities.IndexData::_indexAttributes
0x41864  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Platform.MetadataBusinessEntities.IndexAttribute>::get_Count()
0x41869  brtrue.s loc_41876
0x4186b  ldstr    aIndexCannotBeC// "Index cannot be created without any ind"...
0x41870  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x41875  throw
0x41876  ret
```
