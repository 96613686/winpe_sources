# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read549_SetLocLabelsRequest

- ea: `0x100100`
- end: `0x100579`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read549_SetLocLabelsRequest`
- size: `1145`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0x798a0`
- `0xdd390`
- `0xfabc0`
- `0x100100`

## string_xrefs

- `0x1004ad`: `http://schemas.microsoft.com/crm/2007/WebServices:LocLabel`
- `0x1004bb`: `http://schemas.microsoft.com/crm/2007/WebServices:LocLabel`
- `0x1002c8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1002d6`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x100524`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:EntityMoniker, http://schemas.microsoft.com/crm/2007/WebServices:AttributeName, http://schemas.microsoft.com/crm/2007/WebServices:Labels`
- `0x100532`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:EntityMoniker, http://schemas.microsoft.com/crm/2007/WebServices:AttributeName, http://schemas.microsoft.com/crm/2007/WebServices:Labels`

## pseudocode

```c

```

## disassembly

```asm
0x100100  ldarg.2
0x100101  brtrue.s loc_100106
0x100103  ldnull
0x100104  br.s     loc_10010C
0x100106  ldarg.0
0x100107  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x10010c  stloc.0
0x10010d  ldc.i4.0
0x10010e  stloc.1
0x10010f  ldarg.1
0x100110  brfalse.s loc_100119
0x100112  ldarg.0
0x100113  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x100118  stloc.1
0x100119  ldarg.2
0x10011a  brfalse.s loc_100149
0x10011c  ldloc.0
0x10011d  ldnull
0x10011e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x100123  brtrue.s loc_100149
0x100125  ldloc.0
0x100126  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x10012b  ldarg.0
0x10012c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1602_SetLocLabelsRequest
0x100131  bne.un.s loc_100141
0x100133  ldloc.0
0x100134  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x100139  ldarg.0
0x10013a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x10013f  beq.s    loc_100149
0x100141  ldarg.0
0x100142  ldloc.0
0x100143  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x100148  throw
0x100149  ldloc.1
0x10014a  brfalse.s loc_10014E
0x10014c  ldnull
0x10014d  ret
0x10014e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetLocLabelsRequest::.ctor()
0x100153  stloc.2
0x100154  ldc.i4.4
0x100155  newarr   [mscorlib]System.Boolean
0x10015a  stloc.3
0x10015b  br.s     loc_100177
0x10015d  ldarg.0
0x10015e  ldarg.0
0x10015f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100164  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x100169  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x10016e  brtrue.s loc_100177
0x100170  ldarg.0
0x100171  ldloc.2
0x100172  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x100177  ldarg.0
0x100178  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10017d  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x100182  brtrue.s loc_10015D
0x100184  ldarg.0
0x100185  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10018a  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x10018f  pop
0x100190  ldarg.0
0x100191  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100196  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x10019b  brfalse.s loc_1001AA
0x10019d  ldarg.0
0x10019e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1001a3  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x1001a8  ldloc.2
0x1001a9  ret
0x1001aa  ldarg.0
0x1001ab  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1001b0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x1001b5  ldarg.0
0x1001b6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1001bb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1001c0  pop
0x1001c1  ldc.i4.0
0x1001c2  stloc.s  4
0x1001c4  ldarg.0
0x1001c5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x1001ca  stloc.s  5
0x1001cc  br       loc_100552
0x1001d1  ldarg.0
0x1001d2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1001d7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1001dc  ldc.i4.1
0x1001dd  bne.un   loc_100530
0x1001e2  ldarg.0
0x1001e3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1001e8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1001ed  ldarg.0
0x1001ee  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x1001f3  bne.un   loc_100340
0x1001f8  ldarg.0
0x1001f9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1001fe  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x100203  ldarg.0
0x100204  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x100209  bne.un   loc_100340
0x10020e  ldarg.0
0x10020f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x100214  brtrue   loc_10053C
0x100219  ldnull
0x10021a  stloc.s  6
0x10021c  ldc.i4.0
0x10021d  stloc.s  7
0x10021f  ldarg.0
0x100220  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100225  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x10022a  brfalse.s loc_10023C
0x10022c  ldarg.0
0x10022d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100232  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x100237  br       loc_10031B
0x10023c  ldarg.0
0x10023d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100242  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x100247  ldarg.0
0x100248  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10024d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x100252  pop
0x100253  ldc.i4.0
0x100254  stloc.s  8
0x100256  ldarg.0
0x100257  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x10025c  stloc.s  9
0x10025e  br       loc_1002F6
0x100263  ldarg.0
0x100264  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100269  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x10026e  ldc.i4.1
0x10026f  bne.un.s loc_1002D4
0x100271  ldarg.0
0x100272  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100277  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10027c  ldarg.0
0x10027d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x100282  bne.un.s loc_1002C6
0x100284  ldarg.0
0x100285  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10028a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x10028f  ldarg.0
0x100290  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x100295  bne.un.s loc_1002C6
0x100297  ldarg.0
0x100298  ldloc.s  6
0x10029a  ldloc.s  7
0x10029c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x1002a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1002a6  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x1002ab  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x1002b0  stloc.s  6
0x1002b2  ldloc.s  6
0x1002b4  ldloc.s  7
0x1002b6  dup
0x1002b7  ldc.i4.1
0x1002b8  add
0x1002b9  stloc.s  7
0x1002bb  ldarg.0
0x1002bc  ldc.i4.1
0x1002bd  ldc.i4.1
0x1002be  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x1002c3  stelem.ref
0x1002c4  br.s     loc_1002E0
0x1002c6  ldarg.0
0x1002c7  ldnull
0x1002c8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x1002cd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x1002d2  br.s     loc_1002E0
0x1002d4  ldarg.0
0x1002d5  ldnull
0x1002d6  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x1002db  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x1002e0  ldarg.0
0x1002e1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1002e6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1002eb  pop
0x1002ec  ldarg.0
0x1002ed  ldloca.s 8
0x1002ef  ldloca.s 9
0x1002f1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x1002f6  ldarg.0
0x1002f7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1002fc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x100301  ldc.i4.s 0xF
0x100303  beq.s    loc_100315
0x100305  ldarg.0
0x100306  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10030b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x100310  brtrue   loc_100263
0x100315  ldarg.0
0x100316  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x10031b  ldloc.2
0x10031c  ldarg.0
0x10031d  ldloc.s  6
0x10031f  ldloc.s  7
0x100321  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x100326  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10032b  ldc.i4.0
0x10032c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x100331  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x100336  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x10033b  br       loc_10053C
0x100340  ldloc.3
0x100341  ldc.i4.1
0x100342  ldelem.i1
0x100343  brtrue.s loc_100382
0x100345  ldarg.0
0x100346  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10034b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x100350  ldarg.0
0x100351  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3132_EntityMoniker
0x100356  bne.un.s loc_100382
0x100358  ldarg.0
0x100359  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10035e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x100363  ldarg.0
0x100364  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x100369  bne.un.s loc_100382
0x10036b  ldloc.2
0x10036c  ldarg.0
0x10036d  ldc.i4.0
0x10036e  ldc.i4.1
0x10036f  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read515_Moniker(bool isNullable, bool checkType)
0x100374  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetLocLabelsRequest::set_EntityMoniker(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker)
0x100379  ldloc.3
0x10037a  ldc.i4.1
0x10037b  ldc.i4.1
0x10037c  stelem.i1
0x10037d  br       loc_10053C
0x100382  ldloc.3
0x100383  ldc.i4.2
0x100384  ldelem.i1
0x100385  brtrue.s loc_1003C7
0x100387  ldarg.0
0x100388  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10038d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x100392  ldarg.0
0x100393  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id429_AttributeName
0x100398  bne.un.s loc_1003C7
0x10039a  ldarg.0
0x10039b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1003a0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1003a5  ldarg.0
0x1003a6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1003ab  bne.un.s loc_1003C7
0x1003ad  ldloc.2
0x1003ae  ldarg.0
0x1003af  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1003b4  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1003b9  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetLocLabelsRequest::set_AttributeName(string)
0x1003be  ldloc.3
0x1003bf  ldc.i4.2
0x1003c0  ldc.i4.1
0x1003c1  stelem.i1
0x1003c2  br       loc_10053C
0x1003c7  ldarg.0
0x1003c8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1003cd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1003d2  ldarg.0
0x1003d3  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3133_Labels
0x1003d8  bne.un   loc_100522
0x1003dd  ldarg.0
0x1003de  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1003e3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1003e8  ldarg.0
0x1003e9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1003ee  bne.un   loc_100522
0x1003f3  ldarg.0
0x1003f4  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1003f9  brtrue   loc_10053C
0x1003fe  ldnull
0x1003ff  stloc.s  0xA
0x100401  ldc.i4.0
0x100402  stloc.s  0xB
0x100404  ldarg.0
0x100405  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10040a  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x10040f  brfalse.s loc_100421
0x100411  ldarg.0
0x100412  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100417  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x10041c  br       loc_100500
0x100421  ldarg.0
0x100422  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100427  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x10042c  ldarg.0
0x10042d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x100432  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x100437  pop
0x100438  ldc.i4.0
0x100439  stloc.s  0xC
0x10043b  ldarg.0
0x10043c  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x100441  stloc.s  0xD
0x100443  br       loc_1004DB
0x100448  ldarg.0
0x100449  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10044e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
  ... truncated ...
```
