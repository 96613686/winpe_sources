# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read440_appointment

- ea: `0xd3710`
- end: `0xd4522`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read440_appointment`
- size: `3602`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xf1740`
- `0x1241e0`
- `0x155310`

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
- `0xd3710`
- `0xd4530`

## string_xrefs

- `0xd3d13`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xd3d21`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xd3e71`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xd3e7f`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xd4167`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xd4175`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xd44cd`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:createdby, http://schemas.microsoft.com/crm/2007/WebServices:createdon, http://schemas.microsoft.com/crm/2007/WebServices:descripti`
- `0xd44db`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:createdby, http://schemas.microsoft.com/crm/2007/WebServices:createdon, http://schemas.microsoft.com/crm/2007/WebServices:descripti`

## pseudocode

```c

```

## disassembly

```asm
0xd3710  ldarg.2
0xd3711  brtrue.s loc_D3716
0xd3713  ldnull
0xd3714  br.s     loc_D371C
0xd3716  ldarg.0
0xd3717  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xd371c  stloc.0
0xd371d  ldc.i4.0
0xd371e  stloc.1
0xd371f  ldarg.1
0xd3720  brfalse.s loc_D3729
0xd3722  ldarg.0
0xd3723  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xd3728  stloc.1
0xd3729  ldarg.2
0xd372a  brfalse.s loc_D3759
0xd372c  ldloc.0
0xd372d  ldnull
0xd372e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xd3733  brtrue.s loc_D3759
0xd3735  ldloc.0
0xd3736  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xd373b  ldarg.0
0xd373c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1700_appointment
0xd3741  bne.un.s loc_D3751
0xd3743  ldloc.0
0xd3744  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xd3749  ldarg.0
0xd374a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd374f  beq.s    loc_D3759
0xd3751  ldarg.0
0xd3752  ldloc.0
0xd3753  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xd3758  throw
0xd3759  ldloc.1
0xd375a  brfalse.s loc_D375E
0xd375c  ldnull
0xd375d  ret
0xd375e  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::.ctor()
0xd3763  stloc.2
0xd3764  ldc.i4.s 0x24
0xd3766  newarr   [mscorlib]System.Boolean
0xd376b  stloc.3
0xd376c  br.s     loc_D3788
0xd376e  ldarg.0
0xd376f  ldarg.0
0xd3770  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3775  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xd377a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xd377f  brtrue.s loc_D3788
0xd3781  ldarg.0
0xd3782  ldloc.2
0xd3783  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xd3788  ldarg.0
0xd3789  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd378e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xd3793  brtrue.s loc_D376E
0xd3795  ldarg.0
0xd3796  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd379b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xd37a0  pop
0xd37a1  ldarg.0
0xd37a2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd37a7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xd37ac  brfalse.s loc_D37BB
0xd37ae  ldarg.0
0xd37af  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd37b4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xd37b9  ldloc.2
0xd37ba  ret
0xd37bb  ldarg.0
0xd37bc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd37c1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xd37c6  ldarg.0
0xd37c7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd37cc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xd37d1  pop
0xd37d2  ldc.i4.0
0xd37d3  stloc.s  4
0xd37d5  ldarg.0
0xd37d6  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xd37db  stloc.s  5
0xd37dd  br       loc_D44FB
0xd37e2  ldarg.0
0xd37e3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd37e8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xd37ed  ldc.i4.1
0xd37ee  bne.un   loc_D44D9
0xd37f3  ldloc.3
0xd37f4  ldc.i4.0
0xd37f5  ldelem.i1
0xd37f6  brtrue.s loc_D3835
0xd37f8  ldarg.0
0xd37f9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd37fe  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd3803  ldarg.0
0xd3804  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xd3809  bne.un.s loc_D3835
0xd380b  ldarg.0
0xd380c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3811  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd3816  ldarg.0
0xd3817  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd381c  bne.un.s loc_D3835
0xd381e  ldloc.2
0xd381f  ldarg.0
0xd3820  ldc.i4.0
0xd3821  ldc.i4.1
0xd3822  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xd3827  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xd382c  ldloc.3
0xd382d  ldc.i4.0
0xd382e  ldc.i4.1
0xd382f  stelem.i1
0xd3830  br       loc_D44E5
0xd3835  ldloc.3
0xd3836  ldc.i4.1
0xd3837  ldelem.i1
0xd3838  brtrue.s loc_D3877
0xd383a  ldarg.0
0xd383b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3840  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd3845  ldarg.0
0xd3846  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xd384b  bne.un.s loc_D3877
0xd384d  ldarg.0
0xd384e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3853  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd3858  ldarg.0
0xd3859  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd385e  bne.un.s loc_D3877
0xd3860  ldloc.2
0xd3861  ldarg.0
0xd3862  ldc.i4.0
0xd3863  ldc.i4.1
0xd3864  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xd3869  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xd386e  ldloc.3
0xd386f  ldc.i4.1
0xd3870  ldc.i4.1
0xd3871  stelem.i1
0xd3872  br       loc_D44E5
0xd3877  ldloc.3
0xd3878  ldc.i4.2
0xd3879  ldelem.i1
0xd387a  brtrue.s loc_D38B9
0xd387c  ldarg.0
0xd387d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3882  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd3887  ldarg.0
0xd3888  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xd388d  bne.un.s loc_D38B9
0xd388f  ldarg.0
0xd3890  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3895  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd389a  ldarg.0
0xd389b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd38a0  bne.un.s loc_D38B9
0xd38a2  ldloc.2
0xd38a3  ldarg.0
0xd38a4  ldc.i4.0
0xd38a5  ldc.i4.1
0xd38a6  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xd38ab  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xd38b0  ldloc.3
0xd38b1  ldc.i4.2
0xd38b2  ldc.i4.1
0xd38b3  stelem.i1
0xd38b4  br       loc_D44E5
0xd38b9  ldloc.3
0xd38ba  ldc.i4.3
0xd38bb  ldelem.i1
0xd38bc  brtrue.s loc_D38FB
0xd38be  ldarg.0
0xd38bf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd38c4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd38c9  ldarg.0
0xd38ca  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xd38cf  bne.un.s loc_D38FB
0xd38d1  ldarg.0
0xd38d2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd38d7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd38dc  ldarg.0
0xd38dd  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd38e2  bne.un.s loc_D38FB
0xd38e4  ldloc.2
0xd38e5  ldarg.0
0xd38e6  ldc.i4.0
0xd38e7  ldc.i4.1
0xd38e8  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xd38ed  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xd38f2  ldloc.3
0xd38f3  ldc.i4.3
0xd38f4  ldc.i4.1
0xd38f5  stelem.i1
0xd38f6  br       loc_D44E5
0xd38fb  ldloc.3
0xd38fc  ldc.i4.4
0xd38fd  ldelem.i1
0xd38fe  brtrue.s loc_D3940
0xd3900  ldarg.0
0xd3901  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3906  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd390b  ldarg.0
0xd390c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1971_category
0xd3911  bne.un.s loc_D3940
0xd3913  ldarg.0
0xd3914  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd3919  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd391e  ldarg.0
0xd391f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd3924  bne.un.s loc_D3940
0xd3926  ldloc.2
0xd3927  ldarg.0
0xd3928  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd392d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xd3932  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_category(string)
0xd3937  ldloc.3
0xd3938  ldc.i4.4
0xd3939  ldc.i4.1
0xd393a  stelem.i1
0xd393b  br       loc_D44E5
0xd3940  ldloc.3
0xd3941  ldc.i4.5
0xd3942  ldelem.i1
0xd3943  brtrue.s loc_D3982
0xd3945  ldarg.0
0xd3946  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd394b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd3950  ldarg.0
0xd3951  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1808_createdby
0xd3956  bne.un.s loc_D3982
0xd3958  ldarg.0
0xd3959  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd395e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd3963  ldarg.0
0xd3964  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd3969  bne.un.s loc_D3982
0xd396b  ldloc.2
0xd396c  ldarg.0
0xd396d  ldc.i4.0
0xd396e  ldc.i4.1
0xd396f  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read126_Lookup(bool isNullable, bool checkType)
0xd3974  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_createdby(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup)
0xd3979  ldloc.3
0xd397a  ldc.i4.5
0xd397b  ldc.i4.1
0xd397c  stelem.i1
0xd397d  br       loc_D44E5
0xd3982  ldloc.3
0xd3983  ldc.i4.6
0xd3984  ldelem.i1
0xd3985  brtrue.s loc_D39C4
0xd3987  ldarg.0
0xd3988  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd398d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd3992  ldarg.0
0xd3993  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1809_createdon
0xd3998  bne.un.s loc_D39C4
0xd399a  ldarg.0
0xd399b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd39a0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd39a5  ldarg.0
0xd39a6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd39ab  bne.un.s loc_D39C4
0xd39ad  ldloc.2
0xd39ae  ldarg.0
0xd39af  ldc.i4.0
0xd39b0  ldc.i4.1
0xd39b1  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xd39b6  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_createdon(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xd39bb  ldloc.3
0xd39bc  ldc.i4.6
0xd39bd  ldc.i4.1
0xd39be  stelem.i1
0xd39bf  br       loc_D44E5
0xd39c4  ldloc.3
0xd39c5  ldc.i4.7
0xd39c6  ldelem.i1
0xd39c7  brtrue.s loc_D3A09
0xd39c9  ldarg.0
0xd39ca  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd39cf  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd39d4  ldarg.0
0xd39d5  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1810_description
0xd39da  bne.un.s loc_D3A09
0xd39dc  ldarg.0
0xd39dd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd39e2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xd39e7  ldarg.0
0xd39e8  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xd39ed  bne.un.s loc_D3A09
0xd39ef  ldloc.2
0xd39f0  ldarg.0
0xd39f1  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xd39f6  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xd39fb  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.appointment::set_description(string)
0xd3a00  ldloc.3
0xd3a01  ldc.i4.7
0xd3a02  ldc.i4.1
  ... truncated ...
```
