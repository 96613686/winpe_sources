# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read528_SetReportRelatedRequest

- ea: `0xfcff0`
- end: `0xfd700`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read528_SetReportRelatedRequest`
- size: `1808`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0xdd390`
- `0xfcff0`

## string_xrefs

- `0xfd368`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0xfd376`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0xfd4ce`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0xfd4dc`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0xfd634`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0xfd642`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0xfd1b8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0xfd1c6`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0xfd6ab`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ReportId, http://schemas.microsoft.com/crm/2007/WebServices:Entities, http://schemas.microsoft.com/crm/2007/WebServices:Categories, http://schemas.microsoft.com/crm/2007/WebServices:Visibility`
- `0xfd6b9`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ReportId, http://schemas.microsoft.com/crm/2007/WebServices:Entities, http://schemas.microsoft.com/crm/2007/WebServices:Categories, http://schemas.microsoft.com/crm/2007/WebServices:Visibility`

## pseudocode

```c

```

## disassembly

```asm
0xfcff0  ldarg.2
0xfcff1  brtrue.s loc_FCFF6
0xfcff3  ldnull
0xfcff4  br.s     loc_FCFFC
0xfcff6  ldarg.0
0xfcff7  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xfcffc  stloc.0
0xfcffd  ldc.i4.0
0xfcffe  stloc.1
0xfcfff  ldarg.1
0xfd000  brfalse.s loc_FD009
0xfd002  ldarg.0
0xfd003  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xfd008  stloc.1
0xfd009  ldarg.2
0xfd00a  brfalse.s loc_FD039
0xfd00c  ldloc.0
0xfd00d  ldnull
0xfd00e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xfd013  brtrue.s loc_FD039
0xfd015  ldloc.0
0xfd016  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xfd01b  ldarg.0
0xfd01c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1608_SetReportRelatedRequest
0xfd021  bne.un.s loc_FD031
0xfd023  ldloc.0
0xfd024  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xfd029  ldarg.0
0xfd02a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xfd02f  beq.s    loc_FD039
0xfd031  ldarg.0
0xfd032  ldloc.0
0xfd033  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xfd038  throw
0xfd039  ldloc.1
0xfd03a  brfalse.s loc_FD03E
0xfd03c  ldnull
0xfd03d  ret
0xfd03e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetReportRelatedRequest::.ctor()
0xfd043  stloc.2
0xfd044  ldc.i4.5
0xfd045  newarr   [mscorlib]System.Boolean
0xfd04a  stloc.3
0xfd04b  br.s     loc_FD067
0xfd04d  ldarg.0
0xfd04e  ldarg.0
0xfd04f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd054  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xfd059  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xfd05e  brtrue.s loc_FD067
0xfd060  ldarg.0
0xfd061  ldloc.2
0xfd062  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xfd067  ldarg.0
0xfd068  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd06d  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xfd072  brtrue.s loc_FD04D
0xfd074  ldarg.0
0xfd075  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd07a  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xfd07f  pop
0xfd080  ldarg.0
0xfd081  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd086  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xfd08b  brfalse.s loc_FD09A
0xfd08d  ldarg.0
0xfd08e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd093  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xfd098  ldloc.2
0xfd099  ret
0xfd09a  ldarg.0
0xfd09b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd0a0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xfd0a5  ldarg.0
0xfd0a6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd0ab  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xfd0b0  pop
0xfd0b1  ldc.i4.0
0xfd0b2  stloc.s  4
0xfd0b4  ldarg.0
0xfd0b5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xfd0ba  stloc.s  5
0xfd0bc  br       loc_FD6D9
0xfd0c1  ldarg.0
0xfd0c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd0c7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xfd0cc  ldc.i4.1
0xfd0cd  bne.un   loc_FD6B7
0xfd0d2  ldarg.0
0xfd0d3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd0d8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xfd0dd  ldarg.0
0xfd0de  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0xfd0e3  bne.un   loc_FD230
0xfd0e8  ldarg.0
0xfd0e9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd0ee  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xfd0f3  ldarg.0
0xfd0f4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xfd0f9  bne.un   loc_FD230
0xfd0fe  ldarg.0
0xfd0ff  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xfd104  brtrue   loc_FD6C3
0xfd109  ldnull
0xfd10a  stloc.s  6
0xfd10c  ldc.i4.0
0xfd10d  stloc.s  7
0xfd10f  ldarg.0
0xfd110  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd115  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xfd11a  brfalse.s loc_FD12C
0xfd11c  ldarg.0
0xfd11d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd122  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xfd127  br       loc_FD20B
0xfd12c  ldarg.0
0xfd12d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd132  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xfd137  ldarg.0
0xfd138  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd13d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xfd142  pop
0xfd143  ldc.i4.0
0xfd144  stloc.s  8
0xfd146  ldarg.0
0xfd147  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xfd14c  stloc.s  9
0xfd14e  br       loc_FD1E6
0xfd153  ldarg.0
0xfd154  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd159  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xfd15e  ldc.i4.1
0xfd15f  bne.un.s loc_FD1C4
0xfd161  ldarg.0
0xfd162  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd167  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xfd16c  ldarg.0
0xfd16d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0xfd172  bne.un.s loc_FD1B6
0xfd174  ldarg.0
0xfd175  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd17a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xfd17f  ldarg.0
0xfd180  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xfd185  bne.un.s loc_FD1B6
0xfd187  ldarg.0
0xfd188  ldloc.s  6
0xfd18a  ldloc.s  7
0xfd18c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0xfd191  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfd196  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0xfd19b  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0xfd1a0  stloc.s  6
0xfd1a2  ldloc.s  6
0xfd1a4  ldloc.s  7
0xfd1a6  dup
0xfd1a7  ldc.i4.1
0xfd1a8  add
0xfd1a9  stloc.s  7
0xfd1ab  ldarg.0
0xfd1ac  ldc.i4.1
0xfd1ad  ldc.i4.1
0xfd1ae  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0xfd1b3  stelem.ref
0xfd1b4  br.s     loc_FD1D0
0xfd1b6  ldarg.0
0xfd1b7  ldnull
0xfd1b8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0xfd1bd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xfd1c2  br.s     loc_FD1D0
0xfd1c4  ldarg.0
0xfd1c5  ldnull
0xfd1c6  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0xfd1cb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0xfd1d0  ldarg.0
0xfd1d1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd1d6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xfd1db  pop
0xfd1dc  ldarg.0
0xfd1dd  ldloca.s 8
0xfd1df  ldloca.s 9
0xfd1e1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0xfd1e6  ldarg.0
0xfd1e7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd1ec  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xfd1f1  ldc.i4.s 0xF
0xfd1f3  beq.s    loc_FD205
0xfd1f5  ldarg.0
0xfd1f6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd1fb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xfd200  brtrue   loc_FD153
0xfd205  ldarg.0
0xfd206  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0xfd20b  ldloc.2
0xfd20c  ldarg.0
0xfd20d  ldloc.s  6
0xfd20f  ldloc.s  7
0xfd211  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0xfd216  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfd21b  ldc.i4.0
0xfd21c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0xfd221  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0xfd226  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0xfd22b  br       loc_FD6C3
0xfd230  ldloc.3
0xfd231  ldc.i4.1
0xfd232  ldelem.i1
0xfd233  brtrue.s loc_FD27A
0xfd235  ldarg.0
0xfd236  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd23b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xfd240  ldarg.0
0xfd241  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2943_ReportId
0xfd246  bne.un.s loc_FD27A
0xfd248  ldarg.0
0xfd249  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd24e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xfd253  ldarg.0
0xfd254  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xfd259  bne.un.s loc_FD27A
0xfd25b  ldloc.2
0xfd25c  ldarg.0
0xfd25d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd262  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xfd267  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0xfd26c  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetReportRelatedRequest::set_ReportId(valuetype [mscorlib]System.Guid)
0xfd271  ldloc.3
0xfd272  ldc.i4.1
0xfd273  ldc.i4.1
0xfd274  stelem.i1
0xfd275  br       loc_FD6C3
0xfd27a  ldarg.0
0xfd27b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd280  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xfd285  ldarg.0
0xfd286  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3112_Entities
0xfd28b  bne.un   loc_FD3E0
0xfd290  ldarg.0
0xfd291  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd296  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xfd29b  ldarg.0
0xfd29c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xfd2a1  bne.un   loc_FD3E0
0xfd2a6  ldarg.0
0xfd2a7  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xfd2ac  brtrue   loc_FD6C3
0xfd2b1  ldnull
0xfd2b2  stloc.s  0xA
0xfd2b4  ldc.i4.0
0xfd2b5  stloc.s  0xB
0xfd2b7  ldarg.0
0xfd2b8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd2bd  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xfd2c2  brfalse.s loc_FD2D4
0xfd2c4  ldarg.0
0xfd2c5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd2ca  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xfd2cf  br       loc_FD3BB
0xfd2d4  ldarg.0
0xfd2d5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd2da  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xfd2df  ldarg.0
0xfd2e0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd2e5  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xfd2ea  pop
0xfd2eb  ldc.i4.0
0xfd2ec  stloc.s  0xC
0xfd2ee  ldarg.0
0xfd2ef  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xfd2f4  stloc.s  0xD
0xfd2f6  br       loc_FD396
0xfd2fb  ldarg.0
0xfd2fc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd301  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xfd306  ldc.i4.1
0xfd307  bne.un.s loc_FD374
0xfd309  ldarg.0
0xfd30a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd30f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xfd314  ldarg.0
0xfd315  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id242_int
0xfd31a  bne.un.s loc_FD366
0xfd31c  ldarg.0
0xfd31d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xfd322  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xfd327  ldarg.0
0xfd328  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xfd32d  bne.un.s loc_FD366
0xfd32f  ldarg.0
0xfd330  ldloc.s  0xA
0xfd332  ldloc.s  0xB
0xfd334  ldtoken  [mscorlib]System.Int32
0xfd339  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xfd33e  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0xfd343  castclass int32[]
0xfd348  stloc.s  0xA
0xfd34a  ldloc.s  0xA
0xfd34c  ldloc.s  0xB
0xfd34e  dup
0xfd34f  ldc.i4.1
  ... truncated ...
```
