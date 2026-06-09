# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read416_campaignresponse

- ea: `0xcd9d0`
- end: `0xcea5e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read416_campaignresponse`
- size: `4238`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xf0cc0`
- `0x154590`

## callees

- `0x79630`
- `0x79a60`
- `0x90c00`
- `0x91060`
- `0x91320`
- `0x91730`
- `0x95710`
- `0x95f10`
- `0x9aa80`
- `0xcd9d0`
- `0xcea60`

## string_xrefs

- `0xcddf1`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xcddff`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xce06b`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xce079`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xce474`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xce482`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xcea09`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:channeltypecode, http://schemas.microsoft.com/crm/2007/WebServices:companyname, http://schemas.microsoft.com/crm/2007/WebServices:c`
- `0xcea17`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:channeltypecode, http://schemas.microsoft.com/crm/2007/WebServices:companyname, http://schemas.microsoft.com/crm/2007/WebServices:c`

## pseudocode

```c

```

## disassembly

```asm
0xcd9d0  ldarg.2
0xcd9d1  brtrue.s loc_CD9D6
0xcd9d3  ldnull
0xcd9d4  br.s     loc_CD9DC
0xcd9d6  ldarg.0
0xcd9d7  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xcd9dc  stloc.0
0xcd9dd  ldc.i4.0
0xcd9de  stloc.1
0xcd9df  ldarg.1
0xcd9e0  brfalse.s loc_CD9E9
0xcd9e2  ldarg.0
0xcd9e3  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xcd9e8  stloc.1
0xcd9e9  ldarg.2
0xcd9ea  brfalse.s loc_CDA19
0xcd9ec  ldloc.0
0xcd9ed  ldnull
0xcd9ee  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xcd9f3  brtrue.s loc_CDA19
0xcd9f5  ldloc.0
0xcd9f6  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xcd9fb  ldarg.0
0xcd9fc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1707_campaignresponse
0xcda01  bne.un.s loc_CDA11
0xcda03  ldloc.0
0xcda04  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xcda09  ldarg.0
0xcda0a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcda0f  beq.s    loc_CDA19
0xcda11  ldarg.0
0xcda12  ldloc.0
0xcda13  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xcda18  throw
0xcda19  ldloc.1
0xcda1a  brfalse.s loc_CDA1E
0xcda1c  ldnull
0xcda1d  ret
0xcda1e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::.ctor()
0xcda23  stloc.2
0xcda24  ldc.i4.s 0x2D
0xcda26  newarr   [mscorlib]System.Boolean
0xcda2b  stloc.3
0xcda2c  br.s     loc_CDA48
0xcda2e  ldarg.0
0xcda2f  ldarg.0
0xcda30  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcda35  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xcda3a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xcda3f  brtrue.s loc_CDA48
0xcda41  ldarg.0
0xcda42  ldloc.2
0xcda43  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xcda48  ldarg.0
0xcda49  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcda4e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xcda53  brtrue.s loc_CDA2E
0xcda55  ldarg.0
0xcda56  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcda5b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xcda60  pop
0xcda61  ldarg.0
0xcda62  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcda67  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xcda6c  brfalse.s loc_CDA7B
0xcda6e  ldarg.0
0xcda6f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcda74  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xcda79  ldloc.2
0xcda7a  ret
0xcda7b  ldarg.0
0xcda7c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcda81  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xcda86  ldarg.0
0xcda87  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcda8c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xcda91  pop
0xcda92  ldc.i4.0
0xcda93  stloc.s  4
0xcda95  ldarg.0
0xcda96  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xcda9b  stloc.s  5
0xcda9d  br       loc_CEA37
0xcdaa2  ldarg.0
0xcdaa3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdaa8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xcdaad  ldc.i4.1
0xcdaae  bne.un   loc_CEA15
0xcdab3  ldloc.3
0xcdab4  ldc.i4.0
0xcdab5  ldelem.i1
0xcdab6  brtrue.s loc_CDAF5
0xcdab8  ldarg.0
0xcdab9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdabe  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdac3  ldarg.0
0xcdac4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xcdac9  bne.un.s loc_CDAF5
0xcdacb  ldarg.0
0xcdacc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdad1  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdad6  ldarg.0
0xcdad7  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdadc  bne.un.s loc_CDAF5
0xcdade  ldloc.2
0xcdadf  ldarg.0
0xcdae0  ldc.i4.0
0xcdae1  ldc.i4.1
0xcdae2  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xcdae7  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xcdaec  ldloc.3
0xcdaed  ldc.i4.0
0xcdaee  ldc.i4.1
0xcdaef  stelem.i1
0xcdaf0  br       loc_CEA21
0xcdaf5  ldloc.3
0xcdaf6  ldc.i4.1
0xcdaf7  ldelem.i1
0xcdaf8  brtrue.s loc_CDB37
0xcdafa  ldarg.0
0xcdafb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdb00  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdb05  ldarg.0
0xcdb06  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xcdb0b  bne.un.s loc_CDB37
0xcdb0d  ldarg.0
0xcdb0e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdb13  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdb18  ldarg.0
0xcdb19  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdb1e  bne.un.s loc_CDB37
0xcdb20  ldloc.2
0xcdb21  ldarg.0
0xcdb22  ldc.i4.0
0xcdb23  ldc.i4.1
0xcdb24  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xcdb29  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xcdb2e  ldloc.3
0xcdb2f  ldc.i4.1
0xcdb30  ldc.i4.1
0xcdb31  stelem.i1
0xcdb32  br       loc_CEA21
0xcdb37  ldloc.3
0xcdb38  ldc.i4.2
0xcdb39  ldelem.i1
0xcdb3a  brtrue.s loc_CDB79
0xcdb3c  ldarg.0
0xcdb3d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdb42  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdb47  ldarg.0
0xcdb48  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xcdb4d  bne.un.s loc_CDB79
0xcdb4f  ldarg.0
0xcdb50  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdb55  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdb5a  ldarg.0
0xcdb5b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdb60  bne.un.s loc_CDB79
0xcdb62  ldloc.2
0xcdb63  ldarg.0
0xcdb64  ldc.i4.0
0xcdb65  ldc.i4.1
0xcdb66  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xcdb6b  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xcdb70  ldloc.3
0xcdb71  ldc.i4.2
0xcdb72  ldc.i4.1
0xcdb73  stelem.i1
0xcdb74  br       loc_CEA21
0xcdb79  ldloc.3
0xcdb7a  ldc.i4.3
0xcdb7b  ldelem.i1
0xcdb7c  brtrue.s loc_CDBBB
0xcdb7e  ldarg.0
0xcdb7f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdb84  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdb89  ldarg.0
0xcdb8a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xcdb8f  bne.un.s loc_CDBBB
0xcdb91  ldarg.0
0xcdb92  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdb97  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdb9c  ldarg.0
0xcdb9d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdba2  bne.un.s loc_CDBBB
0xcdba4  ldloc.2
0xcdba5  ldarg.0
0xcdba6  ldc.i4.0
0xcdba7  ldc.i4.1
0xcdba8  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xcdbad  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xcdbb2  ldloc.3
0xcdbb3  ldc.i4.3
0xcdbb4  ldc.i4.1
0xcdbb5  stelem.i1
0xcdbb6  br       loc_CEA21
0xcdbbb  ldloc.3
0xcdbbc  ldc.i4.4
0xcdbbd  ldelem.i1
0xcdbbe  brtrue.s loc_CDC00
0xcdbc0  ldarg.0
0xcdbc1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdbc6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdbcb  ldarg.0
0xcdbcc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1971_category
0xcdbd1  bne.un.s loc_CDC00
0xcdbd3  ldarg.0
0xcdbd4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdbd9  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdbde  ldarg.0
0xcdbdf  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdbe4  bne.un.s loc_CDC00
0xcdbe6  ldloc.2
0xcdbe7  ldarg.0
0xcdbe8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdbed  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xcdbf2  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_category(string)
0xcdbf7  ldloc.3
0xcdbf8  ldc.i4.4
0xcdbf9  ldc.i4.1
0xcdbfa  stelem.i1
0xcdbfb  br       loc_CEA21
0xcdc00  ldloc.3
0xcdc01  ldc.i4.5
0xcdc02  ldelem.i1
0xcdc03  brtrue.s loc_CDC42
0xcdc05  ldarg.0
0xcdc06  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdc0b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdc10  ldarg.0
0xcdc11  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2763_channeltypecode
0xcdc16  bne.un.s loc_CDC42
0xcdc18  ldarg.0
0xcdc19  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdc1e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdc23  ldarg.0
0xcdc24  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdc29  bne.un.s loc_CDC42
0xcdc2b  ldloc.2
0xcdc2c  ldarg.0
0xcdc2d  ldc.i4.0
0xcdc2e  ldc.i4.1
0xcdc2f  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read141_Picklist(bool isNullable, bool checkType)
0xcdc34  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_channeltypecode(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist)
0xcdc39  ldloc.3
0xcdc3a  ldc.i4.5
0xcdc3b  ldc.i4.1
0xcdc3c  stelem.i1
0xcdc3d  br       loc_CEA21
0xcdc42  ldloc.3
0xcdc43  ldc.i4.6
0xcdc44  ldelem.i1
0xcdc45  brtrue.s loc_CDC87
0xcdc47  ldarg.0
0xcdc48  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdc4d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdc52  ldarg.0
0xcdc53  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2478_companyname
0xcdc58  bne.un.s loc_CDC87
0xcdc5a  ldarg.0
0xcdc5b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdc60  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdc65  ldarg.0
0xcdc66  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdc6b  bne.un.s loc_CDC87
0xcdc6d  ldloc.2
0xcdc6e  ldarg.0
0xcdc6f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdc74  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xcdc79  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_companyname(string)
0xcdc7e  ldloc.3
0xcdc7f  ldc.i4.6
0xcdc80  ldc.i4.1
0xcdc81  stelem.i1
0xcdc82  br       loc_CEA21
0xcdc87  ldloc.3
0xcdc88  ldc.i4.7
0xcdc89  ldelem.i1
0xcdc8a  brtrue.s loc_CDCC9
0xcdc8c  ldarg.0
0xcdc8d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdc92  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcdc97  ldarg.0
0xcdc98  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1808_createdby
0xcdc9d  bne.un.s loc_CDCC9
0xcdc9f  ldarg.0
0xcdca0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcdca5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcdcaa  ldarg.0
0xcdcab  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcdcb0  bne.un.s loc_CDCC9
0xcdcb2  ldloc.2
0xcdcb3  ldarg.0
0xcdcb4  ldc.i4.0
0xcdcb5  ldc.i4.1
0xcdcb6  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read126_Lookup(bool isNullable, bool checkType)
0xcdcbb  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignresponse::set_createdby(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup)
0xcdcc0  ldloc.3
0xcdcc1  ldc.i4.7
0xcdcc2  ldc.i4.1
  ... truncated ...
```
