# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read843_Item

- ea: `0x122270`
- end: `0x1226fe`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read843_Item`
- size: `1166`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0x7b120`
- `0xdd390`
- `0x122270`

## string_xrefs

- `0x122484`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x122492`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1225f3`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x122601`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x1226a9`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ResourceIds, http://schemas.microsoft.com/crm/2007/WebServices:Query`
- `0x1226b7`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ResourceIds, http://schemas.microsoft.com/crm/2007/WebServices:Query`

## pseudocode

```c

```

## disassembly

```asm
0x122270  ldarg.2
0x122271  brtrue.s loc_122276
0x122273  ldnull
0x122274  br.s     loc_12227C
0x122276  ldarg.0
0x122277  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x12227c  stloc.0
0x12227d  ldc.i4.0
0x12227e  stloc.1
0x12227f  ldarg.1
0x122280  brfalse.s loc_122289
0x122282  ldarg.0
0x122283  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x122288  stloc.1
0x122289  ldarg.2
0x12228a  brfalse.s loc_1222B9
0x12228c  ldloc.0
0x12228d  ldnull
0x12228e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x122293  brtrue.s loc_1222B9
0x122295  ldloc.0
0x122296  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x12229b  ldarg.0
0x12229c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1547_Item
0x1222a1  bne.un.s loc_1222B1
0x1222a3  ldloc.0
0x1222a4  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x1222a9  ldarg.0
0x1222aa  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1222af  beq.s    loc_1222B9
0x1222b1  ldarg.0
0x1222b2  ldloc.0
0x1222b3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x1222b8  throw
0x1222b9  ldloc.1
0x1222ba  brfalse.s loc_1222BE
0x1222bc  ldnull
0x1222bd  ret
0x1222be  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveByResourcesServiceRequest::.ctor()
0x1222c3  stloc.2
0x1222c4  ldc.i4.4
0x1222c5  newarr   [mscorlib]System.Boolean
0x1222ca  stloc.3
0x1222cb  br.s     loc_122333
0x1222cd  ldloc.3
0x1222ce  ldc.i4.3
0x1222cf  ldelem.i1
0x1222d0  brtrue.s loc_122314
0x1222d2  ldarg.0
0x1222d3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1222d8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1222dd  ldarg.0
0x1222de  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3166_ReturnDynamicEntities
0x1222e3  bne.un.s loc_122314
0x1222e5  ldarg.0
0x1222e6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1222eb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1222f0  ldarg.0
0x1222f1  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id85_Item
0x1222f6  bne.un.s loc_122314
0x1222f8  ldloc.2
0x1222f9  ldarg.0
0x1222fa  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1222ff  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x122304  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x122309  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveByResourcesServiceRequest::set_ReturnDynamicEntities(bool)
0x12230e  ldloc.3
0x12230f  ldc.i4.3
0x122310  ldc.i4.1
0x122311  stelem.i1
0x122312  br.s     loc_122333
0x122314  ldarg.0
0x122315  ldarg.0
0x122316  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12231b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x122320  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x122325  brtrue.s loc_122333
0x122327  ldarg.0
0x122328  ldloc.2
0x122329  ldstr    aReturndynamice_0// ":ReturnDynamicEntities"
0x12232e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x122333  ldarg.0
0x122334  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122339  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x12233e  brtrue.s loc_1222CD
0x122340  ldarg.0
0x122341  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122346  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x12234b  pop
0x12234c  ldarg.0
0x12234d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122352  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x122357  brfalse.s loc_122366
0x122359  ldarg.0
0x12235a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12235f  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x122364  ldloc.2
0x122365  ret
0x122366  ldarg.0
0x122367  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12236c  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x122371  ldarg.0
0x122372  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122377  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12237c  pop
0x12237d  ldc.i4.0
0x12237e  stloc.s  4
0x122380  ldarg.0
0x122381  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x122386  stloc.s  5
0x122388  br       loc_1226D7
0x12238d  ldarg.0
0x12238e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122393  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x122398  ldc.i4.1
0x122399  bne.un   loc_1226B5
0x12239e  ldarg.0
0x12239f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1223a4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1223a9  ldarg.0
0x1223aa  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x1223af  bne.un   loc_1224FC
0x1223b4  ldarg.0
0x1223b5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1223ba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1223bf  ldarg.0
0x1223c0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1223c5  bne.un   loc_1224FC
0x1223ca  ldarg.0
0x1223cb  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1223d0  brtrue   loc_1226C1
0x1223d5  ldnull
0x1223d6  stloc.s  6
0x1223d8  ldc.i4.0
0x1223d9  stloc.s  7
0x1223db  ldarg.0
0x1223dc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1223e1  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1223e6  brfalse.s loc_1223F8
0x1223e8  ldarg.0
0x1223e9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1223ee  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x1223f3  br       loc_1224D7
0x1223f8  ldarg.0
0x1223f9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1223fe  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x122403  ldarg.0
0x122404  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122409  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12240e  pop
0x12240f  ldc.i4.0
0x122410  stloc.s  8
0x122412  ldarg.0
0x122413  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x122418  stloc.s  9
0x12241a  br       loc_1224B2
0x12241f  ldarg.0
0x122420  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122425  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x12242a  ldc.i4.1
0x12242b  bne.un.s loc_122490
0x12242d  ldarg.0
0x12242e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122433  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x122438  ldarg.0
0x122439  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x12243e  bne.un.s loc_122482
0x122440  ldarg.0
0x122441  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122446  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12244b  ldarg.0
0x12244c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x122451  bne.un.s loc_122482
0x122453  ldarg.0
0x122454  ldloc.s  6
0x122456  ldloc.s  7
0x122458  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x12245d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x122462  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x122467  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x12246c  stloc.s  6
0x12246e  ldloc.s  6
0x122470  ldloc.s  7
0x122472  dup
0x122473  ldc.i4.1
0x122474  add
0x122475  stloc.s  7
0x122477  ldarg.0
0x122478  ldc.i4.1
0x122479  ldc.i4.1
0x12247a  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x12247f  stelem.ref
0x122480  br.s     loc_12249C
0x122482  ldarg.0
0x122483  ldnull
0x122484  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x122489  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x12248e  br.s     loc_12249C
0x122490  ldarg.0
0x122491  ldnull
0x122492  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x122497  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x12249c  ldarg.0
0x12249d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1224a2  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1224a7  pop
0x1224a8  ldarg.0
0x1224a9  ldloca.s 8
0x1224ab  ldloca.s 9
0x1224ad  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x1224b2  ldarg.0
0x1224b3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1224b8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1224bd  ldc.i4.s 0xF
0x1224bf  beq.s    loc_1224D1
0x1224c1  ldarg.0
0x1224c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1224c7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1224cc  brtrue   loc_12241F
0x1224d1  ldarg.0
0x1224d2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x1224d7  ldloc.2
0x1224d8  ldarg.0
0x1224d9  ldloc.s  6
0x1224db  ldloc.s  7
0x1224dd  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x1224e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1224e7  ldc.i4.0
0x1224e8  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x1224ed  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x1224f2  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x1224f7  br       loc_1226C1
0x1224fc  ldarg.0
0x1224fd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122502  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x122507  ldarg.0
0x122508  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3185_ResourceIds
0x12250d  bne.un   loc_122668
0x122512  ldarg.0
0x122513  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122518  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12251d  ldarg.0
0x12251e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x122523  bne.un   loc_122668
0x122528  ldarg.0
0x122529  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x12252e  brtrue   loc_1226C1
0x122533  ldnull
0x122534  stloc.s  0xA
0x122536  ldc.i4.0
0x122537  stloc.s  0xB
0x122539  ldarg.0
0x12253a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12253f  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x122544  brfalse.s loc_122556
0x122546  ldarg.0
0x122547  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12254c  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x122551  br       loc_122646
0x122556  ldarg.0
0x122557  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12255c  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x122561  ldarg.0
0x122562  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122567  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12256c  pop
0x12256d  ldc.i4.0
0x12256e  stloc.s  0xC
0x122570  ldarg.0
0x122571  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x122576  stloc.s  0xD
0x122578  br       loc_122621
0x12257d  ldarg.0
0x12257e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122583  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x122588  ldc.i4.1
0x122589  bne.un.s loc_1225FF
0x12258b  ldarg.0
0x12258c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x122591  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x122596  ldarg.0
0x122597  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id308_guid
0x12259c  bne.un.s loc_1225F1
0x12259e  ldarg.0
0x12259f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1225a4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1225a9  ldarg.0
0x1225aa  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1225af  bne.un.s loc_1225F1
0x1225b1  ldarg.0
0x1225b2  ldloc.s  0xA
0x1225b4  ldloc.s  0xB
0x1225b6  ldtoken  [mscorlib]System.Guid
0x1225bb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1225c0  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x1225c5  castclass valuetype [mscorlib]System.Guid[]
0x1225ca  stloc.s  0xA
0x1225cc  ldloc.s  0xA
0x1225ce  ldloc.s  0xB
0x1225d0  dup
  ... truncated ...
```
