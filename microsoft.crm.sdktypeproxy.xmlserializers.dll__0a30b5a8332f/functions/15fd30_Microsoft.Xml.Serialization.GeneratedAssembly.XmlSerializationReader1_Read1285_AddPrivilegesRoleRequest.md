# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1285_AddPrivilegesRoleRequest

- ea: `0x15fd30`
- end: `0x16016c`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read1285_AddPrivilegesRoleRequest`
- size: `1084`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x161620`

## callees

- `0x97c70`
- `0xdd390`
- `0x15fd30`

## string_xrefs

- `0x15fef8`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x15ff06`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1600a0`: `http://schemas.microsoft.com/crm/2007/WebServices:RolePrivilege`
- `0x1600ae`: `http://schemas.microsoft.com/crm/2007/WebServices:RolePrivilege`
- `0x160117`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:RoleId, http://schemas.microsoft.com/crm/2007/WebServices:Privileges`
- `0x160125`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:RoleId, http://schemas.microsoft.com/crm/2007/WebServices:Privileges`

## pseudocode

```c

```

## disassembly

```asm
0x15fd30  ldarg.2
0x15fd31  brtrue.s loc_15FD36
0x15fd33  ldnull
0x15fd34  br.s     loc_15FD3C
0x15fd36  ldarg.0
0x15fd37  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x15fd3c  stloc.0
0x15fd3d  ldc.i4.0
0x15fd3e  stloc.1
0x15fd3f  ldarg.1
0x15fd40  brfalse.s loc_15FD49
0x15fd42  ldarg.0
0x15fd43  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15fd48  stloc.1
0x15fd49  ldarg.2
0x15fd4a  brfalse.s loc_15FD79
0x15fd4c  ldloc.0
0x15fd4d  ldnull
0x15fd4e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x15fd53  brtrue.s loc_15FD79
0x15fd55  ldloc.0
0x15fd56  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x15fd5b  ldarg.0
0x15fd5c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1369_AddPrivilegesRoleRequest
0x15fd61  bne.un.s loc_15FD71
0x15fd63  ldloc.0
0x15fd64  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x15fd69  ldarg.0
0x15fd6a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15fd6f  beq.s    loc_15FD79
0x15fd71  ldarg.0
0x15fd72  ldloc.0
0x15fd73  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x15fd78  throw
0x15fd79  ldloc.1
0x15fd7a  brfalse.s loc_15FD7E
0x15fd7c  ldnull
0x15fd7d  ret
0x15fd7e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddPrivilegesRoleRequest::.ctor()
0x15fd83  stloc.2
0x15fd84  ldc.i4.3
0x15fd85  newarr   [mscorlib]System.Boolean
0x15fd8a  stloc.3
0x15fd8b  br.s     loc_15FDA7
0x15fd8d  ldarg.0
0x15fd8e  ldarg.0
0x15fd8f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fd94  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x15fd99  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x15fd9e  brtrue.s loc_15FDA7
0x15fda0  ldarg.0
0x15fda1  ldloc.2
0x15fda2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x15fda7  ldarg.0
0x15fda8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fdad  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x15fdb2  brtrue.s loc_15FD8D
0x15fdb4  ldarg.0
0x15fdb5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fdba  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x15fdbf  pop
0x15fdc0  ldarg.0
0x15fdc1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fdc6  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15fdcb  brfalse.s loc_15FDDA
0x15fdcd  ldarg.0
0x15fdce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fdd3  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15fdd8  ldloc.2
0x15fdd9  ret
0x15fdda  ldarg.0
0x15fddb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fde0  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15fde5  ldarg.0
0x15fde6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fdeb  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15fdf0  pop
0x15fdf1  ldc.i4.0
0x15fdf2  stloc.s  4
0x15fdf4  ldarg.0
0x15fdf5  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15fdfa  stloc.s  5
0x15fdfc  br       loc_160145
0x15fe01  ldarg.0
0x15fe02  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe07  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15fe0c  ldc.i4.1
0x15fe0d  bne.un   loc_160123
0x15fe12  ldarg.0
0x15fe13  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe18  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15fe1d  ldarg.0
0x15fe1e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x15fe23  bne.un   loc_15FF70
0x15fe28  ldarg.0
0x15fe29  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe2e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15fe33  ldarg.0
0x15fe34  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15fe39  bne.un   loc_15FF70
0x15fe3e  ldarg.0
0x15fe3f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15fe44  brtrue   loc_16012F
0x15fe49  ldnull
0x15fe4a  stloc.s  6
0x15fe4c  ldc.i4.0
0x15fe4d  stloc.s  7
0x15fe4f  ldarg.0
0x15fe50  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe55  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x15fe5a  brfalse.s loc_15FE6C
0x15fe5c  ldarg.0
0x15fe5d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe62  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x15fe67  br       loc_15FF4B
0x15fe6c  ldarg.0
0x15fe6d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe72  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x15fe77  ldarg.0
0x15fe78  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe7d  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15fe82  pop
0x15fe83  ldc.i4.0
0x15fe84  stloc.s  8
0x15fe86  ldarg.0
0x15fe87  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x15fe8c  stloc.s  9
0x15fe8e  br       loc_15FF26
0x15fe93  ldarg.0
0x15fe94  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fe99  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15fe9e  ldc.i4.1
0x15fe9f  bne.un.s loc_15FF04
0x15fea1  ldarg.0
0x15fea2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fea7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15feac  ldarg.0
0x15fead  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x15feb2  bne.un.s loc_15FEF6
0x15feb4  ldarg.0
0x15feb5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15feba  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15febf  ldarg.0
0x15fec0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15fec5  bne.un.s loc_15FEF6
0x15fec7  ldarg.0
0x15fec8  ldloc.s  6
0x15feca  ldloc.s  7
0x15fecc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15fed1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15fed6  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x15fedb  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15fee0  stloc.s  6
0x15fee2  ldloc.s  6
0x15fee4  ldloc.s  7
0x15fee6  dup
0x15fee7  ldc.i4.1
0x15fee8  add
0x15fee9  stloc.s  7
0x15feeb  ldarg.0
0x15feec  ldc.i4.1
0x15feed  ldc.i4.1
0x15feee  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x15fef3  stelem.ref
0x15fef4  br.s     loc_15FF10
0x15fef6  ldarg.0
0x15fef7  ldnull
0x15fef8  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15fefd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15ff02  br.s     loc_15FF10
0x15ff04  ldarg.0
0x15ff05  ldnull
0x15ff06  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x15ff0b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x15ff10  ldarg.0
0x15ff11  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ff16  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x15ff1b  pop
0x15ff1c  ldarg.0
0x15ff1d  ldloca.s 8
0x15ff1f  ldloca.s 9
0x15ff21  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x15ff26  ldarg.0
0x15ff27  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ff2c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15ff31  ldc.i4.s 0xF
0x15ff33  beq.s    loc_15FF45
0x15ff35  ldarg.0
0x15ff36  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ff3b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x15ff40  brtrue   loc_15FE93
0x15ff45  ldarg.0
0x15ff46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x15ff4b  ldloc.2
0x15ff4c  ldarg.0
0x15ff4d  ldloc.s  6
0x15ff4f  ldloc.s  7
0x15ff51  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x15ff56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15ff5b  ldc.i4.0
0x15ff5c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x15ff61  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x15ff66  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x15ff6b  br       loc_16012F
0x15ff70  ldloc.3
0x15ff71  ldc.i4.1
0x15ff72  ldelem.i1
0x15ff73  brtrue.s loc_15FFBA
0x15ff75  ldarg.0
0x15ff76  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ff7b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15ff80  ldarg.0
0x15ff81  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3173_RoleId
0x15ff86  bne.un.s loc_15FFBA
0x15ff88  ldarg.0
0x15ff89  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ff8e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15ff93  ldarg.0
0x15ff94  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15ff99  bne.un.s loc_15FFBA
0x15ff9b  ldloc.2
0x15ff9c  ldarg.0
0x15ff9d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ffa2  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x15ffa7  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x15ffac  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddPrivilegesRoleRequest::set_RoleId(valuetype [mscorlib]System.Guid)
0x15ffb1  ldloc.3
0x15ffb2  ldc.i4.1
0x15ffb3  ldc.i4.1
0x15ffb4  stelem.i1
0x15ffb5  br       loc_16012F
0x15ffba  ldarg.0
0x15ffbb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ffc0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x15ffc5  ldarg.0
0x15ffc6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id77_Privileges
0x15ffcb  bne.un   loc_160115
0x15ffd0  ldarg.0
0x15ffd1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15ffd6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x15ffdb  ldarg.0
0x15ffdc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x15ffe1  bne.un   loc_160115
0x15ffe6  ldarg.0
0x15ffe7  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x15ffec  brtrue   loc_16012F
0x15fff1  ldnull
0x15fff2  stloc.s  0xA
0x15fff4  ldc.i4.0
0x15fff5  stloc.s  0xB
0x15fff7  ldarg.0
0x15fff8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x15fffd  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x160002  brfalse.s loc_160014
0x160004  ldarg.0
0x160005  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16000a  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x16000f  br       loc_1600F3
0x160014  ldarg.0
0x160015  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16001a  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x16001f  ldarg.0
0x160020  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x160025  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x16002a  pop
0x16002b  ldc.i4.0
0x16002c  stloc.s  0xC
0x16002e  ldarg.0
0x16002f  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x160034  stloc.s  0xD
0x160036  br       loc_1600CE
0x16003b  ldarg.0
0x16003c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x160041  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x160046  ldc.i4.1
0x160047  bne.un.s loc_1600AC
0x160049  ldarg.0
0x16004a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x16004f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x160054  ldarg.0
0x160055  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id340_RolePrivilege
0x16005a  bne.un.s loc_16009E
0x16005c  ldarg.0
0x16005d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x160062  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x160067  ldarg.0
0x160068  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x16006d  bne.un.s loc_16009E
0x16006f  ldarg.0
0x160070  ldloc.s  0xA
0x160072  ldloc.s  0xB
0x160074  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege
0x160079  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16007e  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x160083  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[]
0x160088  stloc.s  0xA
0x16008a  ldloc.s  0xA
0x16008c  ldloc.s  0xB
0x16008e  dup
0x16008f  ldc.i4.1
  ... truncated ...
```
