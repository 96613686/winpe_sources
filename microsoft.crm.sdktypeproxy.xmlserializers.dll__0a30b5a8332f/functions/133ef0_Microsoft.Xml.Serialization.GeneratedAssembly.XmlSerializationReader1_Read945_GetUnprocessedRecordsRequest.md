# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read945_GetUnprocessedRecordsRequest

- ea: `0x133ef0`
- end: `0x13443a`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read945_GetUnprocessedRecordsRequest`
- size: `1354`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0xdd390`
- `0x133ef0`

## string_xrefs

- `0x1342dd`: `http://schemas.microsoft.com/crm/2007/WebServices:string`
- `0x1342eb`: `http://schemas.microsoft.com/crm/2007/WebServices:string`
- `0x134104`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x134112`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1343e5`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:EntityName, http://schemas.microsoft.com/crm/2007/WebServices:Columns, http://schemas.microsoft.com/crm/2007/WebServices:RuleId, http://schemas.microsoft.com/crm/2007/WebServices:PageSize`
- `0x1343f3`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:EntityName, http://schemas.microsoft.com/crm/2007/WebServices:Columns, http://schemas.microsoft.com/crm/2007/WebServices:RuleId, http://schemas.microsoft.com/crm/2007/WebServices:PageSize`

## pseudocode

```c

```

## disassembly

