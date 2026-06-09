# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1267_CheckNotificationsRequest

- ea: `0x15b810`
- end: `0x15bc95`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1267_CheckNotificationsRequest`
- size: `1157`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0x79630`
- `0xdd390`
- `0x15b810`

## string_xrefs

- `0x15bb8a`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0x15bb98`: `http://schemas.microsoft.com/crm/2007/WebServices:int`
- `0x15ba24`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15ba32`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15bc40`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:Events, http://schemas.microsoft.com/crm/2007/WebServices:LastChecked`
- `0x15bc4e`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:Events, http://schemas.microsoft.com/crm/2007/WebServices:LastChecked`

## pseudocode

```c

```

## disassembly

```asm
0x15b810  ldarg.2
0x15b811  brtrue.s loc_15B816
0x15b813  ldnull
0x15b814  br.s     loc_15B81C
0x15b816  ldarg.0
0x15b817  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x15b81c  stloc.0
0x15b81d  ldc.i4.0
0x15b81e  stloc.1
0x15b81f  ldarg.1
0x15b820  brfalse.s loc_15B829
0x15b822  ldarg.0
0x15b823  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15b828  stloc.1
0x15b829  ldarg.2
0x15b82a  brfalse.s loc_15B859
0x15b82c  ldloc.0
0x15b82d  ldnull
0x15b82e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x15b833  brtrue.s loc_15B859
0x15b835  ldloc.0
0x15b836  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x15b83b  ldarg.0
0x15b83c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1387_CheckNotificationsRequest
0x15b841  bne.un.s loc_15B851
0x15b843  ldloc.0
0x15b844  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x15b849  ldarg.0
0x15b84a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15b84f  beq.s    loc_15B859
0x15b851  ldarg.0
0x15b852  ldloc.0
0x15b853  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x15b858  throw
0x15b859  ldloc.1
0x15b85a  brfalse.s loc_15B85E
0x15b85c  ldnull
0x15b85d  ret
0x15b85e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckNotificationsRequest::.ctor()
0x15b863  stloc.2
0x15b864  ldc.i4.4
0x15b865  newarr   [mscorlib]System.Boolean
0x15b86a  stloc.3
0x15b86b  br.s     loc_15B8D3
0x15b86d  ldloc.3
0x15b86e  ldc.i4.3
0x15b86f  ldelem.i1
0x15b870  brtrue.s loc_15B8B4
0x15b872  ldarg.0
0x15b873  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b878  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15b87d  ldarg.0
0x15b87e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3166_ReturnDynamicEntities
0x15b883  bne.un.s loc_15B8B4
0x15b885  ldarg.0
0x15b886  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b88b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15b890  ldarg.0
0x15b891  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id85_Item
0x15b896  bne.un.s loc_15B8B4
0x15b898  ldloc.2
0x15b899  ldarg.0
0x15b89a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b89f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Value()
0x15b8a4  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x15b8a9  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CheckNotificationsRequest::set_ReturnDynamicEntities(bool)
0x15b8ae  ldloc.3
0x15b8af  ldc.i4.3
0x15b8b0  ldc.i4.1
0x15b8b1  stelem.i1
0x15b8b2  br.s     loc_15B8D3
0x15b8b4  ldarg.0
0x15b8b5  ldarg.0
0x15b8b6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b8bb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x15b8c0  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x15b8c5  brtrue.s loc_15B8D3
0x15b8c7  ldarg.0
0x15b8c8  ldloc.2
0x15b8c9  ldstr    aReturndynamice_0// ":ReturnDynamicEntities"
0x15b8ce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15b8d3  ldarg.0
0x15b8d4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b8d9  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x15b8de  brtrue.s loc_15B86D
0x15b8e0  ldarg.0
0x15b8e1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b8e6  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x15b8eb  pop
0x15b8ec  ldarg.0
0x15b8ed  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b8f2  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15b8f7  brfalse.s loc_15B906
0x15b8f9  ldarg.0
0x15b8fa  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b8ff  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15b904  ldloc.2
0x15b905  ret
0x15b906  ldarg.0
0x15b907  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b90c  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15b911  ldarg.0
0x15b912  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b917  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15b91c  pop
0x15b91d  ldc.i4.0
0x15b91e  stloc.s  4
0x15b920  ldarg.0
0x15b921  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15b926  stloc.s  5
0x15b928  br       loc_15BC6E
0x15b92d  ldarg.0
0x15b92e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b933  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15b938  ldc.i4.1
0x15b939  bne.un   loc_15BC4C
0x15b93e  ldarg.0
0x15b93f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b944  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15b949  ldarg.0
0x15b94a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x15b94f  bne.un   loc_15BA9C
0x15b954  ldarg.0
0x15b955  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b95a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15b95f  ldarg.0
0x15b960  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15b965  bne.un   loc_15BA9C
0x15b96a  ldarg.0
0x15b96b  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15b970  brtrue   loc_15BC58
0x15b975  ldnull
0x15b976  stloc.s  6
0x15b978  ldc.i4.0
0x15b979  stloc.s  7
0x15b97b  ldarg.0
0x15b97c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b981  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15b986  brfalse.s loc_15B998
0x15b988  ldarg.0
0x15b989  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b98e  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15b993  br       loc_15BA77
0x15b998  ldarg.0
0x15b999  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b99e  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15b9a3  ldarg.0
0x15b9a4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b9a9  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15b9ae  pop
0x15b9af  ldc.i4.0
0x15b9b0  stloc.s  8
0x15b9b2  ldarg.0
0x15b9b3  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15b9b8  stloc.s  9
0x15b9ba  br       loc_15BA52
0x15b9bf  ldarg.0
0x15b9c0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b9c5  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15b9ca  ldc.i4.1
0x15b9cb  bne.un.s loc_15BA30
0x15b9cd  ldarg.0
0x15b9ce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b9d3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15b9d8  ldarg.0
0x15b9d9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x15b9de  bne.un.s loc_15BA22
0x15b9e0  ldarg.0
0x15b9e1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15b9e6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15b9eb  ldarg.0
0x15b9ec  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15b9f1  bne.un.s loc_15BA22
0x15b9f3  ldarg.0
0x15b9f4  ldloc.s  6
0x15b9f6  ldloc.s  7
0x15b9f8  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15b9fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ba02  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x15ba07  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15ba0c  stloc.s  6
0x15ba0e  ldloc.s  6
0x15ba10  ldloc.s  7
0x15ba12  dup
0x15ba13  ldc.i4.1
0x15ba14  add
0x15ba15  stloc.s  7
0x15ba17  ldarg.0
0x15ba18  ldc.i4.1
0x15ba19  ldc.i4.1
0x15ba1a  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x15ba1f  stelem.ref
0x15ba20  br.s     loc_15BA3C
0x15ba22  ldarg.0
0x15ba23  ldnull
0x15ba24  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15ba29  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15ba2e  br.s     loc_15BA3C
0x15ba30  ldarg.0
0x15ba31  ldnull
0x15ba32  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15ba37  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15ba3c  ldarg.0
0x15ba3d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ba42  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15ba47  pop
0x15ba48  ldarg.0
0x15ba49  ldloca.s 8
0x15ba4b  ldloca.s 9
0x15ba4d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x15ba52  ldarg.0
0x15ba53  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ba58  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15ba5d  ldc.i4.s 0xF
0x15ba5f  beq.s    loc_15BA71
0x15ba61  ldarg.0
0x15ba62  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ba67  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15ba6c  brtrue   loc_15B9BF
0x15ba71  ldarg.0
0x15ba72  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x15ba77  ldloc.2
0x15ba78  ldarg.0
0x15ba79  ldloc.s  6
0x15ba7b  ldloc.s  7
0x15ba7d  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15ba82  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ba87  ldc.i4.0
0x15ba88  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x15ba8d  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15ba92  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x15ba97  br       loc_15BC58
0x15ba9c  ldarg.0
0x15ba9d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15baa2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15baa7  ldarg.0
0x15baa8  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3296_Events
0x15baad  bne.un   loc_15BBFF
0x15bab2  ldarg.0
0x15bab3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15bab8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15babd  ldarg.0
0x15babe  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15bac3  bne.un   loc_15BBFF
0x15bac8  ldarg.0
0x15bac9  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15bace  brtrue   loc_15BC58
0x15bad3  ldnull
0x15bad4  stloc.s  0xA
0x15bad6  ldc.i4.0
0x15bad7  stloc.s  0xB
0x15bad9  ldarg.0
0x15bada  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15badf  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15bae4  brfalse.s loc_15BAF6
0x15bae6  ldarg.0
0x15bae7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15baec  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15baf1  br       loc_15BBDD
0x15baf6  ldarg.0
0x15baf7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15bafc  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15bb01  ldarg.0
0x15bb02  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15bb07  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15bb0c  pop
0x15bb0d  ldc.i4.0
0x15bb0e  stloc.s  0xC
0x15bb10  ldarg.0
0x15bb11  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15bb16  stloc.s  0xD
0x15bb18  br       loc_15BBB8
0x15bb1d  ldarg.0
0x15bb1e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15bb23  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15bb28  ldc.i4.1
0x15bb29  bne.un.s loc_15BB96
0x15bb2b  ldarg.0
0x15bb2c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15bb31  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15bb36  ldarg.0
0x15bb37  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id242_int
0x15bb3c  bne.un.s loc_15BB88
0x15bb3e  ldarg.0
0x15bb3f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15bb44  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15bb49  ldarg.0
0x15bb4a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15bb4f  bne.un.s loc_15BB88
0x15bb51  ldarg.0
0x15bb52  ldloc.s  0xA
0x15bb54  ldloc.s  0xB
0x15bb56  ldtoken  [mscorlib]System.Int32
0x15bb5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15bb60  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x15bb65  castclass int32[]
0x15bb6a  stloc.s  0xA
0x15bb6c  ldloc.s  0xA
0x15bb6e  ldloc.s  0xB
0x15bb70  dup
  ... truncated ...
```
