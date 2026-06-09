# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read877_RegisterSolutionRequest

- ea: `0x127a30`
- end: `0x127e64`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read877_RegisterSolutionRequest`
- size: `1076`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0x97290`
- `0x9b920`
- `0xdd390`
- `0x127a30`

## string_xrefs

- `0x127bf8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x127c06`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x127d98`: `http://schemas.microsoft.com/crm/2007/WebServices:SdkMessageProcessingStepRegistration`
- `0x127da6`: `http://schemas.microsoft.com/crm/2007/WebServices:SdkMessageProcessingStepRegistration`
- `0x127e0f`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:PluginAssembly, http://schemas.microsoft.com/crm/2007/WebServices:Steps`
- `0x127e1d`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:PluginAssembly, http://schemas.microsoft.com/crm/2007/WebServices:Steps`

## pseudocode

```c

```

## disassembly

```asm
0x127a30  ldarg.2
0x127a31  brtrue.s loc_127A36
0x127a33  ldnull
0x127a34  br.s     loc_127A3C
0x127a36  ldarg.0
0x127a37  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x127a3c  stloc.0
0x127a3d  ldc.i4.0
0x127a3e  stloc.1
0x127a3f  ldarg.1
0x127a40  brfalse.s loc_127A49
0x127a42  ldarg.0
0x127a43  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x127a48  stloc.1
0x127a49  ldarg.2
0x127a4a  brfalse.s loc_127A79
0x127a4c  ldloc.0
0x127a4d  ldnull
0x127a4e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x127a53  brtrue.s loc_127A79
0x127a55  ldloc.0
0x127a56  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x127a5b  ldarg.0
0x127a5c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1524_RegisterSolutionRequest
0x127a61  bne.un.s loc_127A71
0x127a63  ldloc.0
0x127a64  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x127a69  ldarg.0
0x127a6a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x127a6f  beq.s    loc_127A79
0x127a71  ldarg.0
0x127a72  ldloc.0
0x127a73  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x127a78  throw
0x127a79  ldloc.1
0x127a7a  brfalse.s loc_127A7E
0x127a7c  ldnull
0x127a7d  ret
0x127a7e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RegisterSolutionRequest::.ctor()
0x127a83  stloc.2
0x127a84  ldc.i4.3
0x127a85  newarr   [mscorlib]System.Boolean
0x127a8a  stloc.3
0x127a8b  br.s     loc_127AA7
0x127a8d  ldarg.0
0x127a8e  ldarg.0
0x127a8f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127a94  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x127a99  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x127a9e  brtrue.s loc_127AA7
0x127aa0  ldarg.0
0x127aa1  ldloc.2
0x127aa2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x127aa7  ldarg.0
0x127aa8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127aad  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x127ab2  brtrue.s loc_127A8D
0x127ab4  ldarg.0
0x127ab5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127aba  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x127abf  pop
0x127ac0  ldarg.0
0x127ac1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127ac6  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x127acb  brfalse.s loc_127ADA
0x127acd  ldarg.0
0x127ace  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127ad3  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x127ad8  ldloc.2
0x127ad9  ret
0x127ada  ldarg.0
0x127adb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127ae0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x127ae5  ldarg.0
0x127ae6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127aeb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x127af0  pop
0x127af1  ldc.i4.0
0x127af2  stloc.s  4
0x127af4  ldarg.0
0x127af5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x127afa  stloc.s  5
0x127afc  br       loc_127E3D
0x127b01  ldarg.0
0x127b02  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b07  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x127b0c  ldc.i4.1
0x127b0d  bne.un   loc_127E1B
0x127b12  ldarg.0
0x127b13  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b18  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x127b1d  ldarg.0
0x127b1e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x127b23  bne.un   loc_127C70
0x127b28  ldarg.0
0x127b29  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b2e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x127b33  ldarg.0
0x127b34  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x127b39  bne.un   loc_127C70
0x127b3e  ldarg.0
0x127b3f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x127b44  brtrue   loc_127E27
0x127b49  ldnull
0x127b4a  stloc.s  6
0x127b4c  ldc.i4.0
0x127b4d  stloc.s  7
0x127b4f  ldarg.0
0x127b50  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b55  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x127b5a  brfalse.s loc_127B6C
0x127b5c  ldarg.0
0x127b5d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b62  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x127b67  br       loc_127C4B
0x127b6c  ldarg.0
0x127b6d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b72  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x127b77  ldarg.0
0x127b78  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b7d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x127b82  pop
0x127b83  ldc.i4.0
0x127b84  stloc.s  8
0x127b86  ldarg.0
0x127b87  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x127b8c  stloc.s  9
0x127b8e  br       loc_127C26
0x127b93  ldarg.0
0x127b94  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127b99  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x127b9e  ldc.i4.1
0x127b9f  bne.un.s loc_127C04
0x127ba1  ldarg.0
0x127ba2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127ba7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x127bac  ldarg.0
0x127bad  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x127bb2  bne.un.s loc_127BF6
0x127bb4  ldarg.0
0x127bb5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127bba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x127bbf  ldarg.0
0x127bc0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x127bc5  bne.un.s loc_127BF6
0x127bc7  ldarg.0
0x127bc8  ldloc.s  6
0x127bca  ldloc.s  7
0x127bcc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x127bd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x127bd6  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x127bdb  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x127be0  stloc.s  6
0x127be2  ldloc.s  6
0x127be4  ldloc.s  7
0x127be6  dup
0x127be7  ldc.i4.1
0x127be8  add
0x127be9  stloc.s  7
0x127beb  ldarg.0
0x127bec  ldc.i4.1
0x127bed  ldc.i4.1
0x127bee  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x127bf3  stelem.ref
0x127bf4  br.s     loc_127C10
0x127bf6  ldarg.0
0x127bf7  ldnull
0x127bf8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x127bfd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x127c02  br.s     loc_127C10
0x127c04  ldarg.0
0x127c05  ldnull
0x127c06  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x127c0b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x127c10  ldarg.0
0x127c11  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127c16  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x127c1b  pop
0x127c1c  ldarg.0
0x127c1d  ldloca.s 8
0x127c1f  ldloca.s 9
0x127c21  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x127c26  ldarg.0
0x127c27  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127c2c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x127c31  ldc.i4.s 0xF
0x127c33  beq.s    loc_127C45
0x127c35  ldarg.0
0x127c36  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127c3b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x127c40  brtrue   loc_127B93
0x127c45  ldarg.0
0x127c46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x127c4b  ldloc.2
0x127c4c  ldarg.0
0x127c4d  ldloc.s  6
0x127c4f  ldloc.s  7
0x127c51  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x127c56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x127c5b  ldc.i4.0
0x127c5c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x127c61  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x127c66  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x127c6b  br       loc_127E27
0x127c70  ldloc.3
0x127c71  ldc.i4.1
0x127c72  ldelem.i1
0x127c73  brtrue.s loc_127CB2
0x127c75  ldarg.0
0x127c76  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127c7b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x127c80  ldarg.0
0x127c81  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2996_PluginAssembly
0x127c86  bne.un.s loc_127CB2
0x127c88  ldarg.0
0x127c89  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127c8e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x127c93  ldarg.0
0x127c94  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x127c99  bne.un.s loc_127CB2
0x127c9b  ldloc.2
0x127c9c  ldarg.0
0x127c9d  ldc.i4.0
0x127c9e  ldc.i4.1
0x127c9f  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read132_BusinessEntity(bool isNullable, bool checkType)
0x127ca4  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RegisterSolutionRequest::set_PluginAssembly(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity)
0x127ca9  ldloc.3
0x127caa  ldc.i4.1
0x127cab  ldc.i4.1
0x127cac  stelem.i1
0x127cad  br       loc_127E27
0x127cb2  ldarg.0
0x127cb3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127cb8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x127cbd  ldarg.0
0x127cbe  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3198_Steps
0x127cc3  bne.un   loc_127E0D
0x127cc8  ldarg.0
0x127cc9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127cce  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x127cd3  ldarg.0
0x127cd4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x127cd9  bne.un   loc_127E0D
0x127cde  ldarg.0
0x127cdf  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x127ce4  brtrue   loc_127E27
0x127ce9  ldnull
0x127cea  stloc.s  0xA
0x127cec  ldc.i4.0
0x127ced  stloc.s  0xB
0x127cef  ldarg.0
0x127cf0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127cf5  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x127cfa  brfalse.s loc_127D0C
0x127cfc  ldarg.0
0x127cfd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127d02  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x127d07  br       loc_127DEB
0x127d0c  ldarg.0
0x127d0d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127d12  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x127d17  ldarg.0
0x127d18  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127d1d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x127d22  pop
0x127d23  ldc.i4.0
0x127d24  stloc.s  0xC
0x127d26  ldarg.0
0x127d27  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x127d2c  stloc.s  0xD
0x127d2e  br       loc_127DC6
0x127d33  ldarg.0
0x127d34  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127d39  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x127d3e  ldc.i4.1
0x127d3f  bne.un.s loc_127DA4
0x127d41  ldarg.0
0x127d42  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127d47  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x127d4c  ldarg.0
0x127d4d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id344_Item
0x127d52  bne.un.s loc_127D96
0x127d54  ldarg.0
0x127d55  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x127d5a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x127d5f  ldarg.0
0x127d60  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x127d65  bne.un.s loc_127D96
0x127d67  ldarg.0
0x127d68  ldloc.s  0xA
0x127d6a  ldloc.s  0xB
0x127d6c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration
0x127d71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x127d76  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x127d7b  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration[]
0x127d80  stloc.s  0xA
0x127d82  ldloc.s  0xA
0x127d84  ldloc.s  0xB
0x127d86  dup
0x127d87  ldc.i4.1
  ... truncated ...
```
