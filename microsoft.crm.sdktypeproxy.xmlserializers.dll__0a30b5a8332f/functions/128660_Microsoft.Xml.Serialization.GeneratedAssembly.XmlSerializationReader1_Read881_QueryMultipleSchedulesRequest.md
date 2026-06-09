# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read881_QueryMultipleSchedulesRequest

- ea: `0x128660`
- end: `0x128c4e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read881_QueryMultipleSchedulesRequest`
- size: `1518`
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
- `0x128660`

## string_xrefs

- `0x128828`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x128836`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x128997`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x1289a5`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x128b82`: `http://schemas.microsoft.com/crm/2007/WebServices:TimeCode`
- `0x128b90`: `http://schemas.microsoft.com/crm/2007/WebServices:TimeCode`
- `0x128bf9`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ResourceIds, http://schemas.microsoft.com/crm/2007/WebServices:Start, http://schemas.microsoft.com/crm/2007/WebServices:End, http://schemas.microsoft.com/crm/2007/WebServices:TimeCodes`
- `0x128c07`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:ResourceIds, http://schemas.microsoft.com/crm/2007/WebServices:Start, http://schemas.microsoft.com/crm/2007/WebServices:End, http://schemas.microsoft.com/crm/2007/WebServices:TimeCodes`

## pseudocode

```c

```

## disassembly

