# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read858_ReplacePrivilegesRoleRequest

- ea: `0x124660`
- end: `0x124a9c`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read858_ReplacePrivilegesRoleRequest`
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
- `0x124660`

## string_xrefs

- `0x124828`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x124836`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameter`
- `0x1249d0`: `http://schemas.microsoft.com/crm/2007/WebServices:RolePrivilege`
- `0x1249de`: `http://schemas.microsoft.com/crm/2007/WebServices:RolePrivilege`
- `0x124a47`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:RoleId, http://schemas.microsoft.com/crm/2007/WebServices:Privileges`
- `0x124a55`: `http://schemas.microsoft.com/crm/2007/WebServices:OptionalParameters, http://schemas.microsoft.com/crm/2007/WebServices:RoleId, http://schemas.microsoft.com/crm/2007/WebServices:Privileges`

## pseudocode

```c

```

## disassembly

```asm
0x124660  ldarg.2
0x124661  brtrue.s loc_124666
0x124663  ldnull
0x124664  br.s     loc_12466C
0x124666  ldarg.0
0x124667  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x12466c  stloc.0
0x12466d  ldc.i4.0
0x12466e  stloc.1
0x12466f  ldarg.1
0x124670  brfalse.s loc_124679
0x124672  ldarg.0
0x124673  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x124678  stloc.1
0x124679  ldarg.2
0x12467a  brfalse.s loc_1246A9
0x12467c  ldloc.0
0x12467d  ldnull
0x12467e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x124683  brtrue.s loc_1246A9
0x124685  ldloc.0
0x124686  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x12468b  ldarg.0
0x12468c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1538_ReplacePrivilegesRoleRequest
0x124691  bne.un.s loc_1246A1
0x124693  ldloc.0
0x124694  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x124699  ldarg.0
0x12469a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x12469f  beq.s    loc_1246A9
0x1246a1  ldarg.0
0x1246a2  ldloc.0
0x1246a3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x1246a8  throw
0x1246a9  ldloc.1
0x1246aa  brfalse.s loc_1246AE
0x1246ac  ldnull
0x1246ad  ret
0x1246ae  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ReplacePrivilegesRoleRequest::.ctor()
0x1246b3  stloc.2
0x1246b4  ldc.i4.3
0x1246b5  newarr   [mscorlib]System.Boolean
0x1246ba  stloc.3
0x1246bb  br.s     loc_1246D7
0x1246bd  ldarg.0
0x1246be  ldarg.0
0x1246bf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1246c4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x1246c9  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x1246ce  brtrue.s loc_1246D7
0x1246d0  ldarg.0
0x1246d1  ldloc.2
0x1246d2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x1246d7  ldarg.0
0x1246d8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1246dd  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x1246e2  brtrue.s loc_1246BD
0x1246e4  ldarg.0
0x1246e5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1246ea  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x1246ef  pop
0x1246f0  ldarg.0
0x1246f1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1246f6  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1246fb  brfalse.s loc_12470A
0x1246fd  ldarg.0
0x1246fe  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124703  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x124708  ldloc.2
0x124709  ret
0x12470a  ldarg.0
0x12470b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124710  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x124715  ldarg.0
0x124716  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12471b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x124720  pop
0x124721  ldc.i4.0
0x124722  stloc.s  4
0x124724  ldarg.0
0x124725  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x12472a  stloc.s  5
0x12472c  br       loc_124A75
0x124731  ldarg.0
0x124732  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124737  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x12473c  ldc.i4.1
0x12473d  bne.un   loc_124A53
0x124742  ldarg.0
0x124743  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124748  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x12474d  ldarg.0
0x12474e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2940_OptionalParameters
0x124753  bne.un   loc_1248A0
0x124758  ldarg.0
0x124759  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12475e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x124763  ldarg.0
0x124764  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x124769  bne.un   loc_1248A0
0x12476e  ldarg.0
0x12476f  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x124774  brtrue   loc_124A5F
0x124779  ldnull
0x12477a  stloc.s  6
0x12477c  ldc.i4.0
0x12477d  stloc.s  7
0x12477f  ldarg.0
0x124780  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124785  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x12478a  brfalse.s loc_12479C
0x12478c  ldarg.0
0x12478d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124792  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x124797  br       loc_12487B
0x12479c  ldarg.0
0x12479d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1247a2  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x1247a7  ldarg.0
0x1247a8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1247ad  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x1247b2  pop
0x1247b3  ldc.i4.0
0x1247b4  stloc.s  8
0x1247b6  ldarg.0
0x1247b7  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x1247bc  stloc.s  9
0x1247be  br       loc_124856
0x1247c3  ldarg.0
0x1247c4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1247c9  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1247ce  ldc.i4.1
0x1247cf  bne.un.s loc_124834
0x1247d1  ldarg.0
0x1247d2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1247d7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1247dc  ldarg.0
0x1247dd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id254_OptionalParameter
0x1247e2  bne.un.s loc_124826
0x1247e4  ldarg.0
0x1247e5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1247ea  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1247ef  ldarg.0
0x1247f0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1247f5  bne.un.s loc_124826
0x1247f7  ldarg.0
0x1247f8  ldloc.s  6
0x1247fa  ldloc.s  7
0x1247fc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x124801  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x124806  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x12480b  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x124810  stloc.s  6
0x124812  ldloc.s  6
0x124814  ldloc.s  7
0x124816  dup
0x124817  ldc.i4.1
0x124818  add
0x124819  stloc.s  7
0x12481b  ldarg.0
0x12481c  ldc.i4.1
0x12481d  ldc.i4.1
0x12481e  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read167_OptionalParameter(bool isNullable, bool checkType)
0x124823  stelem.ref
0x124824  br.s     loc_124840
0x124826  ldarg.0
0x124827  ldnull
0x124828  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x12482d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x124832  br.s     loc_124840
0x124834  ldarg.0
0x124835  ldnull
0x124836  ldstr    aHttpSchemasMic_49// "http://schemas.microsoft.com/crm/2007/W"...
0x12483b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object, string)
0x124840  ldarg.0
0x124841  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124846  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12484b  pop
0x12484c  ldarg.0
0x12484d  ldloca.s 8
0x12484f  ldloca.s 9
0x124851  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::CheckReaderCount(int32&, int32&)
0x124856  ldarg.0
0x124857  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12485c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x124861  ldc.i4.s 0xF
0x124863  beq.s    loc_124875
0x124865  ldarg.0
0x124866  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12486b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x124870  brtrue   loc_1247C3
0x124875  ldarg.0
0x124876  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadEndElement()
0x12487b  ldloc.2
0x12487c  ldarg.0
0x12487d  ldloc.s  6
0x12487f  ldloc.s  7
0x124881  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x124886  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12488b  ldc.i4.0
0x12488c  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::ShrinkArray(class [mscorlib]System.Array, int32, class [mscorlib]System.Type, bool)
0x124891  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[]
0x124896  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::set_OptionalParameters(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[])
0x12489b  br       loc_124A5F
0x1248a0  ldloc.3
0x1248a1  ldc.i4.1
0x1248a2  ldelem.i1
0x1248a3  brtrue.s loc_1248EA
0x1248a5  ldarg.0
0x1248a6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1248ab  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1248b0  ldarg.0
0x1248b1  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3173_RoleId
0x1248b6  bne.un.s loc_1248EA
0x1248b8  ldarg.0
0x1248b9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1248be  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x1248c3  ldarg.0
0x1248c4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x1248c9  bne.un.s loc_1248EA
0x1248cb  ldloc.2
0x1248cc  ldarg.0
0x1248cd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1248d2  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1248d7  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x1248dc  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ReplacePrivilegesRoleRequest::set_RoleId(valuetype [mscorlib]System.Guid)
0x1248e1  ldloc.3
0x1248e2  ldc.i4.1
0x1248e3  ldc.i4.1
0x1248e4  stelem.i1
0x1248e5  br       loc_124A5F
0x1248ea  ldarg.0
0x1248eb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x1248f0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1248f5  ldarg.0
0x1248f6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id77_Privileges
0x1248fb  bne.un   loc_124A45
0x124900  ldarg.0
0x124901  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124906  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x12490b  ldarg.0
0x12490c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x124911  bne.un   loc_124A45
0x124916  ldarg.0
0x124917  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x12491c  brtrue   loc_124A5F
0x124921  ldnull
0x124922  stloc.s  0xA
0x124924  ldc.i4.0
0x124925  stloc.s  0xB
0x124927  ldarg.0
0x124928  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12492d  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x124932  brfalse.s loc_124944
0x124934  ldarg.0
0x124935  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12493a  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x12493f  br       loc_124A23
0x124944  ldarg.0
0x124945  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12494a  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x12494f  ldarg.0
0x124950  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124955  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12495a  pop
0x12495b  ldc.i4.0
0x12495c  stloc.s  0xC
0x12495e  ldarg.0
0x12495f  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x124964  stloc.s  0xD
0x124966  br       loc_1249FE
0x12496b  ldarg.0
0x12496c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124971  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x124976  ldc.i4.1
0x124977  bne.un.s loc_1249DC
0x124979  ldarg.0
0x12497a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x12497f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x124984  ldarg.0
0x124985  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id340_RolePrivilege
0x12498a  bne.un.s loc_1249CE
0x12498c  ldarg.0
0x12498d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x124992  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x124997  ldarg.0
0x124998  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x12499d  bne.un.s loc_1249CE
0x12499f  ldarg.0
0x1249a0  ldloc.s  0xA
0x1249a2  ldloc.s  0xB
0x1249a4  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege
0x1249a9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1249ae  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x1249b3  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[]
0x1249b8  stloc.s  0xA
0x1249ba  ldloc.s  0xA
0x1249bc  ldloc.s  0xB
0x1249be  dup
0x1249bf  ldc.i4.1
  ... truncated ...
```
