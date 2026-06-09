# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read556_SendTemplateRequest

- ea: `0x1012f0`
- end: `0x101850`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read556_SendTemplateRequest`
- size: `1376`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0xdd390`
- `0xfabc0`
- `0x1012f0`

## string_xrefs

- `0x1014b8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1014c6`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1016f8`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x101706`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x1017fb`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:TemplateId, http://schemas.microsoft.com/crm/2007/WebServices:Sender, http://schemas.microsoft.com/crm/2007/WebServices:RecipientType, http://schemas.microsoft.com/crm/2007/WebServices:RecipientIds, http://schemas.microsoft.com/crm/2007/WebServices:RegardingType, http://schemas.microsoft.com/crm/2007/WebServices:RegardingId`
- `0x101809`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:TemplateId, http://schemas.microsoft.com/crm/2007/WebServices:Sender, http://schemas.microsoft.com/crm/2007/WebServices:RecipientType, http://schemas.microsoft.com/crm/2007/WebServices:RecipientIds, http://schemas.microsoft.com/crm/2007/WebServices:RegardingType, http://schemas.microsoft.com/crm/2007/WebServices:RegardingId`

## pseudocode

```c

```

## disassembly

```asm
0x1012f0  ldarg.2
0x1012f1  brtrue.s loc_1012F6
0x1012f3  ldnull
0x1012f4  br.s     loc_1012FC
0x1012f6  ldarg.0
0x1012f7  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x1012fc  stloc.0
0x1012fd  ldc.i4.0
0x1012fe  stloc.1
0x1012ff  ldarg.1
0x101300  brfalse.s loc_101309
0x101302  ldarg.0
0x101303  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x101308  stloc.1
0x101309  ldarg.2
0x10130a  brfalse.s loc_101339
0x10130c  ldloc.0
0x10130d  ldnull
0x10130e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x101313  brtrue.s loc_101339
0x101315  ldloc.0
0x101316  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x10131b  ldarg.0
0x10131c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1597_SendTemplateRequest
0x101321  bne.un.s loc_101331
0x101323  ldloc.0
0x101324  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x101329  ldarg.0
0x10132a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x10132f  beq.s    loc_101339
0x101331  ldarg.0
0x101332  ldloc.0
0x101333  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x101338  throw
0x101339  ldloc.1
0x10133a  brfalse.s loc_10133E
0x10133c  ldnull
0x10133d  ret
0x10133e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::.ctor()
0x101343  stloc.2
0x101344  ldc.i4.7
0x101345  newarr   [mscorlib]System.Boolean
0x10134a  stloc.3
0x10134b  br.s     loc_101367
0x10134d  ldarg.0
0x10134e  ldarg.0
0x10134f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101354  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x101359  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x10135e  brtrue.s loc_101367
0x101360  ldarg.0
0x101361  ldloc.2
0x101362  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x101367  ldarg.0
0x101368  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10136d  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x101372  brtrue.s loc_10134D
0x101374  ldarg.0
0x101375  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10137a  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x10137f  pop
0x101380  ldarg.0
0x101381  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101386  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x10138b  brfalse.s loc_10139A
0x10138d  ldarg.0
0x10138e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101393  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x101398  ldloc.2
0x101399  ret
0x10139a  ldarg.0
0x10139b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1013a0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x1013a5  ldarg.0
0x1013a6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1013ab  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1013b0  pop
0x1013b1  ldc.i4.0
0x1013b2  stloc.s  4
0x1013b4  ldarg.0
0x1013b5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x1013ba  stloc.s  5
0x1013bc  br       loc_101829
0x1013c1  ldarg.0
0x1013c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1013c7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1013cc  ldc.i4.1
0x1013cd  bne.un   loc_101807
0x1013d2  ldarg.0
0x1013d3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1013d8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1013dd  ldarg.0
0x1013de  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x1013e3  bne.un   loc_101530
0x1013e8  ldarg.0
0x1013e9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1013ee  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1013f3  ldarg.0
0x1013f4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1013f9  bne.un   loc_101530
0x1013fe  ldarg.0
0x1013ff  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x101404  brtrue   loc_101813
0x101409  ldnull
0x10140a  stloc.s  6
0x10140c  ldc.i4.0
0x10140d  stloc.s  7
0x10140f  ldarg.0
0x101410  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101415  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x10141a  brfalse.s loc_10142C
0x10141c  ldarg.0
0x10141d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101422  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x101427  br       loc_10150B
0x10142c  ldarg.0
0x10142d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101432  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x101437  ldarg.0
0x101438  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10143d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x101442  pop
0x101443  ldc.i4.0
0x101444  stloc.s  8
0x101446  ldarg.0
0x101447  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x10144c  stloc.s  9
0x10144e  br       loc_1014E6
0x101453  ldarg.0
0x101454  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101459  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x10145e  ldc.i4.1
0x10145f  bne.un.s loc_1014C4
0x101461  ldarg.0
0x101462  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101467  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10146c  ldarg.0
0x10146d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x101472  bne.un.s loc_1014B6
0x101474  ldarg.0
0x101475  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10147a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x10147f  ldarg.0
0x101480  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x101485  bne.un.s loc_1014B6
0x101487  ldarg.0
0x101488  ldloc.s  6
0x10148a  ldloc.s  7
0x10148c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x101491  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x101496  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x10149b  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x1014a0  stloc.s  6
0x1014a2  ldloc.s  6
0x1014a4  ldloc.s  7
0x1014a6  dup
0x1014a7  ldc.i4.1
0x1014a8  add
0x1014a9  stloc.s  7
0x1014ab  ldarg.0
0x1014ac  ldc.i4.1
0x1014ad  ldc.i4.1
0x1014ae  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x1014b3  stelem.ref
0x1014b4  br.s     loc_1014D0
0x1014b6  ldarg.0
0x1014b7  ldnull
0x1014b8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x1014bd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x1014c2  br.s     loc_1014D0
0x1014c4  ldarg.0
0x1014c5  ldnull
0x1014c6  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x1014cb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x1014d0  ldarg.0
0x1014d1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1014d6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1014db  pop
0x1014dc  ldarg.0
0x1014dd  ldloca.s 8
0x1014df  ldloca.s 9
0x1014e1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x1014e6  ldarg.0
0x1014e7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1014ec  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1014f1  ldc.i4.s 0xF
0x1014f3  beq.s    loc_101505
0x1014f5  ldarg.0
0x1014f6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1014fb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x101500  brtrue   loc_101453
0x101505  ldarg.0
0x101506  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x10150b  ldloc.2
0x10150c  ldarg.0
0x10150d  ldloc.s  6
0x10150f  ldloc.s  7
0x101511  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x101516  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10151b  ldc.i4.0
0x10151c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x101521  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x101526  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x10152b  br       loc_101813
0x101530  ldloc.3
0x101531  ldc.i4.1
0x101532  ldelem.i1
0x101533  brtrue.s loc_10157A
0x101535  ldarg.0
0x101536  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10153b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x101540  ldarg.0
0x101541  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3140_TemplateId
0x101546  bne.un.s loc_10157A
0x101548  ldarg.0
0x101549  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10154e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x101553  ldarg.0
0x101554  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x101559  bne.un.s loc_10157A
0x10155b  ldloc.2
0x10155c  ldarg.0
0x10155d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101562  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x101567  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x10156c  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::set_TemplateId(valuetype [mscorlib]System.Guid)
0x101571  ldloc.3
0x101572  ldc.i4.1
0x101573  ldc.i4.1
0x101574  stelem.i1
0x101575  br       loc_101813
0x10157a  ldloc.3
0x10157b  ldc.i4.2
0x10157c  ldelem.i1
0x10157d  brtrue.s loc_1015BC
0x10157f  ldarg.0
0x101580  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101585  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10158a  ldarg.0
0x10158b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3141_Sender
0x101590  bne.un.s loc_1015BC
0x101592  ldarg.0
0x101593  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101598  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x10159d  ldarg.0
0x10159e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1015a3  bne.un.s loc_1015BC
0x1015a5  ldloc.2
0x1015a6  ldarg.0
0x1015a7  ldc.i4.0
0x1015a8  ldc.i4.1
0x1015a9  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read515_Moniker(bool isNullable, bool checkType)
0x1015ae  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::set_Sender(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker)
0x1015b3  ldloc.3
0x1015b4  ldc.i4.2
0x1015b5  ldc.i4.1
0x1015b6  stelem.i1
0x1015b7  br       loc_101813
0x1015bc  ldloc.3
0x1015bd  ldc.i4.3
0x1015be  ldelem.i1
0x1015bf  brtrue.s loc_101601
0x1015c1  ldarg.0
0x1015c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1015c7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1015cc  ldarg.0
0x1015cd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3142_RecipientType
0x1015d2  bne.un.s loc_101601
0x1015d4  ldarg.0
0x1015d5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1015da  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1015df  ldarg.0
0x1015e0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1015e5  bne.un.s loc_101601
0x1015e7  ldloc.2
0x1015e8  ldarg.0
0x1015e9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1015ee  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1015f3  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SendTemplateRequest::set_RecipientType(string)
0x1015f8  ldloc.3
0x1015f9  ldc.i4.3
0x1015fa  ldc.i4.1
0x1015fb  stelem.i1
0x1015fc  br       loc_101813
0x101601  ldarg.0
0x101602  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x101607  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10160c  ldarg.0
0x10160d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3143_RecipientIds
0x101612  bne.un   loc_101770
0x101617  ldarg.0
0x101618  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10161d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x101622  ldarg.0
0x101623  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x101628  bne.un   loc_101770
0x10162d  ldarg.0
0x10162e  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x101633  brtrue   loc_101813
0x101638  ldnull
  ... truncated ...
```