```asm
0x133ef0  ldarg.2
0x133ef1  brtrue.s loc_133EF6
0x133ef3  ldnull
0x133ef4  br.s     loc_133EFC
0x133ef6  ldarg.0
0x133ef7  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x133efc  stloc.0
0x133efd  ldc.i4.0
0x133efe  stloc.1
0x133eff  ldarg.1
0x133f00  brfalse.s loc_133F09
0x133f02  ldarg.0
0x133f03  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x133f08  stloc.1
0x133f09  ldarg.2
0x133f0a  brfalse.s loc_133F39
0x133f0c  ldloc.0
0x133f0d  ldnull
0x133f0e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x133f13  brtrue.s loc_133F39
0x133f15  ldloc.0
0x133f16  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x133f1b  ldarg.0
0x133f1c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1467_GetUnprocessedRecordsRequest
0x133f21  bne.un.s loc_133F31
0x133f23  ldloc.0
0x133f24  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x133f29  ldarg.0
0x133f2a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x133f2f  beq.s    loc_133F39
0x133f31  ldarg.0
0x133f32  ldloc.0
0x133f33  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x133f38  throw
0x133f39  ldloc.1
0x133f3a  brfalse.s loc_133F3E
0x133f3c  ldnull
0x133f3d  ret
0x133f3e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::.ctor()
0x133f43  stloc.2
0x133f44  ldc.i4.6
0x133f45  newarr   [mscorlib]System.Boolean
0x133f4a  stloc.3
0x133f4b  br.s     loc_133FB3
0x133f4d  ldloc.3
0x133f4e  ldc.i4.5
0x133f4f  ldelem.i1
0x133f50  brtrue.s loc_133F94
0x133f52  ldarg.0
0x133f53  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133f58  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x133f5d  ldarg.0
0x133f5e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3166_ReturnDynamicEntities
0x133f63  bne.un.s loc_133F94
0x133f65  ldarg.0
0x133f66  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133f6b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x133f70  ldarg.0
0x133f71  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id85_Item
0x133f76  bne.un.s loc_133F94
0x133f78  ldloc.2
0x133f79  ldarg.0
0x133f7a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133f7f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x133f84  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x133f89  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::set_ReturnDynamicEntities(bool)
0x133f8e  ldloc.3
0x133f8f  ldc.i4.5
0x133f90  ldc.i4.1
0x133f91  stelem.i1
0x133f92  br.s     loc_133FB3
0x133f94  ldarg.0
0x133f95  ldarg.0
0x133f96  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133f9b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x133fa0  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x133fa5  brtrue.s loc_133FB3
0x133fa7  ldarg.0
0x133fa8  ldloc.2
0x133fa9  ldstr    aReturndynamice_0// ":ReturnDynamicEntities"
0x133fae  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x133fb3  ldarg.0
0x133fb4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133fb9  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x133fbe  brtrue.s loc_133F4D
0x133fc0  ldarg.0
0x133fc1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133fc6  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x133fcb  pop
0x133fcc  ldarg.0
0x133fcd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133fd2  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x133fd7  brfalse.s loc_133FE6
0x133fd9  ldarg.0
0x133fda  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133fdf  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x133fe4  ldloc.2
0x133fe5  ret
0x133fe6  ldarg.0
0x133fe7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133fec  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x133ff1  ldarg.0
0x133ff2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x133ff7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x133ffc  pop
0x133ffd  ldc.i4.0
0x133ffe  stloc.s  4
0x134000  ldarg.0
0x134001  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x134006  stloc.s  5
0x134008  br       loc_134413
0x13400d  ldarg.0
0x13400e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134013  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x134018  ldc.i4.1
0x134019  bne.un   loc_1343F1
0x13401e  ldarg.0
0x13401f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134024  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x134029  ldarg.0
0x13402a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x13402f  bne.un   loc_13417C
0x134034  ldarg.0
0x134035  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x13403a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x13403f  ldarg.0
0x134040  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x134045  bne.un   loc_13417C
0x13404a  ldarg.0
0x13404b  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x134050  brtrue   loc_1343FD
0x134055  ldnull
0x134056  stloc.s  6
0x134058  ldc.i4.0
0x134059  stloc.s  7
0x13405b  ldarg.0
0x13405c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134061  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x134066  brfalse.s loc_134078
0x134068  ldarg.0
0x134069  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x13406e  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x134073  br       loc_134157
0x134078  ldarg.0
0x134079  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x13407e  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x134083  ldarg.0
0x134084  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134089  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x13408e  pop
0x13408f  ldc.i4.0
0x134090  stloc.s  8
0x134092  ldarg.0
0x134093  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x134098  stloc.s  9
0x13409a  br       loc_134132
0x13409f  ldarg.0
0x1340a0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1340a5  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1340aa  ldc.i4.1
0x1340ab  bne.un.s loc_134110
0x1340ad  ldarg.0
0x1340ae  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1340b3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1340b8  ldarg.0
0x1340b9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x1340be  bne.un.s loc_134102
0x1340c0  ldarg.0
0x1340c1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1340c6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1340cb  ldarg.0
0x1340cc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1340d1  bne.un.s loc_134102
0x1340d3  ldarg.0
0x1340d4  ldloc.s  6
0x1340d6  ldloc.s  7
0x1340d8  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x1340dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1340e2  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x1340e7  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x1340ec  stloc.s  6
0x1340ee  ldloc.s  6
0x1340f0  ldloc.s  7
0x1340f2  dup
0x1340f3  ldc.i4.1
0x1340f4  add
0x1340f5  stloc.s  7
0x1340f7  ldarg.0
0x1340f8  ldc.i4.1
0x1340f9  ldc.i4.1
0x1340fa  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x1340ff  stelem.ref
0x134100  br.s     loc_13411C
0x134102  ldarg.0
0x134103  ldnull
0x134104  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x134109  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x13410e  br.s     loc_13411C
0x134110  ldarg.0
0x134111  ldnull
0x134112  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x134117  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x13411c  ldarg.0
0x13411d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134122  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x134127  pop
0x134128  ldarg.0
0x134129  ldloca.s 8
0x13412b  ldloca.s 9
0x13412d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x134132  ldarg.0
0x134133  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134138  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x13413d  ldc.i4.s 0xF
0x13413f  beq.s    loc_134151
0x134141  ldarg.0
0x134142  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134147  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x13414c  brtrue   loc_13409F
0x134151  ldarg.0
0x134152  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x134157  ldloc.2
0x134158  ldarg.0
0x134159  ldloc.s  6
0x13415b  ldloc.s  7
0x13415d  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x134162  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x134167  ldc.i4.0
0x134168  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x13416d  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x134172  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x134177  br       loc_1343FD
0x13417c  ldloc.3
0x13417d  ldc.i4.1
0x13417e  ldelem.i1
0x13417f  brtrue.s loc_1341C1
0x134181  ldarg.0
0x134182  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134187  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x13418c  ldarg.0
0x13418d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id337_EntityName
0x134192  bne.un.s loc_1341C1
0x134194  ldarg.0
0x134195  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x13419a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x13419f  ldarg.0
0x1341a0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1341a5  bne.un.s loc_1341C1
0x1341a7  ldloc.2
0x1341a8  ldarg.0
0x1341a9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1341ae  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1341b3  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetUnprocessedRecordsRequest::set_EntityName(string)
0x1341b8  ldloc.3
0x1341b9  ldc.i4.1
0x1341ba  ldc.i4.1
0x1341bb  stelem.i1
0x1341bc  br       loc_1343FD
0x1341c1  ldarg.0
0x1341c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1341c7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1341cc  ldarg.0
0x1341cd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3235_Columns
0x1341d2  bne.un   loc_134355
0x1341d7  ldarg.0
0x1341d8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1341dd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1341e2  ldarg.0
0x1341e3  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1341e8  bne.un   loc_134355
0x1341ed  ldarg.0
0x1341ee  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1341f3  brtrue   loc_1343FD
0x1341f8  ldnull
0x1341f9  stloc.s  0xA
0x1341fb  ldc.i4.0
0x1341fc  stloc.s  0xB
0x1341fe  ldarg.0
0x1341ff  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134204  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x134209  brfalse.s loc_13421B
0x13420b  ldarg.0
0x13420c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134211  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x134216  br       loc_134330
0x13421b  ldarg.0
0x13421c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x134221  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x134226  ldarg.0
0x134227  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x13422c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x134231  pop
0x134232  ldc.i4.0
0x134233  stloc.s  0xC
0x134235  ldarg.0
0x134236  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x13423b  stloc.s  0xD
0x13423d  br       loc_13430B
0x134242  ldarg.0
0x134243  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
  ... truncated ...
```
