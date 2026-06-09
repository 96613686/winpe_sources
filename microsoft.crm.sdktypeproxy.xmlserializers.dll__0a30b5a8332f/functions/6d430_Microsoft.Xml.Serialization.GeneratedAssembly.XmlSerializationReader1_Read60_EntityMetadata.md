# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read60_EntityMetadata

- ea: `0x6d430`
- end: `0x6e253`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read60_EntityMetadata`
- size: `3619`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6d2b0`
- `0x71080`
- `0xddfc0`
- `0x185260`
- `0x1854b0`

## callees

- `0x6c710`
- `0x6d430`
- `0x6e260`
- `0x6e490`
- `0x6eaf0`
- `0x6ef50`
- `0x6f6e0`
- `0x6fcd0`
- `0x70600`
- `0x1849f0`

## string_xrefs

- `0x6db8a`: `http://schemas.microsoft.com/crm/2007/WebServices:Attribute`
- `0x6db98`: `http://schemas.microsoft.com/crm/2007/WebServices:Attribute`
- `0x6dce8`: `http://schemas.microsoft.com/crm/2007/WebServices:From`
- `0x6dcf6`: `http://schemas.microsoft.com/crm/2007/WebServices:From`
- `0x6de46`: `http://schemas.microsoft.com/crm/2007/WebServices:To`
- `0x6de54`: `http://schemas.microsoft.com/crm/2007/WebServices:To`
- `0x6dfa4`: `http://schemas.microsoft.com/crm/2007/WebServices:Privilege`
- `0x6dfb2`: `http://schemas.microsoft.com/crm/2007/WebServices:Privilege`
- `0x6e102`: `http://schemas.microsoft.com/crm/2007/WebServices:Intersect`
- `0x6e110`: `http://schemas.microsoft.com/crm/2007/WebServices:Intersect`
- `0x6e1fe`: `http://schemas.microsoft.com/crm/2007/WebServices:MetadataId, http://schemas.microsoft.com/crm/2007/WebServices:SchemaName, http://schemas.microsoft.com/crm/2007/WebServices:LogicalName, http://schemas.microsoft.com/crm/2007/WebServices:ObjectTypeCode, http://schemas.microsoft.com/crm/2007/WebServices:DisplayName, http://schemas.microsoft.com/crm/2007/WebServices:DisplayCollectionName, http://schemas.microsoft.com/crm/2007/WebServices:Description, http://schemas.microsoft.com/crm/2007/WebService`
- `0x6e20c`: `http://schemas.microsoft.com/crm/2007/WebServices:MetadataId, http://schemas.microsoft.com/crm/2007/WebServices:SchemaName, http://schemas.microsoft.com/crm/2007/WebServices:LogicalName, http://schemas.microsoft.com/crm/2007/WebServices:ObjectTypeCode, http://schemas.microsoft.com/crm/2007/WebServices:DisplayName, http://schemas.microsoft.com/crm/2007/WebServices:DisplayCollectionName, http://schemas.microsoft.com/crm/2007/WebServices:Description, http://schemas.microsoft.com/crm/2007/WebService`

## pseudocode

```c

```

## disassembly

