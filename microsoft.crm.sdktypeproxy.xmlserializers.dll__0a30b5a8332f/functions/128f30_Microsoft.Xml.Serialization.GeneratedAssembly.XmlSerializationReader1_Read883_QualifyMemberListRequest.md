# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read883_QualifyMemberListRequest

- ea: `0x128f30`
- end: `0x1293c4`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read883_QualifyMemberListRequest`
- size: `1172`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0xdd390`
- `0x128f30`

## string_xrefs

- `0x1290f8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x129106`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1292b1`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x1292bf`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x12936f`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ListId, http://schemas.microsoft.com/crm/2007/WebServices:MembersId, http://schemas.microsoft.com/crm/2007/WebServices:OverrideorRemove`
- `0x12937d`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ListId, http://schemas.microsoft.com/crm/2007/WebServices:MembersId, http://schemas.microsoft.com/crm/2007/WebServices:OverrideorRemove`

## pseudocode

```c

```

## disassembly

```asm
0x128f30  ldarg.2
0x128f31  brtrue.s loc_128F36
0x128f33  ldnull
0x128f34  br.s     loc_128F3C
0x128f36  ldarg.0
0x128f37  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x128f3c  stloc.0
0x128f3d  ldc.i4.0
0x128f3e  stloc.1
0x128f3f  ldarg.1
0x128f40  brfalse.s loc_128F49
0x128f42  ldarg.0
0x128f43  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x128f48  stloc.1
0x128f49  ldarg.2
0x128f4a  brfalse.s loc_128F79
0x128f4c  ldloc.0
0x128f4d  ldnull
0x128f4e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x128f53  brtrue.s loc_128F79
0x128f55  ldloc.0
0x128f56  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x128f5b  ldarg.0
0x128f5c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1519_QualifyMemberListRequest
0x128f61  bne.un.s loc_128F71
0x128f63  ldloc.0
0x128f64  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x128f69  ldarg.0
0x128f6a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x128f6f  beq.s    loc_128F79
0x128f71  ldarg.0
0x128f72  ldloc.0
0x128f73  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x128f78  throw
0x128f79  ldloc.1
0x128f7a  brfalse.s loc_128F7E
0x128f7c  ldnull
0x128f7d  ret
0x128f7e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QualifyMemberListRequest::.ctor()
0x128f83  stloc.2
0x128f84  ldc.i4.4
0x128f85  newarr   [mscorlib]System.Boolean
0x128f8a  stloc.3
0x128f8b  br.s     loc_128FA7
0x128f8d  ldarg.0
0x128f8e  ldarg.0
0x128f8f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128f94  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x128f99  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x128f9e  brtrue.s loc_128FA7
0x128fa0  ldarg.0
0x128fa1  ldloc.2
0x128fa2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x128fa7  ldarg.0
0x128fa8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128fad  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x128fb2  brtrue.s loc_128F8D
0x128fb4  ldarg.0
0x128fb5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128fba  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x128fbf  pop
0x128fc0  ldarg.0
0x128fc1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128fc6  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x128fcb  brfalse.s loc_128FDA
0x128fcd  ldarg.0
0x128fce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128fd3  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x128fd8  ldloc.2
0x128fd9  ret
0x128fda  ldarg.0
0x128fdb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128fe0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x128fe5  ldarg.0
0x128fe6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128feb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x128ff0  pop
0x128ff1  ldc.i4.0
0x128ff2  stloc.s  4
0x128ff4  ldarg.0
0x128ff5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x128ffa  stloc.s  5
0x128ffc  br       loc_12939D
0x129001  ldarg.0
0x129002  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129007  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x12900c  ldc.i4.1
0x12900d  bne.un   loc_12937B
0x129012  ldarg.0
0x129013  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129018  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12901d  ldarg.0
0x12901e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x129023  bne.un   loc_129170
0x129028  ldarg.0
0x129029  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12902e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x129033  ldarg.0
0x129034  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x129039  bne.un   loc_129170
0x12903e  ldarg.0
0x12903f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x129044  brtrue   loc_129387
0x129049  ldnull
0x12904a  stloc.s  6
0x12904c  ldc.i4.0
0x12904d  stloc.s  7
0x12904f  ldarg.0
0x129050  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129055  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x12905a  brfalse.s loc_12906C
0x12905c  ldarg.0
0x12905d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129062  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x129067  br       loc_12914B
0x12906c  ldarg.0
0x12906d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129072  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x129077  ldarg.0
0x129078  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12907d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x129082  pop
0x129083  ldc.i4.0
0x129084  stloc.s  8
0x129086  ldarg.0
0x129087  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x12908c  stloc.s  9
0x12908e  br       loc_129126
0x129093  ldarg.0
0x129094  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129099  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x12909e  ldc.i4.1
0x12909f  bne.un.s loc_129104
0x1290a1  ldarg.0
0x1290a2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1290a7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1290ac  ldarg.0
0x1290ad  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x1290b2  bne.un.s loc_1290F6
0x1290b4  ldarg.0
0x1290b5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1290ba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1290bf  ldarg.0
0x1290c0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1290c5  bne.un.s loc_1290F6
0x1290c7  ldarg.0
0x1290c8  ldloc.s  6
0x1290ca  ldloc.s  7
0x1290cc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x1290d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1290d6  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x1290db  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x1290e0  stloc.s  6
0x1290e2  ldloc.s  6
0x1290e4  ldloc.s  7
0x1290e6  dup
0x1290e7  ldc.i4.1
0x1290e8  add
0x1290e9  stloc.s  7
0x1290eb  ldarg.0
0x1290ec  ldc.i4.1
0x1290ed  ldc.i4.1
0x1290ee  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x1290f3  stelem.ref
0x1290f4  br.s     loc_129110
0x1290f6  ldarg.0
0x1290f7  ldnull
0x1290f8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x1290fd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x129102  br.s     loc_129110
0x129104  ldarg.0
0x129105  ldnull
0x129106  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x12910b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x129110  ldarg.0
0x129111  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129116  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12911b  pop
0x12911c  ldarg.0
0x12911d  ldloca.s 8
0x12911f  ldloca.s 9
0x129121  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x129126  ldarg.0
0x129127  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12912c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x129131  ldc.i4.s 0xF
0x129133  beq.s    loc_129145
0x129135  ldarg.0
0x129136  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12913b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x129140  brtrue   loc_129093
0x129145  ldarg.0
0x129146  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x12914b  ldloc.2
0x12914c  ldarg.0
0x12914d  ldloc.s  6
0x12914f  ldloc.s  7
0x129151  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x129156  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12915b  ldc.i4.0
0x12915c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x129161  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x129166  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x12916b  br       loc_129387
0x129170  ldloc.3
0x129171  ldc.i4.1
0x129172  ldelem.i1
0x129173  brtrue.s loc_1291BA
0x129175  ldarg.0
0x129176  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12917b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x129180  ldarg.0
0x129181  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3194_ListId
0x129186  bne.un.s loc_1291BA
0x129188  ldarg.0
0x129189  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12918e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x129193  ldarg.0
0x129194  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x129199  bne.un.s loc_1291BA
0x12919b  ldloc.2
0x12919c  ldarg.0
0x12919d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1291a2  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1291a7  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x1291ac  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QualifyMemberListRequest::set_ListId(valuetype [mscorlib]System.Guid)
0x1291b1  ldloc.3
0x1291b2  ldc.i4.1
0x1291b3  ldc.i4.1
0x1291b4  stelem.i1
0x1291b5  br       loc_129387
0x1291ba  ldarg.0
0x1291bb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1291c0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1291c5  ldarg.0
0x1291c6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3200_MembersId
0x1291cb  bne.un   loc_129326
0x1291d0  ldarg.0
0x1291d1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1291d6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1291db  ldarg.0
0x1291dc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1291e1  bne.un   loc_129326
0x1291e6  ldarg.0
0x1291e7  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1291ec  brtrue   loc_129387
0x1291f1  ldnull
0x1291f2  stloc.s  0xA
0x1291f4  ldc.i4.0
0x1291f5  stloc.s  0xB
0x1291f7  ldarg.0
0x1291f8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1291fd  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x129202  brfalse.s loc_129214
0x129204  ldarg.0
0x129205  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12920a  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x12920f  br       loc_129304
0x129214  ldarg.0
0x129215  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12921a  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x12921f  ldarg.0
0x129220  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129225  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12922a  pop
0x12922b  ldc.i4.0
0x12922c  stloc.s  0xC
0x12922e  ldarg.0
0x12922f  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x129234  stloc.s  0xD
0x129236  br       loc_1292DF
0x12923b  ldarg.0
0x12923c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129241  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x129246  ldc.i4.1
0x129247  bne.un.s loc_1292BD
0x129249  ldarg.0
0x12924a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12924f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x129254  ldarg.0
0x129255  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id308_guid
0x12925a  bne.un.s loc_1292AF
0x12925c  ldarg.0
0x12925d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x129262  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x129267  ldarg.0
0x129268  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x12926d  bne.un.s loc_1292AF
0x12926f  ldarg.0
0x129270  ldloc.s  0xA
0x129272  ldloc.s  0xB
0x129274  ldtoken  [mscorlib]System.Guid
0x129279  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12927e  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x129283  castclass valuetype [mscorlib]System.Guid[]
0x129288  stloc.s  0xA
0x12928a  ldloc.s  0xA
0x12928c  ldloc.s  0xB
0x12928e  dup
0x12928f  ldc.i4.1
  ... truncated ...
```
