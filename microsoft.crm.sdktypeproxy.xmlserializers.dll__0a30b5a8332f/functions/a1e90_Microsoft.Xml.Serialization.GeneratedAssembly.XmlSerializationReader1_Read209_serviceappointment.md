# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read209_serviceappointment

- ea: `0xa1e90`
- end: `0xa2aff`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read209_serviceappointment`
- size: `3183`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xe9f40`
- `0x124360`
- `0x14d510`

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
- `0xa1e90`
- `0xa2b00`

## string_xrefs

- `0xa222a`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xa2238`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xa2700`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xa270e`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xa2aaa`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:createdby, http://schemas.microsoft.com/crm/2007/WebServices:createdon, http://schemas.microsoft.com/crm/2007/WebServices:customers`
- `0xa2ab8`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:createdby, http://schemas.microsoft.com/crm/2007/WebServices:createdon, http://schemas.microsoft.com/crm/2007/WebServices:customers`

## pseudocode

```c

```

## disassembly

```asm
0xa1e90  ldarg.2
0xa1e91  brtrue.s loc_A1E96
0xa1e93  ldnull
0xa1e94  br.s     loc_A1E9C
0xa1e96  ldarg.0
0xa1e97  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xa1e9c  stloc.0
0xa1e9d  ldc.i4.0
0xa1e9e  stloc.1
0xa1e9f  ldarg.1
0xa1ea0  brfalse.s loc_A1EA9
0xa1ea2  ldarg.0
0xa1ea3  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xa1ea8  stloc.1
0xa1ea9  ldarg.2
0xa1eaa  brfalse.s loc_A1ED9
0xa1eac  ldloc.0
0xa1ead  ldnull
0xa1eae  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xa1eb3  brtrue.s loc_A1ED9
0xa1eb5  ldloc.0
0xa1eb6  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xa1ebb  ldarg.0
0xa1ebc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1775_serviceappointment
0xa1ec1  bne.un.s loc_A1ED1
0xa1ec3  ldloc.0
0xa1ec4  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xa1ec9  ldarg.0
0xa1eca  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa1ecf  beq.s    loc_A1ED9
0xa1ed1  ldarg.0
0xa1ed2  ldloc.0
0xa1ed3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xa1ed8  throw
0xa1ed9  ldloc.1
0xa1eda  brfalse.s loc_A1EDE
0xa1edc  ldnull
0xa1edd  ret
0xa1ede  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::.ctor()
0xa1ee3  stloc.2
0xa1ee4  ldc.i4.s 0x22
0xa1ee6  newarr   [mscorlib]System.Boolean
0xa1eeb  stloc.3
0xa1eec  br.s     loc_A1F08
0xa1eee  ldarg.0
0xa1eef  ldarg.0
0xa1ef0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1ef5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xa1efa  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xa1eff  brtrue.s loc_A1F08
0xa1f01  ldarg.0
0xa1f02  ldloc.2
0xa1f03  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xa1f08  ldarg.0
0xa1f09  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f0e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xa1f13  brtrue.s loc_A1EEE
0xa1f15  ldarg.0
0xa1f16  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f1b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xa1f20  pop
0xa1f21  ldarg.0
0xa1f22  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f27  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa1f2c  brfalse.s loc_A1F3B
0xa1f2e  ldarg.0
0xa1f2f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f34  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xa1f39  ldloc.2
0xa1f3a  ret
0xa1f3b  ldarg.0
0xa1f3c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f41  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xa1f46  ldarg.0
0xa1f47  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f4c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xa1f51  pop
0xa1f52  ldc.i4.0
0xa1f53  stloc.s  4
0xa1f55  ldarg.0
0xa1f56  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xa1f5b  stloc.s  5
0xa1f5d  br       loc_A2AD8
0xa1f62  ldarg.0
0xa1f63  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f68  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xa1f6d  ldc.i4.1
0xa1f6e  bne.un   loc_A2AB6
0xa1f73  ldloc.3
0xa1f74  ldc.i4.0
0xa1f75  ldelem.i1
0xa1f76  brtrue.s loc_A1FB5
0xa1f78  ldarg.0
0xa1f79  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f7e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1f83  ldarg.0
0xa1f84  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xa1f89  bne.un.s loc_A1FB5
0xa1f8b  ldarg.0
0xa1f8c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1f91  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa1f96  ldarg.0
0xa1f97  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa1f9c  bne.un.s loc_A1FB5
0xa1f9e  ldloc.2
0xa1f9f  ldarg.0
0xa1fa0  ldc.i4.0
0xa1fa1  ldc.i4.1
0xa1fa2  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xa1fa7  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xa1fac  ldloc.3
0xa1fad  ldc.i4.0
0xa1fae  ldc.i4.1
0xa1faf  stelem.i1
0xa1fb0  br       loc_A2AC2
0xa1fb5  ldloc.3
0xa1fb6  ldc.i4.1
0xa1fb7  ldelem.i1
0xa1fb8  brtrue.s loc_A1FF7
0xa1fba  ldarg.0
0xa1fbb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1fc0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa1fc5  ldarg.0
0xa1fc6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xa1fcb  bne.un.s loc_A1FF7
0xa1fcd  ldarg.0
0xa1fce  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa1fd3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa1fd8  ldarg.0
0xa1fd9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa1fde  bne.un.s loc_A1FF7
0xa1fe0  ldloc.2
0xa1fe1  ldarg.0
0xa1fe2  ldc.i4.0
0xa1fe3  ldc.i4.1
0xa1fe4  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xa1fe9  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xa1fee  ldloc.3
0xa1fef  ldc.i4.1
0xa1ff0  ldc.i4.1
0xa1ff1  stelem.i1
0xa1ff2  br       loc_A2AC2
0xa1ff7  ldloc.3
0xa1ff8  ldc.i4.2
0xa1ff9  ldelem.i1
0xa1ffa  brtrue.s loc_A2039
0xa1ffc  ldarg.0
0xa1ffd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2002  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa2007  ldarg.0
0xa2008  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xa200d  bne.un.s loc_A2039
0xa200f  ldarg.0
0xa2010  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2015  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa201a  ldarg.0
0xa201b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa2020  bne.un.s loc_A2039
0xa2022  ldloc.2
0xa2023  ldarg.0
0xa2024  ldc.i4.0
0xa2025  ldc.i4.1
0xa2026  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xa202b  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xa2030  ldloc.3
0xa2031  ldc.i4.2
0xa2032  ldc.i4.1
0xa2033  stelem.i1
0xa2034  br       loc_A2AC2
0xa2039  ldloc.3
0xa203a  ldc.i4.3
0xa203b  ldelem.i1
0xa203c  brtrue.s loc_A207B
0xa203e  ldarg.0
0xa203f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2044  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa2049  ldarg.0
0xa204a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xa204f  bne.un.s loc_A207B
0xa2051  ldarg.0
0xa2052  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2057  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa205c  ldarg.0
0xa205d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa2062  bne.un.s loc_A207B
0xa2064  ldloc.2
0xa2065  ldarg.0
0xa2066  ldc.i4.0
0xa2067  ldc.i4.1
0xa2068  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xa206d  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xa2072  ldloc.3
0xa2073  ldc.i4.3
0xa2074  ldc.i4.1
0xa2075  stelem.i1
0xa2076  br       loc_A2AC2
0xa207b  ldloc.3
0xa207c  ldc.i4.4
0xa207d  ldelem.i1
0xa207e  brtrue.s loc_A20C0
0xa2080  ldarg.0
0xa2081  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2086  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa208b  ldarg.0
0xa208c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1971_category
0xa2091  bne.un.s loc_A20C0
0xa2093  ldarg.0
0xa2094  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2099  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa209e  ldarg.0
0xa209f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa20a4  bne.un.s loc_A20C0
0xa20a6  ldloc.2
0xa20a7  ldarg.0
0xa20a8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa20ad  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xa20b2  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::set_category(string)
0xa20b7  ldloc.3
0xa20b8  ldc.i4.4
0xa20b9  ldc.i4.1
0xa20ba  stelem.i1
0xa20bb  br       loc_A2AC2
0xa20c0  ldloc.3
0xa20c1  ldc.i4.5
0xa20c2  ldelem.i1
0xa20c3  brtrue.s loc_A2102
0xa20c5  ldarg.0
0xa20c6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa20cb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa20d0  ldarg.0
0xa20d1  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1808_createdby
0xa20d6  bne.un.s loc_A2102
0xa20d8  ldarg.0
0xa20d9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa20de  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa20e3  ldarg.0
0xa20e4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa20e9  bne.un.s loc_A2102
0xa20eb  ldloc.2
0xa20ec  ldarg.0
0xa20ed  ldc.i4.0
0xa20ee  ldc.i4.1
0xa20ef  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read126_Lookup(bool isNullable, bool checkType)
0xa20f4  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::set_createdby(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup)
0xa20f9  ldloc.3
0xa20fa  ldc.i4.5
0xa20fb  ldc.i4.1
0xa20fc  stelem.i1
0xa20fd  br       loc_A2AC2
0xa2102  ldloc.3
0xa2103  ldc.i4.6
0xa2104  ldelem.i1
0xa2105  brtrue.s loc_A2144
0xa2107  ldarg.0
0xa2108  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa210d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa2112  ldarg.0
0xa2113  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1809_createdon
0xa2118  bne.un.s loc_A2144
0xa211a  ldarg.0
0xa211b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2120  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa2125  ldarg.0
0xa2126  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa212b  bne.un.s loc_A2144
0xa212d  ldloc.2
0xa212e  ldarg.0
0xa212f  ldc.i4.0
0xa2130  ldc.i4.1
0xa2131  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xa2136  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.serviceappointment::set_createdon(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xa213b  ldloc.3
0xa213c  ldc.i4.6
0xa213d  ldc.i4.1
0xa213e  stelem.i1
0xa213f  br       loc_A2AC2
0xa2144  ldarg.0
0xa2145  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa214a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xa214f  ldarg.0
0xa2150  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2062_customers
0xa2155  bne.un   loc_A22A2
0xa215a  ldarg.0
0xa215b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2160  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xa2165  ldarg.0
0xa2166  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xa216b  bne.un   loc_A22A2
0xa2170  ldarg.0
0xa2171  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xa2176  brtrue   loc_A2AC2
0xa217b  ldnull
0xa217c  stloc.s  6
0xa217e  ldc.i4.0
0xa217f  stloc.s  7
0xa2181  ldarg.0
0xa2182  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xa2187  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xa218c  brfalse.s loc_A219E
0xa218e  ldarg.0
  ... truncated ...
```
