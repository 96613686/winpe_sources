# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read420_campaignactivity

- ea: `0xcec30`
- end: `0xcfa76`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read420_campaignactivity`
- size: `3654`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xf0e40`
- `0x154710`

## callees

- `0x79630`
- `0x79a60`
- `0x90c00`
- `0x90e30`
- `0x91060`
- `0x91320`
- `0x91730`
- `0x918b0`
- `0x95710`
- `0x95f10`
- `0x9aa80`
- `0xcec30`
- `0xcfa80`

## string_xrefs

- `0xcf22d`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xcf23b`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xcf5ef`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xcf5fd`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xcfa21`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualcost, http://schemas.microsoft.com/crm/2007/WebServices:actualcost_base, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:budgetedcost, http://schemas.microsoft.com/crm/2007/WebService`
- `0xcfa2f`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualcost, http://schemas.microsoft.com/crm/2007/WebServices:actualcost_base, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:budgetedcost, http://schemas.microsoft.com/crm/2007/WebService`

## pseudocode

```c

```

## disassembly

```asm
0xcec30  ldarg.2
0xcec31  brtrue.s loc_CEC36
0xcec33  ldnull
0xcec34  br.s     loc_CEC3C
0xcec36  ldarg.0
0xcec37  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xcec3c  stloc.0
0xcec3d  ldc.i4.0
0xcec3e  stloc.1
0xcec3f  ldarg.1
0xcec40  brfalse.s loc_CEC49
0xcec42  ldarg.0
0xcec43  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xcec48  stloc.1
0xcec49  ldarg.2
0xcec4a  brfalse.s loc_CEC79
0xcec4c  ldloc.0
0xcec4d  ldnull
0xcec4e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xcec53  brtrue.s loc_CEC79
0xcec55  ldloc.0
0xcec56  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xcec5b  ldarg.0
0xcec5c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1706_campaignactivity
0xcec61  bne.un.s loc_CEC71
0xcec63  ldloc.0
0xcec64  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xcec69  ldarg.0
0xcec6a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcec6f  beq.s    loc_CEC79
0xcec71  ldarg.0
0xcec72  ldloc.0
0xcec73  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xcec78  throw
0xcec79  ldloc.1
0xcec7a  brfalse.s loc_CEC7E
0xcec7c  ldnull
0xcec7d  ret
0xcec7e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::.ctor()
0xcec83  stloc.2
0xcec84  ldc.i4.s 0x29
0xcec86  newarr   [mscorlib]System.Boolean
0xcec8b  stloc.3
0xcec8c  br.s     loc_CECA8
0xcec8e  ldarg.0
0xcec8f  ldarg.0
0xcec90  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcec95  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xcec9a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xcec9f  brtrue.s loc_CECA8
0xceca1  ldarg.0
0xceca2  ldloc.2
0xceca3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xceca8  ldarg.0
0xceca9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcecae  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xcecb3  brtrue.s loc_CEC8E
0xcecb5  ldarg.0
0xcecb6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcecbb  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xcecc0  pop
0xcecc1  ldarg.0
0xcecc2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcecc7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xceccc  brfalse.s loc_CECDB
0xcecce  ldarg.0
0xceccf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcecd4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xcecd9  ldloc.2
0xcecda  ret
0xcecdb  ldarg.0
0xcecdc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcece1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xcece6  ldarg.0
0xcece7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcecec  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xcecf1  pop
0xcecf2  ldc.i4.0
0xcecf3  stloc.s  4
0xcecf5  ldarg.0
0xcecf6  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xcecfb  stloc.s  5
0xcecfd  br       loc_CFA4F
0xced02  ldarg.0
0xced03  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xced08  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xced0d  ldc.i4.1
0xced0e  bne.un   loc_CFA2D
0xced13  ldloc.3
0xced14  ldc.i4.0
0xced15  ldelem.i1
0xced16  brtrue.s loc_CED55
0xced18  ldarg.0
0xced19  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xced1e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xced23  ldarg.0
0xced24  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xced29  bne.un.s loc_CED55
0xced2b  ldarg.0
0xced2c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xced31  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xced36  ldarg.0
0xced37  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xced3c  bne.un.s loc_CED55
0xced3e  ldloc.2
0xced3f  ldarg.0
0xced40  ldc.i4.0
0xced41  ldc.i4.1
0xced42  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xced47  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xced4c  ldloc.3
0xced4d  ldc.i4.0
0xced4e  ldc.i4.1
0xced4f  stelem.i1
0xced50  br       loc_CFA39
0xced55  ldloc.3
0xced56  ldc.i4.1
0xced57  ldelem.i1
0xced58  brtrue.s loc_CED97
0xced5a  ldarg.0
0xced5b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xced60  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xced65  ldarg.0
0xced66  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2771_actualcost
0xced6b  bne.un.s loc_CED97
0xced6d  ldarg.0
0xced6e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xced73  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xced78  ldarg.0
0xced79  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xced7e  bne.un.s loc_CED97
0xced80  ldloc.2
0xced81  ldarg.0
0xced82  ldc.i4.0
0xced83  ldc.i4.1
0xced84  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read156_CrmMoney(bool isNullable, bool checkType)
0xced89  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_actualcost(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney)
0xced8e  ldloc.3
0xced8f  ldc.i4.1
0xced90  ldc.i4.1
0xced91  stelem.i1
0xced92  br       loc_CFA39
0xced97  ldloc.3
0xced98  ldc.i4.2
0xced99  ldelem.i1
0xced9a  brtrue.s loc_CEDD9
0xced9c  ldarg.0
0xced9d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xceda2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xceda7  ldarg.0
0xceda8  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2772_actualcost_base
0xcedad  bne.un.s loc_CEDD9
0xcedaf  ldarg.0
0xcedb0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcedb5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcedba  ldarg.0
0xcedbb  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcedc0  bne.un.s loc_CEDD9
0xcedc2  ldloc.2
0xcedc3  ldarg.0
0xcedc4  ldc.i4.0
0xcedc5  ldc.i4.1
0xcedc6  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read156_CrmMoney(bool isNullable, bool checkType)
0xcedcb  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_actualcost_base(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney)
0xcedd0  ldloc.3
0xcedd1  ldc.i4.2
0xcedd2  ldc.i4.1
0xcedd3  stelem.i1
0xcedd4  br       loc_CFA39
0xcedd9  ldloc.3
0xcedda  ldc.i4.3
0xceddb  ldelem.i1
0xceddc  brtrue.s loc_CEE1B
0xcedde  ldarg.0
0xceddf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcede4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcede9  ldarg.0
0xcedea  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xcedef  bne.un.s loc_CEE1B
0xcedf1  ldarg.0
0xcedf2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcedf7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcedfc  ldarg.0
0xcedfd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcee02  bne.un.s loc_CEE1B
0xcee04  ldloc.2
0xcee05  ldarg.0
0xcee06  ldc.i4.0
0xcee07  ldc.i4.1
0xcee08  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xcee0d  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xcee12  ldloc.3
0xcee13  ldc.i4.3
0xcee14  ldc.i4.1
0xcee15  stelem.i1
0xcee16  br       loc_CFA39
0xcee1b  ldloc.3
0xcee1c  ldc.i4.4
0xcee1d  ldelem.i1
0xcee1e  brtrue.s loc_CEE5D
0xcee20  ldarg.0
0xcee21  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcee26  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcee2b  ldarg.0
0xcee2c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xcee31  bne.un.s loc_CEE5D
0xcee33  ldarg.0
0xcee34  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcee39  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcee3e  ldarg.0
0xcee3f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcee44  bne.un.s loc_CEE5D
0xcee46  ldloc.2
0xcee47  ldarg.0
0xcee48  ldc.i4.0
0xcee49  ldc.i4.1
0xcee4a  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xcee4f  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xcee54  ldloc.3
0xcee55  ldc.i4.4
0xcee56  ldc.i4.1
0xcee57  stelem.i1
0xcee58  br       loc_CFA39
0xcee5d  ldloc.3
0xcee5e  ldc.i4.5
0xcee5f  ldelem.i1
0xcee60  brtrue.s loc_CEE9F
0xcee62  ldarg.0
0xcee63  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcee68  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xcee6d  ldarg.0
0xcee6e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xcee73  bne.un.s loc_CEE9F
0xcee75  ldarg.0
0xcee76  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xcee7b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcee80  ldarg.0
0xcee81  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcee86  bne.un.s loc_CEE9F
0xcee88  ldloc.2
0xcee89  ldarg.0
0xcee8a  ldc.i4.0
0xcee8b  ldc.i4.1
0xcee8c  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xcee91  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xcee96  ldloc.3
0xcee97  ldc.i4.5
0xcee98  ldc.i4.1
0xcee99  stelem.i1
0xcee9a  br       loc_CFA39
0xcee9f  ldloc.3
0xceea0  ldc.i4.6
0xceea1  ldelem.i1
0xceea2  brtrue.s loc_CEEE1
0xceea4  ldarg.0
0xceea5  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xceeaa  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xceeaf  ldarg.0
0xceeb0  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2773_budgetedcost
0xceeb5  bne.un.s loc_CEEE1
0xceeb7  ldarg.0
0xceeb8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xceebd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xceec2  ldarg.0
0xceec3  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xceec8  bne.un.s loc_CEEE1
0xceeca  ldloc.2
0xceecb  ldarg.0
0xceecc  ldc.i4.0
0xceecd  ldc.i4.1
0xceece  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read156_CrmMoney(bool isNullable, bool checkType)
0xceed3  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_budgetedcost(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney)
0xceed8  ldloc.3
0xceed9  ldc.i4.6
0xceeda  ldc.i4.1
0xceedb  stelem.i1
0xceedc  br       loc_CFA39
0xceee1  ldloc.3
0xceee2  ldc.i4.7
0xceee3  ldelem.i1
0xceee4  brtrue.s loc_CEF23
0xceee6  ldarg.0
0xceee7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xceeec  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xceef1  ldarg.0
0xceef2  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2774_budgetedcost_base
0xceef7  bne.un.s loc_CEF23
0xceef9  ldarg.0
0xceefa  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xceeff  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xcef04  ldarg.0
0xcef05  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xcef0a  bne.un.s loc_CEF23
0xcef0c  ldloc.2
0xcef0d  ldarg.0
0xcef0e  ldc.i4.0
0xcef0f  ldc.i4.1
0xcef10  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read156_CrmMoney(bool isNullable, bool checkType)
0xcef15  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.campaignactivity::set_budgetedcost_base(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney)
0xcef1a  ldloc.3
  ... truncated ...
```
