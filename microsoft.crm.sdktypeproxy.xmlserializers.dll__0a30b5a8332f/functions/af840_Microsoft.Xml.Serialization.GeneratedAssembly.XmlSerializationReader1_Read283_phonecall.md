# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read283_phonecall

- ea: `0xaf840`
- end: `0xb0469`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read283_phonecall`
- size: `3113`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xecac0`
- `0x150210`

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
- `0xaf840`
- `0xb0470`

## string_xrefs

- `0xafc61`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xafc6f`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb035c`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb036a`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xb0414`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:createdby, http://schemas.microsoft.com/crm/2007/WebServices:createdon, http://schemas.microsoft.com/crm/2007/WebServices:descripti`
- `0xb0422`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:createdby, http://schemas.microsoft.com/crm/2007/WebServices:createdon, http://schemas.microsoft.com/crm/2007/WebServices:descripti`

## pseudocode

```c

```

## disassembly

```asm
0xaf840  ldarg.2
0xaf841  brtrue.s loc_AF846
0xaf843  ldnull
0xaf844  br.s     loc_AF84C
0xaf846  ldarg.0
0xaf847  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xaf84c  stloc.0
0xaf84d  ldc.i4.0
0xaf84e  stloc.1
0xaf84f  ldarg.1
0xaf850  brfalse.s loc_AF859
0xaf852  ldarg.0
0xaf853  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xaf858  stloc.1
0xaf859  ldarg.2
0xaf85a  brfalse.s loc_AF889
0xaf85c  ldloc.0
0xaf85d  ldnull
0xaf85e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xaf863  brtrue.s loc_AF889
0xaf865  ldloc.0
0xaf866  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xaf86b  ldarg.0
0xaf86c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1748_phonecall
0xaf871  bne.un.s loc_AF881
0xaf873  ldloc.0
0xaf874  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xaf879  ldarg.0
0xaf87a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xaf87f  beq.s    loc_AF889
0xaf881  ldarg.0
0xaf882  ldloc.0
0xaf883  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xaf888  throw
0xaf889  ldloc.1
0xaf88a  brfalse.s loc_AF88E
0xaf88c  ldnull
0xaf88d  ret
0xaf88e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::.ctor()
0xaf893  stloc.2
0xaf894  ldc.i4.s 0x21
0xaf896  newarr   [mscorlib]System.Boolean
0xaf89b  stloc.3
0xaf89c  br.s     loc_AF8B8
0xaf89e  ldarg.0
0xaf89f  ldarg.0
0xaf8a0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8a5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xaf8aa  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xaf8af  brtrue.s loc_AF8B8
0xaf8b1  ldarg.0
0xaf8b2  ldloc.2
0xaf8b3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xaf8b8  ldarg.0
0xaf8b9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8be  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xaf8c3  brtrue.s loc_AF89E
0xaf8c5  ldarg.0
0xaf8c6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8cb  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xaf8d0  pop
0xaf8d1  ldarg.0
0xaf8d2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8d7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xaf8dc  brfalse.s loc_AF8EB
0xaf8de  ldarg.0
0xaf8df  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8e4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xaf8e9  ldloc.2
0xaf8ea  ret
0xaf8eb  ldarg.0
0xaf8ec  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8f1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xaf8f6  ldarg.0
0xaf8f7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf8fc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xaf901  pop
0xaf902  ldc.i4.0
0xaf903  stloc.s  4
0xaf905  ldarg.0
0xaf906  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xaf90b  stloc.s  5
0xaf90d  br       loc_B0442
0xaf912  ldarg.0
0xaf913  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf918  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xaf91d  ldc.i4.1
0xaf91e  bne.un   loc_B0420
0xaf923  ldloc.3
0xaf924  ldc.i4.0
0xaf925  ldelem.i1
0xaf926  brtrue.s loc_AF965
0xaf928  ldarg.0
0xaf929  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf92e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xaf933  ldarg.0
0xaf934  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xaf939  bne.un.s loc_AF965
0xaf93b  ldarg.0
0xaf93c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf941  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xaf946  ldarg.0
0xaf947  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xaf94c  bne.un.s loc_AF965
0xaf94e  ldloc.2
0xaf94f  ldarg.0
0xaf950  ldc.i4.0
0xaf951  ldc.i4.1
0xaf952  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xaf957  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xaf95c  ldloc.3
0xaf95d  ldc.i4.0
0xaf95e  ldc.i4.1
0xaf95f  stelem.i1
0xaf960  br       loc_B042C
0xaf965  ldloc.3
0xaf966  ldc.i4.1
0xaf967  ldelem.i1
0xaf968  brtrue.s loc_AF9A7
0xaf96a  ldarg.0
0xaf96b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf970  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xaf975  ldarg.0
0xaf976  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xaf97b  bne.un.s loc_AF9A7
0xaf97d  ldarg.0
0xaf97e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf983  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xaf988  ldarg.0
0xaf989  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xaf98e  bne.un.s loc_AF9A7
0xaf990  ldloc.2
0xaf991  ldarg.0
0xaf992  ldc.i4.0
0xaf993  ldc.i4.1
0xaf994  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xaf999  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xaf99e  ldloc.3
0xaf99f  ldc.i4.1
0xaf9a0  ldc.i4.1
0xaf9a1  stelem.i1
0xaf9a2  br       loc_B042C
0xaf9a7  ldloc.3
0xaf9a8  ldc.i4.2
0xaf9a9  ldelem.i1
0xaf9aa  brtrue.s loc_AF9E9
0xaf9ac  ldarg.0
0xaf9ad  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf9b2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xaf9b7  ldarg.0
0xaf9b8  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xaf9bd  bne.un.s loc_AF9E9
0xaf9bf  ldarg.0
0xaf9c0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf9c5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xaf9ca  ldarg.0
0xaf9cb  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xaf9d0  bne.un.s loc_AF9E9
0xaf9d2  ldloc.2
0xaf9d3  ldarg.0
0xaf9d4  ldc.i4.0
0xaf9d5  ldc.i4.1
0xaf9d6  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xaf9db  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xaf9e0  ldloc.3
0xaf9e1  ldc.i4.2
0xaf9e2  ldc.i4.1
0xaf9e3  stelem.i1
0xaf9e4  br       loc_B042C
0xaf9e9  ldloc.3
0xaf9ea  ldc.i4.3
0xaf9eb  ldelem.i1
0xaf9ec  brtrue.s loc_AFA2B
0xaf9ee  ldarg.0
0xaf9ef  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xaf9f4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xaf9f9  ldarg.0
0xaf9fa  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xaf9ff  bne.un.s loc_AFA2B
0xafa01  ldarg.0
0xafa02  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafa07  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xafa0c  ldarg.0
0xafa0d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xafa12  bne.un.s loc_AFA2B
0xafa14  ldloc.2
0xafa15  ldarg.0
0xafa16  ldc.i4.0
0xafa17  ldc.i4.1
0xafa18  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xafa1d  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xafa22  ldloc.3
0xafa23  ldc.i4.3
0xafa24  ldc.i4.1
0xafa25  stelem.i1
0xafa26  br       loc_B042C
0xafa2b  ldloc.3
0xafa2c  ldc.i4.4
0xafa2d  ldelem.i1
0xafa2e  brtrue.s loc_AFA70
0xafa30  ldarg.0
0xafa31  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafa36  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xafa3b  ldarg.0
0xafa3c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1971_category
0xafa41  bne.un.s loc_AFA70
0xafa43  ldarg.0
0xafa44  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafa49  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xafa4e  ldarg.0
0xafa4f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xafa54  bne.un.s loc_AFA70
0xafa56  ldloc.2
0xafa57  ldarg.0
0xafa58  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafa5d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xafa62  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_category(string)
0xafa67  ldloc.3
0xafa68  ldc.i4.4
0xafa69  ldc.i4.1
0xafa6a  stelem.i1
0xafa6b  br       loc_B042C
0xafa70  ldloc.3
0xafa71  ldc.i4.5
0xafa72  ldelem.i1
0xafa73  brtrue.s loc_AFAB2
0xafa75  ldarg.0
0xafa76  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafa7b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xafa80  ldarg.0
0xafa81  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1808_createdby
0xafa86  bne.un.s loc_AFAB2
0xafa88  ldarg.0
0xafa89  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafa8e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xafa93  ldarg.0
0xafa94  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xafa99  bne.un.s loc_AFAB2
0xafa9b  ldloc.2
0xafa9c  ldarg.0
0xafa9d  ldc.i4.0
0xafa9e  ldc.i4.1
0xafa9f  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read126_Lookup(bool isNullable, bool checkType)
0xafaa4  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_createdby(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup)
0xafaa9  ldloc.3
0xafaaa  ldc.i4.5
0xafaab  ldc.i4.1
0xafaac  stelem.i1
0xafaad  br       loc_B042C
0xafab2  ldloc.3
0xafab3  ldc.i4.6
0xafab4  ldelem.i1
0xafab5  brtrue.s loc_AFAF4
0xafab7  ldarg.0
0xafab8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafabd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xafac2  ldarg.0
0xafac3  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1809_createdon
0xafac8  bne.un.s loc_AFAF4
0xafaca  ldarg.0
0xafacb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafad0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xafad5  ldarg.0
0xafad6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xafadb  bne.un.s loc_AFAF4
0xafadd  ldloc.2
0xafade  ldarg.0
0xafadf  ldc.i4.0
0xafae0  ldc.i4.1
0xafae1  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xafae6  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_createdon(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xafaeb  ldloc.3
0xafaec  ldc.i4.6
0xafaed  ldc.i4.1
0xafaee  stelem.i1
0xafaef  br       loc_B042C
0xafaf4  ldloc.3
0xafaf5  ldc.i4.7
0xafaf6  ldelem.i1
0xafaf7  brtrue.s loc_AFB39
0xafaf9  ldarg.0
0xafafa  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafaff  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xafb04  ldarg.0
0xafb05  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1810_description
0xafb0a  bne.un.s loc_AFB39
0xafb0c  ldarg.0
0xafb0d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafb12  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xafb17  ldarg.0
0xafb18  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xafb1d  bne.un.s loc_AFB39
0xafb1f  ldloc.2
0xafb20  ldarg.0
0xafb21  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xafb26  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xafb2b  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.phonecall::set_description(string)
0xafb30  ldloc.3
0xafb31  ldc.i4.7
0xafb32  ldc.i4.1
  ... truncated ...
```
