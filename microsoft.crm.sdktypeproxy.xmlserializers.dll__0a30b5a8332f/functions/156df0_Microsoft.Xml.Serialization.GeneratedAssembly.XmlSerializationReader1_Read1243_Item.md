# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1243_Item

- ea: `0x156df0`
- end: `0x157238`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1243_Item`
- size: `1096`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0xdd390`
- `0x156df0`

## string_xrefs

- `0x156fb8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x156fc6`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15716c`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x15717a`: `http://schemas.microsoft.com/crm/2007/WebServices:guid`
- `0x1571e3`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:MapXml, http://schemas.microsoft.com/crm/2007/WebServices:ColMappingIdsToDelete`
- `0x1571f1`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:MapXml, http://schemas.microsoft.com/crm/2007/WebServices:ColMappingIdsToDelete`

## pseudocode

```c

```

## disassembly

```asm
0x156df0  ldarg.2
0x156df1  brtrue.s loc_156DF6
0x156df3  ldnull
0x156df4  br.s     loc_156DFC
0x156df6  ldarg.0
0x156df7  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x156dfc  stloc.0
0x156dfd  ldc.i4.0
0x156dfe  stloc.1
0x156dff  ldarg.1
0x156e00  brfalse.s loc_156E09
0x156e02  ldarg.0
0x156e03  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x156e08  stloc.1
0x156e09  ldarg.2
0x156e0a  brfalse.s loc_156E39
0x156e0c  ldloc.0
0x156e0d  ldnull
0x156e0e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x156e13  brtrue.s loc_156E39
0x156e15  ldloc.0
0x156e16  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x156e1b  ldarg.0
0x156e1c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1405_Item
0x156e21  bne.un.s loc_156E31
0x156e23  ldloc.0
0x156e24  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x156e29  ldarg.0
0x156e2a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x156e2f  beq.s    loc_156E39
0x156e31  ldarg.0
0x156e32  ldloc.0
0x156e33  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x156e38  throw
0x156e39  ldloc.1
0x156e3a  brfalse.s loc_156E3E
0x156e3c  ldnull
0x156e3d  ret
0x156e3e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateOrUpdateImportMapFromAppRequest::.ctor()
0x156e43  stloc.2
0x156e44  ldc.i4.3
0x156e45  newarr   [mscorlib]System.Boolean
0x156e4a  stloc.3
0x156e4b  br.s     loc_156E67
0x156e4d  ldarg.0
0x156e4e  ldarg.0
0x156e4f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156e54  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x156e59  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x156e5e  brtrue.s loc_156E67
0x156e60  ldarg.0
0x156e61  ldloc.2
0x156e62  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x156e67  ldarg.0
0x156e68  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156e6d  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x156e72  brtrue.s loc_156E4D
0x156e74  ldarg.0
0x156e75  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156e7a  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x156e7f  pop
0x156e80  ldarg.0
0x156e81  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156e86  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x156e8b  brfalse.s loc_156E9A
0x156e8d  ldarg.0
0x156e8e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156e93  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x156e98  ldloc.2
0x156e99  ret
0x156e9a  ldarg.0
0x156e9b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156ea0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x156ea5  ldarg.0
0x156ea6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156eab  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x156eb0  pop
0x156eb1  ldc.i4.0
0x156eb2  stloc.s  4
0x156eb4  ldarg.0
0x156eb5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x156eba  stloc.s  5
0x156ebc  br       loc_157211
0x156ec1  ldarg.0
0x156ec2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156ec7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x156ecc  ldc.i4.1
0x156ecd  bne.un   loc_1571EF
0x156ed2  ldarg.0
0x156ed3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156ed8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x156edd  ldarg.0
0x156ede  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x156ee3  bne.un   loc_157030
0x156ee8  ldarg.0
0x156ee9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156eee  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x156ef3  ldarg.0
0x156ef4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x156ef9  bne.un   loc_157030
0x156efe  ldarg.0
0x156eff  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x156f04  brtrue   loc_1571FB
0x156f09  ldnull
0x156f0a  stloc.s  6
0x156f0c  ldc.i4.0
0x156f0d  stloc.s  7
0x156f0f  ldarg.0
0x156f10  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156f15  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x156f1a  brfalse.s loc_156F2C
0x156f1c  ldarg.0
0x156f1d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156f22  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x156f27  br       loc_15700B
0x156f2c  ldarg.0
0x156f2d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156f32  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x156f37  ldarg.0
0x156f38  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156f3d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x156f42  pop
0x156f43  ldc.i4.0
0x156f44  stloc.s  8
0x156f46  ldarg.0
0x156f47  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x156f4c  stloc.s  9
0x156f4e  br       loc_156FE6
0x156f53  ldarg.0
0x156f54  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156f59  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x156f5e  ldc.i4.1
0x156f5f  bne.un.s loc_156FC4
0x156f61  ldarg.0
0x156f62  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156f67  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x156f6c  ldarg.0
0x156f6d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x156f72  bne.un.s loc_156FB6
0x156f74  ldarg.0
0x156f75  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156f7a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x156f7f  ldarg.0
0x156f80  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x156f85  bne.un.s loc_156FB6
0x156f87  ldarg.0
0x156f88  ldloc.s  6
0x156f8a  ldloc.s  7
0x156f8c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x156f91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x156f96  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x156f9b  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x156fa0  stloc.s  6
0x156fa2  ldloc.s  6
0x156fa4  ldloc.s  7
0x156fa6  dup
0x156fa7  ldc.i4.1
0x156fa8  add
0x156fa9  stloc.s  7
0x156fab  ldarg.0
0x156fac  ldc.i4.1
0x156fad  ldc.i4.1
0x156fae  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x156fb3  stelem.ref
0x156fb4  br.s     loc_156FD0
0x156fb6  ldarg.0
0x156fb7  ldnull
0x156fb8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x156fbd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x156fc2  br.s     loc_156FD0
0x156fc4  ldarg.0
0x156fc5  ldnull
0x156fc6  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x156fcb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x156fd0  ldarg.0
0x156fd1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156fd6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x156fdb  pop
0x156fdc  ldarg.0
0x156fdd  ldloca.s 8
0x156fdf  ldloca.s 9
0x156fe1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x156fe6  ldarg.0
0x156fe7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156fec  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x156ff1  ldc.i4.s 0xF
0x156ff3  beq.s    loc_157005
0x156ff5  ldarg.0
0x156ff6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x156ffb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x157000  brtrue   loc_156F53
0x157005  ldarg.0
0x157006  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x15700b  ldloc.2
0x15700c  ldarg.0
0x15700d  ldloc.s  6
0x15700f  ldloc.s  7
0x157011  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x157016  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15701b  ldc.i4.0
0x15701c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x157021  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x157026  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x15702b  br       loc_1571FB
0x157030  ldloc.3
0x157031  ldc.i4.1
0x157032  ldelem.i1
0x157033  brtrue.s loc_157075
0x157035  ldarg.0
0x157036  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15703b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x157040  ldarg.0
0x157041  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3283_MapXml
0x157046  bne.un.s loc_157075
0x157048  ldarg.0
0x157049  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15704e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x157053  ldarg.0
0x157054  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x157059  bne.un.s loc_157075
0x15705b  ldloc.2
0x15705c  ldarg.0
0x15705d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x157062  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x157067  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateOrUpdateImportMapFromAppRequest::set_MapXml(string)
0x15706c  ldloc.3
0x15706d  ldc.i4.1
0x15706e  ldc.i4.1
0x15706f  stelem.i1
0x157070  br       loc_1571FB
0x157075  ldarg.0
0x157076  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15707b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x157080  ldarg.0
0x157081  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3284_ColMappingIdsToDelete
0x157086  bne.un   loc_1571E1
0x15708b  ldarg.0
0x15708c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x157091  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x157096  ldarg.0
0x157097  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15709c  bne.un   loc_1571E1
0x1570a1  ldarg.0
0x1570a2  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x1570a7  brtrue   loc_1571FB
0x1570ac  ldnull
0x1570ad  stloc.s  0xA
0x1570af  ldc.i4.0
0x1570b0  stloc.s  0xB
0x1570b2  ldarg.0
0x1570b3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1570b8  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1570bd  brfalse.s loc_1570CF
0x1570bf  ldarg.0
0x1570c0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1570c5  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x1570ca  br       loc_1571BF
0x1570cf  ldarg.0
0x1570d0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1570d5  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x1570da  ldarg.0
0x1570db  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1570e0  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1570e5  pop
0x1570e6  ldc.i4.0
0x1570e7  stloc.s  0xC
0x1570e9  ldarg.0
0x1570ea  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x1570ef  stloc.s  0xD
0x1570f1  br       loc_15719A
0x1570f6  ldarg.0
0x1570f7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1570fc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x157101  ldc.i4.1
0x157102  bne.un.s loc_157178
0x157104  ldarg.0
0x157105  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15710a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15710f  ldarg.0
0x157110  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id308_guid
0x157115  bne.un.s loc_15716A
0x157117  ldarg.0
0x157118  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15711d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x157122  ldarg.0
0x157123  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x157128  bne.un.s loc_15716A
0x15712a  ldarg.0
0x15712b  ldloc.s  0xA
0x15712d  ldloc.s  0xB
0x15712f  ldtoken  [mscorlib]System.Guid
0x157134  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x157139  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x15713e  castclass valuetype [mscorlib]System.Guid[]
0x157143  stloc.s  0xA
0x157145  ldloc.s  0xA
0x157147  ldloc.s  0xB
0x157149  dup
0x15714a  ldc.i4.1
0x15714b  add
  ... truncated ...
```
