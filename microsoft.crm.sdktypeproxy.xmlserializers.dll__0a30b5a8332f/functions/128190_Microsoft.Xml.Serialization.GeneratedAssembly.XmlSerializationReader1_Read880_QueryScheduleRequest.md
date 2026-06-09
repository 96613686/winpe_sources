# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read880_QueryScheduleRequest

- ea: `0x128190`
- end: `0x128659`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read880_QueryScheduleRequest`
- size: `1225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0x795d0`
- `0x79630`
- `0xdd390`
- `0x128190`

## string_xrefs

- `0x128358`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x128366`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x12858d`: `http://schemas.microsoft.com/crm/2007/WebServices:TimeCode`
- `0x12859b`: `http://schemas.microsoft.com/crm/2007/WebServices:TimeCode`
- `0x128604`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ResourceId, http://schemas.microsoft.com/crm/2007/WebServices:Start, http://schemas.microsoft.com/crm/2007/WebServices:End, http://schemas.microsoft.com/crm/2007/WebServices:TimeCodes`
- `0x128612`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ResourceId, http://schemas.microsoft.com/crm/2007/WebServices:Start, http://schemas.microsoft.com/crm/2007/WebServices:End, http://schemas.microsoft.com/crm/2007/WebServices:TimeCodes`

## pseudocode

```c

```

## disassembly

