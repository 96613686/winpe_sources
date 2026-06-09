# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read315_letter

- ea: `0xb7b00`
- end: `0xb89e9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read315_letter`
- size: `3817`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xed9c0`
- `0x151290`

## callees

- `0x79630`
- `0x79a60`
- `0x90c00`
- `0x91060`
- `0x91320`
- `0x91550`
- `0x91730`
- `0x95710`
- `0x95f10`
- `0x9aa80`
- `0xb7b00`
- `0xb89f0`

## string_xrefs

- `0xb7e16`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb7e24`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb7fb9`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb7fc7`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb8228`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb8236`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb88dc`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb88ea`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb8994`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:address, http://schemas.microsoft.com/crm/2007/WebServices:bcc, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:cc, http://schema`
- `0xb89a2`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:address, http://schemas.microsoft.com/crm/2007/WebServices:bcc, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:cc, http://schema`

## pseudocode

```c

```

## disassembly

```asm
0xb7b00  ldarg.2
0xb7b01  brtrue.s loc_B7B06
0xb7b03  ldnull
0xb7b04  br.s     loc_B7B0C
0xb7b06  ldarg.0
0xb7b07  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xb7b0c  stloc.0
0xb7b0d  ldc.i4.0
0xb7b0e  stloc.1
0xb7b0f  ldarg.1
0xb7b10  brfalse.s loc_B7B19
0xb7b12  ldarg.0
0xb7b13  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xb7b18  stloc.1
0xb7b19  ldarg.2
0xb7b1a  brfalse.s loc_B7B49
0xb7b1c  ldloc.0
0xb7b1d  ldnull
0xb7b1e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xb7b23  brtrue.s loc_B7B49
0xb7b25  ldloc.0
0xb7b26  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xb7b2b  ldarg.0
0xb7b2c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1738_letter
0xb7b31  bne.un.s loc_B7B41
0xb7b33  ldloc.0
0xb7b34  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xb7b39  ldarg.0
0xb7b3a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7b3f  beq.s    loc_B7B49
0xb7b41  ldarg.0
0xb7b42  ldloc.0
0xb7b43  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xb7b48  throw
0xb7b49  ldloc.1
0xb7b4a  brfalse.s loc_B7B4E
0xb7b4c  ldnull
0xb7b4d  ret
0xb7b4e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::.ctor()
0xb7b53  stloc.2
0xb7b54  ldc.i4.s 0x23
0xb7b56  newarr   [mscorlib]System.Boolean
0xb7b5b  stloc.3
0xb7b5c  br.s     loc_B7B78
0xb7b5e  ldarg.0
0xb7b5f  ldarg.0
0xb7b60  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7b65  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xb7b6a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xb7b6f  brtrue.s loc_B7B78
0xb7b71  ldarg.0
0xb7b72  ldloc.2
0xb7b73  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xb7b78  ldarg.0
0xb7b79  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7b7e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xb7b83  brtrue.s loc_B7B5E
0xb7b85  ldarg.0
0xb7b86  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7b8b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xb7b90  pop
0xb7b91  ldarg.0
0xb7b92  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7b97  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xb7b9c  brfalse.s loc_B7BAB
0xb7b9e  ldarg.0
0xb7b9f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7ba4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xb7ba9  ldloc.2
0xb7baa  ret
0xb7bab  ldarg.0
0xb7bac  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7bb1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xb7bb6  ldarg.0
0xb7bb7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7bbc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xb7bc1  pop
0xb7bc2  ldc.i4.0
0xb7bc3  stloc.s  4
0xb7bc5  ldarg.0
0xb7bc6  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xb7bcb  stloc.s  5
0xb7bcd  br       loc_B89C2
0xb7bd2  ldarg.0
0xb7bd3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7bd8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xb7bdd  ldc.i4.1
0xb7bde  bne.un   loc_B89A0
0xb7be3  ldloc.3
0xb7be4  ldc.i4.0
0xb7be5  ldelem.i1
0xb7be6  brtrue.s loc_B7C25
0xb7be8  ldarg.0
0xb7be9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7bee  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb7bf3  ldarg.0
0xb7bf4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xb7bf9  bne.un.s loc_B7C25
0xb7bfb  ldarg.0
0xb7bfc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7c01  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb7c06  ldarg.0
0xb7c07  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7c0c  bne.un.s loc_B7C25
0xb7c0e  ldloc.2
0xb7c0f  ldarg.0
0xb7c10  ldc.i4.0
0xb7c11  ldc.i4.1
0xb7c12  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xb7c17  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xb7c1c  ldloc.3
0xb7c1d  ldc.i4.0
0xb7c1e  ldc.i4.1
0xb7c1f  stelem.i1
0xb7c20  br       loc_B89AC
0xb7c25  ldloc.3
0xb7c26  ldc.i4.1
0xb7c27  ldelem.i1
0xb7c28  brtrue.s loc_B7C67
0xb7c2a  ldarg.0
0xb7c2b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7c30  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb7c35  ldarg.0
0xb7c36  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xb7c3b  bne.un.s loc_B7C67
0xb7c3d  ldarg.0
0xb7c3e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7c43  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb7c48  ldarg.0
0xb7c49  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7c4e  bne.un.s loc_B7C67
0xb7c50  ldloc.2
0xb7c51  ldarg.0
0xb7c52  ldc.i4.0
0xb7c53  ldc.i4.1
0xb7c54  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xb7c59  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xb7c5e  ldloc.3
0xb7c5f  ldc.i4.1
0xb7c60  ldc.i4.1
0xb7c61  stelem.i1
0xb7c62  br       loc_B89AC
0xb7c67  ldloc.3
0xb7c68  ldc.i4.2
0xb7c69  ldelem.i1
0xb7c6a  brtrue.s loc_B7CA9
0xb7c6c  ldarg.0
0xb7c6d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7c72  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb7c77  ldarg.0
0xb7c78  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xb7c7d  bne.un.s loc_B7CA9
0xb7c7f  ldarg.0
0xb7c80  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7c85  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb7c8a  ldarg.0
0xb7c8b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7c90  bne.un.s loc_B7CA9
0xb7c92  ldloc.2
0xb7c93  ldarg.0
0xb7c94  ldc.i4.0
0xb7c95  ldc.i4.1
0xb7c96  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xb7c9b  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xb7ca0  ldloc.3
0xb7ca1  ldc.i4.2
0xb7ca2  ldc.i4.1
0xb7ca3  stelem.i1
0xb7ca4  br       loc_B89AC
0xb7ca9  ldloc.3
0xb7caa  ldc.i4.3
0xb7cab  ldelem.i1
0xb7cac  brtrue.s loc_B7CEB
0xb7cae  ldarg.0
0xb7caf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7cb4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb7cb9  ldarg.0
0xb7cba  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xb7cbf  bne.un.s loc_B7CEB
0xb7cc1  ldarg.0
0xb7cc2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7cc7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb7ccc  ldarg.0
0xb7ccd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7cd2  bne.un.s loc_B7CEB
0xb7cd4  ldloc.2
0xb7cd5  ldarg.0
0xb7cd6  ldc.i4.0
0xb7cd7  ldc.i4.1
0xb7cd8  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xb7cdd  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xb7ce2  ldloc.3
0xb7ce3  ldc.i4.3
0xb7ce4  ldc.i4.1
0xb7ce5  stelem.i1
0xb7ce6  br       loc_B89AC
0xb7ceb  ldloc.3
0xb7cec  ldc.i4.4
0xb7ced  ldelem.i1
0xb7cee  brtrue.s loc_B7D30
0xb7cf0  ldarg.0
0xb7cf1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7cf6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb7cfb  ldarg.0
0xb7cfc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2475_address
0xb7d01  bne.un.s loc_B7D30
0xb7d03  ldarg.0
0xb7d04  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d09  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb7d0e  ldarg.0
0xb7d0f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7d14  bne.un.s loc_B7D30
0xb7d16  ldloc.2
0xb7d17  ldarg.0
0xb7d18  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d1d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xb7d22  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::set_address(string)
0xb7d27  ldloc.3
0xb7d28  ldc.i4.4
0xb7d29  ldc.i4.1
0xb7d2a  stelem.i1
0xb7d2b  br       loc_B89AC
0xb7d30  ldarg.0
0xb7d31  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d36  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb7d3b  ldarg.0
0xb7d3c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2476_bcc
0xb7d41  bne.un   loc_B7E8E
0xb7d46  ldarg.0
0xb7d47  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d4c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb7d51  ldarg.0
0xb7d52  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7d57  bne.un   loc_B7E8E
0xb7d5c  ldarg.0
0xb7d5d  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xb7d62  brtrue   loc_B89AC
0xb7d67  ldnull
0xb7d68  stloc.s  6
0xb7d6a  ldc.i4.0
0xb7d6b  stloc.s  7
0xb7d6d  ldarg.0
0xb7d6e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d73  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xb7d78  brfalse.s loc_B7D8A
0xb7d7a  ldarg.0
0xb7d7b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d80  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xb7d85  br       loc_B7E69
0xb7d8a  ldarg.0
0xb7d8b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d90  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xb7d95  ldarg.0
0xb7d96  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7d9b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xb7da0  pop
0xb7da1  ldc.i4.0
0xb7da2  stloc.s  8
0xb7da4  ldarg.0
0xb7da5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xb7daa  stloc.s  9
0xb7dac  br       loc_B7E44
0xb7db1  ldarg.0
0xb7db2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7db7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xb7dbc  ldc.i4.1
0xb7dbd  bne.un.s loc_B7E22
0xb7dbf  ldarg.0
0xb7dc0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7dc5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb7dca  ldarg.0
0xb7dcb  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id252_activityparty
0xb7dd0  bne.un.s loc_B7E14
0xb7dd2  ldarg.0
0xb7dd3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xb7dd8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xb7ddd  ldarg.0
0xb7dde  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xb7de3  bne.un.s loc_B7E14
0xb7de5  ldarg.0
0xb7de6  ldloc.s  6
0xb7de8  ldloc.s  7
0xb7dea  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty
0xb7def  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xb7df4  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0xb7df9  castclass class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[]
0xb7dfe  stloc.s  6
0xb7e00  ldloc.s  6
0xb7e02  ldloc.s  7
0xb7e04  dup
0xb7e05  ldc.i4.1
0xb7e06  add
0xb7e07  stloc.s  7
0xb7e09  ldarg.0
0xb7e0a  ldc.i4.0
0xb7e0b  ldc.i4.1
0xb7e0c  call     instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read159_activityparty(bool isNullable, bool checkType)
0xb7e11  stelem.ref
0xb7e12  br.s     loc_B7E2E
0xb7e14  ldarg.0
  ... truncated ...
```