```asm
0x6d430  ldarg.2
0x6d431  brtrue.s loc_6D436
0x6d433  ldnull
0x6d434  br.s     loc_6D43C
0x6d436  ldarg.0
0x6d437  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x6d43c  stloc.0
0x6d43d  ldc.i4.0
0x6d43e  stloc.1
0x6d43f  ldarg.1
0x6d440  brfalse.s loc_6D449
0x6d442  ldarg.0
0x6d443  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x6d448  stloc.1
0x6d449  ldarg.2
0x6d44a  brfalse.s loc_6D479
0x6d44c  ldloc.0
0x6d44d  ldnull
0x6d44e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x6d453  brtrue.s loc_6D479
0x6d455  ldloc.0
0x6d456  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x6d45b  ldarg.0
0x6d45c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id49_EntityMetadata
0x6d461  bne.un.s loc_6D471
0x6d463  ldloc.0
0x6d464  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x6d469  ldarg.0
0x6d46a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d46f  beq.s    loc_6D479
0x6d471  ldarg.0
0x6d472  ldloc.0
0x6d473  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x6d478  throw
0x6d479  ldloc.1
0x6d47a  brfalse.s loc_6D47E
0x6d47c  ldnull
0x6d47d  ret
0x6d47e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::.ctor()
0x6d483  stloc.2
0x6d484  ldc.i4.s 0x1C
0x6d486  newarr   [mscorlib]System.Boolean
0x6d48b  stloc.3
0x6d48c  br.s     loc_6D4A8
0x6d48e  ldarg.0
0x6d48f  ldarg.0
0x6d490  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d495  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x6d49a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x6d49f  brtrue.s loc_6D4A8
0x6d4a1  ldarg.0
0x6d4a2  ldloc.2
0x6d4a3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x6d4a8  ldarg.0
0x6d4a9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d4ae  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x6d4b3  brtrue.s loc_6D48E
0x6d4b5  ldarg.0
0x6d4b6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d4bb  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x6d4c0  pop
0x6d4c1  ldarg.0
0x6d4c2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d4c7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x6d4cc  brfalse.s loc_6D4DB
0x6d4ce  ldarg.0
0x6d4cf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d4d4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x6d4d9  ldloc.2
0x6d4da  ret
0x6d4db  ldarg.0
0x6d4dc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d4e1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x6d4e6  ldarg.0
0x6d4e7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d4ec  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x6d4f1  pop
0x6d4f2  ldc.i4.0
0x6d4f3  stloc.s  4
0x6d4f5  ldarg.0
0x6d4f6  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x6d4fb  stloc.s  5
0x6d4fd  br       loc_6E22C
0x6d502  ldarg.0
0x6d503  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d508  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x6d50d  ldc.i4.1
0x6d50e  bne.un   loc_6E20A
0x6d513  ldloc.3
0x6d514  ldc.i4.0
0x6d515  ldelem.i1
0x6d516  brtrue.s loc_6D555
0x6d518  ldarg.0
0x6d519  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d51e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d523  ldarg.0
0x6d524  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id50_MetadataId
0x6d529  bne.un.s loc_6D555
0x6d52b  ldarg.0
0x6d52c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d531  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d536  ldarg.0
0x6d537  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d53c  bne.un.s loc_6D555
0x6d53e  ldloc.2
0x6d53f  ldarg.0
0x6d540  ldc.i4.0
0x6d541  ldc.i4.1
0x6d542  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read6_Key(bool isNullable, bool checkType)
0x6d547  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmMetadata::set_MetadataId(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0x6d54c  ldloc.3
0x6d54d  ldc.i4.0
0x6d54e  ldc.i4.1
0x6d54f  stelem.i1
0x6d550  br       loc_6E216
0x6d555  ldloc.3
0x6d556  ldc.i4.1
0x6d557  ldelem.i1
0x6d558  brtrue.s loc_6D59A
0x6d55a  ldarg.0
0x6d55b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d560  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d565  ldarg.0
0x6d566  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id51_SchemaName
0x6d56b  bne.un.s loc_6D59A
0x6d56d  ldarg.0
0x6d56e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d573  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d578  ldarg.0
0x6d579  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d57e  bne.un.s loc_6D59A
0x6d580  ldloc.2
0x6d581  ldarg.0
0x6d582  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d587  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x6d58c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::set_SchemaName(string)
0x6d591  ldloc.3
0x6d592  ldc.i4.1
0x6d593  ldc.i4.1
0x6d594  stelem.i1
0x6d595  br       loc_6E216
0x6d59a  ldloc.3
0x6d59b  ldc.i4.2
0x6d59c  ldelem.i1
0x6d59d  brtrue.s loc_6D5DF
0x6d59f  ldarg.0
0x6d5a0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d5a5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d5aa  ldarg.0
0x6d5ab  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id52_LogicalName
0x6d5b0  bne.un.s loc_6D5DF
0x6d5b2  ldarg.0
0x6d5b3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d5b8  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d5bd  ldarg.0
0x6d5be  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d5c3  bne.un.s loc_6D5DF
0x6d5c5  ldloc.2
0x6d5c6  ldarg.0
0x6d5c7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d5cc  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x6d5d1  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::set_LogicalName(string)
0x6d5d6  ldloc.3
0x6d5d7  ldc.i4.2
0x6d5d8  ldc.i4.1
0x6d5d9  stelem.i1
0x6d5da  br       loc_6E216
0x6d5df  ldloc.3
0x6d5e0  ldc.i4.3
0x6d5e1  ldelem.i1
0x6d5e2  brtrue.s loc_6D621
0x6d5e4  ldarg.0
0x6d5e5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d5ea  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d5ef  ldarg.0
0x6d5f0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id53_ObjectTypeCode
0x6d5f5  bne.un.s loc_6D621
0x6d5f7  ldarg.0
0x6d5f8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d5fd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d602  ldarg.0
0x6d603  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d608  bne.un.s loc_6D621
0x6d60a  ldloc.2
0x6d60b  ldarg.0
0x6d60c  ldc.i4.0
0x6d60d  ldc.i4.1
0x6d60e  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read8_CrmNumber(bool isNullable, bool checkType)
0x6d613  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::set_ObjectTypeCode(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0x6d618  ldloc.3
0x6d619  ldc.i4.3
0x6d61a  ldc.i4.1
0x6d61b  stelem.i1
0x6d61c  br       loc_6E216
0x6d621  ldloc.3
0x6d622  ldc.i4.4
0x6d623  ldelem.i1
0x6d624  brtrue.s loc_6D663
0x6d626  ldarg.0
0x6d627  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d62c  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d631  ldarg.0
0x6d632  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id54_DisplayName
0x6d637  bne.un.s loc_6D663
0x6d639  ldarg.0
0x6d63a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d63f  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d644  ldarg.0
0x6d645  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d64a  bne.un.s loc_6D663
0x6d64c  ldloc.2
0x6d64d  ldarg.0
0x6d64e  ldc.i4.0
0x6d64f  ldc.i4.1
0x6d650  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read10_CrmLabel(bool isNullable, bool checkType)
0x6d655  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::set_DisplayName(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel)
0x6d65a  ldloc.3
0x6d65b  ldc.i4.4
0x6d65c  ldc.i4.1
0x6d65d  stelem.i1
0x6d65e  br       loc_6E216
0x6d663  ldloc.3
0x6d664  ldc.i4.5
0x6d665  ldelem.i1
0x6d666  brtrue.s loc_6D6A5
0x6d668  ldarg.0
0x6d669  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d66e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d673  ldarg.0
0x6d674  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id55_DisplayCollectionName
0x6d679  bne.un.s loc_6D6A5
0x6d67b  ldarg.0
0x6d67c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d681  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d686  ldarg.0
0x6d687  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d68c  bne.un.s loc_6D6A5
0x6d68e  ldloc.2
0x6d68f  ldarg.0
0x6d690  ldc.i4.0
0x6d691  ldc.i4.1
0x6d692  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read10_CrmLabel(bool isNullable, bool checkType)
0x6d697  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::set_DisplayCollectionName(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel)
0x6d69c  ldloc.3
0x6d69d  ldc.i4.5
0x6d69e  ldc.i4.1
0x6d69f  stelem.i1
0x6d6a0  br       loc_6E216
0x6d6a5  ldloc.3
0x6d6a6  ldc.i4.6
0x6d6a7  ldelem.i1
0x6d6a8  brtrue.s loc_6D6E7
0x6d6aa  ldarg.0
0x6d6ab  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d6b0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d6b5  ldarg.0
0x6d6b6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id56_Description
0x6d6bb  bne.un.s loc_6D6E7
0x6d6bd  ldarg.0
0x6d6be  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d6c3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d6c8  ldarg.0
0x6d6c9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d6ce  bne.un.s loc_6D6E7
0x6d6d0  ldloc.2
0x6d6d1  ldarg.0
0x6d6d2  ldc.i4.0
0x6d6d3  ldc.i4.1
0x6d6d4  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read10_CrmLabel(bool isNullable, bool checkType)
0x6d6d9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::set_Description(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmLabel)
0x6d6de  ldloc.3
0x6d6df  ldc.i4.6
0x6d6e0  ldc.i4.1
0x6d6e1  stelem.i1
0x6d6e2  br       loc_6E216
0x6d6e7  ldloc.3
0x6d6e8  ldc.i4.7
0x6d6e9  ldelem.i1
0x6d6ea  brtrue.s loc_6D729
0x6d6ec  ldarg.0
0x6d6ed  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d6f2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x6d6f7  ldarg.0
0x6d6f8  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id57_IsCustomEntity
0x6d6fd  bne.un.s loc_6D729
0x6d6ff  ldarg.0
0x6d700  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x6d705  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x6d70a  ldarg.0
0x6d70b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0x6d710  bne.un.s loc_6D729
0x6d712  ldloc.2
0x6d713  ldarg.0
0x6d714  ldc.i4.0
0x6d715  ldc.i4.1
0x6d716  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read11_CrmBoolean(bool isNullable, bool checkType)
0x6d71b  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.EntityMetadata::set_IsCustomEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean)
0x6d720  ldloc.3
0x6d721  ldc.i4.7
0x6d722  ldc.i4.1
  ... truncated ...
```