```asm
0x128660  ldarg.2
0x128661  brtrue.s loc_128666
0x128663  ldnull
0x128664  br.s     loc_12866C
0x128666  ldarg.0
0x128667  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x12866c  stloc.0
0x12866d  ldc.i4.0
0x12866e  stloc.1
0x12866f  ldarg.1
0x128670  brfalse.s loc_128679
0x128672  ldarg.0
0x128673  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x128678  stloc.1
0x128679  ldarg.2
0x12867a  brfalse.s loc_1286A9
0x12867c  ldloc.0
0x12867d  ldnull
0x12867e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x128683  brtrue.s loc_1286A9
0x128685  ldloc.0
0x128686  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x12868b  ldarg.0
0x12868c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1521_QueryMultipleSchedulesRequest
0x128691  bne.un.s loc_1286A1
0x128693  ldloc.0
0x128694  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x128699  ldarg.0
0x12869a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x12869f  beq.s    loc_1286A9
0x1286a1  ldarg.0
0x1286a2  ldloc.0
0x1286a3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x1286a8  throw
0x1286a9  ldloc.1
0x1286aa  brfalse.s loc_1286AE
0x1286ac  ldnull
0x1286ad  ret
0x1286ae  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryMultipleSchedulesRequest::.ctor()
0x1286b3  stloc.2
0x1286b4  ldc.i4.5
0x1286b5  newarr   [mscorlib]System.Boolean
0x1286ba  stloc.3
0x1286bb  br.s     loc_1286D7
0x1286bd  ldarg.0
0x1286be  ldarg.0
0x1286bf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1286c4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x1286c9  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x1286ce  brtrue.s loc_1286D7
0x1286d0  ldarg.0
0x1286d1  ldloc.2
0x1286d2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x1286d7  ldarg.0
0x1286d8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1286dd  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x1286e2  brtrue.s loc_1286BD
0x1286e4  ldarg.0
0x1286e5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1286ea  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x1286ef  pop
0x1286f0  ldarg.0
0x1286f1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1286f6  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1286fb  brfalse.s loc_12870A
0x1286fd  ldarg.0
0x1286fe  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128703  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x128708  ldloc.2
0x128709  ret
0x12870a  ldarg.0
0x12870b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128710  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x128715  ldarg.0
0x128716  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12871b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x128720  pop
0x128721  ldc.i4.0
0x128722  stloc.s  4
0x128724  ldarg.0
0x128725  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x12872a  stloc.s  5
0x12872c  br       loc_128C27
0x128731  ldarg.0
0x128732  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128737  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x12873c  ldc.i4.1
0x12873d  bne.un   loc_128C05
0x128742  ldarg.0
0x128743  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128748  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12874d  ldarg.0
0x12874e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x128753  bne.un   loc_1288A0
0x128758  ldarg.0
0x128759  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12875e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x128763  ldarg.0
0x128764  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x128769  bne.un   loc_1288A0
0x12876e  ldarg.0
0x12876f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x128774  brtrue   loc_128C11
0x128779  ldnull
0x12877a  stloc.s  6
0x12877c  ldc.i4.0
0x12877d  stloc.s  7
0x12877f  ldarg.0
0x128780  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128785  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x12878a  brfalse.s loc_12879C
0x12878c  ldarg.0
0x12878d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128792  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x128797  br       loc_12887B
0x12879c  ldarg.0
0x12879d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1287a2  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x1287a7  ldarg.0
0x1287a8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1287ad  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1287b2  pop
0x1287b3  ldc.i4.0
0x1287b4  stloc.s  8
0x1287b6  ldarg.0
0x1287b7  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x1287bc  stloc.s  9
0x1287be  br       loc_128856
0x1287c3  ldarg.0
0x1287c4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1287c9  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1287ce  ldc.i4.1
0x1287cf  bne.un.s loc_128834
0x1287d1  ldarg.0
0x1287d2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1287d7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1287dc  ldarg.0
0x1287dd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x1287e2  bne.un.s loc_128826
0x1287e4  ldarg.0
0x1287e5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1287ea  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1287ef  ldarg.0
0x1287f0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1287f5  bne.un.s loc_128826
0x1287f7  ldarg.0
0x1287f8  ldloc.s  6
0x1287fa  ldloc.s  7
0x1287fc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x128801  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x128806  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x12880b  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x128810  stloc.s  6
0x128812  ldloc.s  6
0x128814  ldloc.s  7
0x128816  dup
0x128817  ldc.i4.1
0x128818  add
0x128819  stloc.s  7
0x12881b  ldarg.0
0x12881c  ldc.i4.1
0x12881d  ldc.i4.1
0x12881e  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x128823  stelem.ref
0x128824  br.s     loc_128840
0x128826  ldarg.0
0x128827  ldnull
0x128828  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x12882d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x128832  br.s     loc_128840
0x128834  ldarg.0
0x128835  ldnull
0x128836  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x12883b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x128840  ldarg.0
0x128841  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128846  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12884b  pop
0x12884c  ldarg.0
0x12884d  ldloca.s 8
0x12884f  ldloca.s 9
0x128851  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x128856  ldarg.0
0x128857  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12885c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x128861  ldc.i4.s 0xF
0x128863  beq.s    loc_128875
0x128865  ldarg.0
0x128866  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12886b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x128870  brtrue   loc_1287C3
0x128875  ldarg.0
0x128876  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x12887b  ldloc.2
0x12887c  ldarg.0
0x12887d  ldloc.s  6
0x12887f  ldloc.s  7
0x128881  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x128886  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12888b  ldc.i4.0
0x12888c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x128891  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x128896  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x12889b  br       loc_128C11
0x1288a0  ldarg.0
0x1288a1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1288a6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1288ab  ldarg.0
0x1288ac  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3185_ResourceIds
0x1288b1  bne.un   loc_128A0F
0x1288b6  ldarg.0
0x1288b7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1288bc  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1288c1  ldarg.0
0x1288c2  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1288c7  bne.un   loc_128A0F
0x1288cc  ldarg.0
0x1288cd  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1288d2  brtrue   loc_128C11
0x1288d7  ldnull
0x1288d8  stloc.s  0xA
0x1288da  ldc.i4.0
0x1288db  stloc.s  0xB
0x1288dd  ldarg.0
0x1288de  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1288e3  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1288e8  brfalse.s loc_1288FA
0x1288ea  ldarg.0
0x1288eb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1288f0  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x1288f5  br       loc_1289EA
0x1288fa  ldarg.0
0x1288fb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128900  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x128905  ldarg.0
0x128906  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12890b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x128910  pop
0x128911  ldc.i4.0
0x128912  stloc.s  0xC
0x128914  ldarg.0
0x128915  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x12891a  stloc.s  0xD
0x12891c  br       loc_1289C5
0x128921  ldarg.0
0x128922  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128927  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x12892c  ldc.i4.1
0x12892d  bne.un.s loc_1289A3
0x12892f  ldarg.0
0x128930  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128935  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12893a  ldarg.0
0x12893b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id308_guid
0x128940  bne.un.s loc_128995
0x128942  ldarg.0
0x128943  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128948  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12894d  ldarg.0
0x12894e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x128953  bne.un.s loc_128995
0x128955  ldarg.0
0x128956  ldloc.s  0xA
0x128958  ldloc.s  0xB
0x12895a  ldtoken  [mscorlib]System.Guid
0x12895f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x128964  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x128969  castclass valuetype [mscorlib]System.Guid[]
0x12896e  stloc.s  0xA
0x128970  ldloc.s  0xA
0x128972  ldloc.s  0xB
0x128974  dup
0x128975  ldc.i4.1
0x128976  add
0x128977  stloc.s  0xB
0x128979  ldelema  [mscorlib]System.Guid
0x12897e  ldarg.0
0x12897f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x128984  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x128989  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x12898e  stobj    [mscorlib]System.Guid
0x128993  br.s     loc_1289AF
0x128995  ldarg.0
0x128996  ldnull
0x128997  ldstr    aHttpSchemasMic_52// "http://schemas.microsoft.com/crm/2007/W"...
0x12899c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x1289a1  br.s     loc_1289AF
0x1289a3  ldarg.0
0x1289a4  ldnull
0x1289a5  ldstr    aHttpSchemasMic_52// "http://schemas.microsoft.com/crm/2007/W"...
0x1289aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x1289af  ldarg.0
0x1289b0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1289b5  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1289ba  pop
0x1289bb  ldarg.0
0x1289bc  ldloca.s 0xC
0x1289be  ldloca.s 0xD
0x1289c0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x1289c5  ldarg.0
  ... truncated ...
```