```asm
0x128190  ldarg.2
0x128191  brtrue.s loc_128196
0x128193  ldnull
0x128194  br.s     loc_12819C
0x128196  ldarg.0
0x128197  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x12819c  stloc.0
0x12819d  ldc.i4.0
0x12819e  stloc.1
0x12819f  ldarg.1
0x1281a0  brfalse.s loc_1281A9
0x1281a2  ldarg.0
0x1281a3  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1281a8  stloc.1
0x1281a9  ldarg.2
0x1281aa  brfalse.s loc_1281D9
0x1281ac  ldloc.0
0x1281ad  ldnull
0x1281ae  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x1281b3  brtrue.s loc_1281D9
0x1281b5  ldloc.0
0x1281b6  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x1281bb  ldarg.0
0x1281bc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1522_QueryScheduleRequest
0x1281c1  bne.un.s loc_1281D1
0x1281c3  ldloc.0
0x1281c4  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1281c9  ldarg.0
0x1281ca  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1281cf  beq.s    loc_1281D9
0x1281d1  ldarg.0
0x1281d2  ldloc.0
0x1281d3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x1281d8  throw
0x1281d9  ldloc.1
0x1281da  brfalse.s loc_1281DE
0x1281dc  ldnull
0x1281dd  ret
0x1281de  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::.ctor()
0x1281e3  stloc.2
0x1281e4  ldc.i4.5
0x1281e5  newarr   [mscorlib]System.Boolean
0x1281ea  stloc.3
0x1281eb  br.s     loc_128207
0x1281ed  ldarg.0
0x1281ee  ldarg.0
0x1281ef  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1281f4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x1281f9  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x1281fe  brtrue.s loc_128207
0x128200  ldarg.0
0x128201  ldloc.2
0x128202  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x128207  ldarg.0
0x128208  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12820d  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x128212  brtrue.s loc_1281ED
0x128214  ldarg.0
0x128215  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12821a  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x12821f  pop
0x128220  ldarg.0
0x128221  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128226  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x12822b  brfalse.s loc_12823A
0x12822d  ldarg.0
0x12822e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128233  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x128238  ldloc.2
0x128239  ret
0x12823a  ldarg.0
0x12823b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128240  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x128245  ldarg.0
0x128246  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12824b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x128250  pop
0x128251  ldc.i4.0
0x128252  stloc.s  4
0x128254  ldarg.0
0x128255  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x12825a  stloc.s  5
0x12825c  br       loc_128632
0x128261  ldarg.0
0x128262  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128267  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x12826c  ldc.i4.1
0x12826d  bne.un   loc_128610
0x128272  ldarg.0
0x128273  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128278  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12827d  ldarg.0
0x12827e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x128283  bne.un   loc_1283D0
0x128288  ldarg.0
0x128289  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12828e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x128293  ldarg.0
0x128294  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x128299  bne.un   loc_1283D0
0x12829e  ldarg.0
0x12829f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1282a4  brtrue   loc_12861C
0x1282a9  ldnull
0x1282aa  stloc.s  6
0x1282ac  ldc.i4.0
0x1282ad  stloc.s  7
0x1282af  ldarg.0
0x1282b0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1282b5  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1282ba  brfalse.s loc_1282CC
0x1282bc  ldarg.0
0x1282bd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1282c2  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x1282c7  br       loc_1283AB
0x1282cc  ldarg.0
0x1282cd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1282d2  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x1282d7  ldarg.0
0x1282d8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1282dd  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1282e2  pop
0x1282e3  ldc.i4.0
0x1282e4  stloc.s  8
0x1282e6  ldarg.0
0x1282e7  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x1282ec  stloc.s  9
0x1282ee  br       loc_128386
0x1282f3  ldarg.0
0x1282f4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1282f9  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1282fe  ldc.i4.1
0x1282ff  bne.un.s loc_128364
0x128301  ldarg.0
0x128302  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128307  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12830c  ldarg.0
0x12830d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x128312  bne.un.s loc_128356
0x128314  ldarg.0
0x128315  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12831a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12831f  ldarg.0
0x128320  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x128325  bne.un.s loc_128356
0x128327  ldarg.0
0x128328  ldloc.s  6
0x12832a  ldloc.s  7
0x12832c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x128331  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x128336  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x12833b  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x128340  stloc.s  6
0x128342  ldloc.s  6
0x128344  ldloc.s  7
0x128346  dup
0x128347  ldc.i4.1
0x128348  add
0x128349  stloc.s  7
0x12834b  ldarg.0
0x12834c  ldc.i4.1
0x12834d  ldc.i4.1
0x12834e  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x128353  stelem.ref
0x128354  br.s     loc_128370
0x128356  ldarg.0
0x128357  ldnull
0x128358  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x12835d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x128362  br.s     loc_128370
0x128364  ldarg.0
0x128365  ldnull
0x128366  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x12836b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x128370  ldarg.0
0x128371  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128376  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12837b  pop
0x12837c  ldarg.0
0x12837d  ldloca.s 8
0x12837f  ldloca.s 9
0x128381  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x128386  ldarg.0
0x128387  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12838c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x128391  ldc.i4.s 0xF
0x128393  beq.s    loc_1283A5
0x128395  ldarg.0
0x128396  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12839b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1283a0  brtrue   loc_1282F3
0x1283a5  ldarg.0
0x1283a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x1283ab  ldloc.2
0x1283ac  ldarg.0
0x1283ad  ldloc.s  6
0x1283af  ldloc.s  7
0x1283b1  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x1283b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1283bb  ldc.i4.0
0x1283bc  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x1283c1  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x1283c6  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x1283cb  br       loc_12861C
0x1283d0  ldloc.3
0x1283d1  ldc.i4.1
0x1283d2  ldelem.i1
0x1283d3  brtrue.s loc_12841A
0x1283d5  ldarg.0
0x1283d6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1283db  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1283e0  ldarg.0
0x1283e1  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id410_ResourceId
0x1283e6  bne.un.s loc_12841A
0x1283e8  ldarg.0
0x1283e9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1283ee  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1283f3  ldarg.0
0x1283f4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1283f9  bne.un.s loc_12841A
0x1283fb  ldloc.2
0x1283fc  ldarg.0
0x1283fd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128402  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x128407  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x12840c  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::set_ResourceId(valuetype [mscorlib]System.Guid)
0x128411  ldloc.3
0x128412  ldc.i4.1
0x128413  ldc.i4.1
0x128414  stelem.i1
0x128415  br       loc_12861C
0x12841a  ldloc.3
0x12841b  ldc.i4.2
0x12841c  ldelem.i1
0x12841d  brtrue.s loc_12845C
0x12841f  ldarg.0
0x128420  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128425  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12842a  ldarg.0
0x12842b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id392_Start
0x128430  bne.un.s loc_12845C
0x128432  ldarg.0
0x128433  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128438  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12843d  ldarg.0
0x12843e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x128443  bne.un.s loc_12845C
0x128445  ldloc.2
0x128446  ldarg.0
0x128447  ldc.i4.0
0x128448  ldc.i4.1
0x128449  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0x12844e  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::set_Start(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0x128453  ldloc.3
0x128454  ldc.i4.2
0x128455  ldc.i4.1
0x128456  stelem.i1
0x128457  br       loc_12861C
0x12845c  ldloc.3
0x12845d  ldc.i4.3
0x12845e  ldelem.i1
0x12845f  brtrue.s loc_12849E
0x128461  ldarg.0
0x128462  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128467  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12846c  ldarg.0
0x12846d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id393_End
0x128472  bne.un.s loc_12849E
0x128474  ldarg.0
0x128475  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12847a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12847f  ldarg.0
0x128480  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x128485  bne.un.s loc_12849E
0x128487  ldloc.2
0x128488  ldarg.0
0x128489  ldc.i4.0
0x12848a  ldc.i4.1
0x12848b  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0x128490  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::set_End(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0x128495  ldloc.3
0x128496  ldc.i4.3
0x128497  ldc.i4.1
0x128498  stelem.i1
0x128499  br       loc_12861C
0x12849e  ldarg.0
0x12849f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1284a4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1284a9  ldarg.0
0x1284aa  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3199_TimeCodes
0x1284af  bne.un   loc_128602
0x1284b4  ldarg.0
0x1284b5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1284ba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1284bf  ldarg.0
0x1284c0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1284c5  bne.un   loc_128602
0x1284ca  ldarg.0
0x1284cb  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1284d0  brtrue   loc_12861C
  ... truncated ...
```
