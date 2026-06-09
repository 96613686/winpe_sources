# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read367_fax

- ea: `0xc1d90`
- end: `0xc2ad2`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read367_fax`
- size: `3394`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x9b920`
- `0xef1c0`
- `0x152a90`

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
- `0xc1d90`
- `0xc2ae0`

## string_xrefs

- `0xc2286`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc2294`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc297e`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc298c`: `http://schemas.microsoft.com/crm/2007/WebServices:activityparty`
- `0xc2a7d`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:billingcode, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:coverpagename, http://schemas.microsoft.com/crm/2007/WebServices:cre`
- `0xc2a8b`: `http://schemas.microsoft.com/crm/2007/WebServices:activityid, http://schemas.microsoft.com/crm/2007/WebServices:actualdurationminutes, http://schemas.microsoft.com/crm/2007/WebServices:actualend, http://schemas.microsoft.com/crm/2007/WebServices:actualstart, http://schemas.microsoft.com/crm/2007/WebServices:billingcode, http://schemas.microsoft.com/crm/2007/WebServices:category, http://schemas.microsoft.com/crm/2007/WebServices:coverpagename, http://schemas.microsoft.com/crm/2007/WebServices:cre`

## pseudocode

```c

```

## disassembly

```asm
0xc1d90  ldarg.2
0xc1d91  brtrue.s loc_C1D96
0xc1d93  ldnull
0xc1d94  br.s     loc_C1D9C
0xc1d96  ldarg.0
0xc1d97  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0xc1d9c  stloc.0
0xc1d9d  ldc.i4.0
0xc1d9e  stloc.1
0xc1d9f  ldarg.1
0xc1da0  brfalse.s loc_C1DA9
0xc1da2  ldarg.0
0xc1da3  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0xc1da8  stloc.1
0xc1da9  ldarg.2
0xc1daa  brfalse.s loc_C1DD9
0xc1dac  ldloc.0
0xc1dad  ldnull
0xc1dae  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xc1db3  brtrue.s loc_C1DD9
0xc1db5  ldloc.0
0xc1db6  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xc1dbb  ldarg.0
0xc1dbc  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1723_fax
0xc1dc1  bne.un.s loc_C1DD1
0xc1dc3  ldloc.0
0xc1dc4  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xc1dc9  ldarg.0
0xc1dca  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc1dcf  beq.s    loc_C1DD9
0xc1dd1  ldarg.0
0xc1dd2  ldloc.0
0xc1dd3  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0xc1dd8  throw
0xc1dd9  ldloc.1
0xc1dda  brfalse.s loc_C1DDE
0xc1ddc  ldnull
0xc1ddd  ret
0xc1dde  newobj   instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::.ctor()
0xc1de3  stloc.2
0xc1de4  ldc.i4.s 0x25
0xc1de6  newarr   [mscorlib]System.Boolean
0xc1deb  stloc.3
0xc1dec  br.s     loc_C1E08
0xc1dee  ldarg.0
0xc1def  ldarg.0
0xc1df0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1df5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xc1dfa  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0xc1dff  brtrue.s loc_C1E08
0xc1e01  ldarg.0
0xc1e02  ldloc.2
0xc1e03  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0xc1e08  ldarg.0
0xc1e09  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e0e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0xc1e13  brtrue.s loc_C1DEE
0xc1e15  ldarg.0
0xc1e16  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e1b  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0xc1e20  pop
0xc1e21  ldarg.0
0xc1e22  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e27  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xc1e2c  brfalse.s loc_C1E3B
0xc1e2e  ldarg.0
0xc1e2f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e34  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0xc1e39  ldloc.2
0xc1e3a  ret
0xc1e3b  ldarg.0
0xc1e3c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e41  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0xc1e46  ldarg.0
0xc1e47  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e4c  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0xc1e51  pop
0xc1e52  ldc.i4.0
0xc1e53  stloc.s  4
0xc1e55  ldarg.0
0xc1e56  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0xc1e5b  stloc.s  5
0xc1e5d  br       loc_C2AAB
0xc1e62  ldarg.0
0xc1e63  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e68  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xc1e6d  ldc.i4.1
0xc1e6e  bne.un   loc_C2A89
0xc1e73  ldloc.3
0xc1e74  ldc.i4.0
0xc1e75  ldelem.i1
0xc1e76  brtrue.s loc_C1EB5
0xc1e78  ldarg.0
0xc1e79  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e7e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc1e83  ldarg.0
0xc1e84  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1908_activityid
0xc1e89  bne.un.s loc_C1EB5
0xc1e8b  ldarg.0
0xc1e8c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1e91  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc1e96  ldarg.0
0xc1e97  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc1e9c  bne.un.s loc_C1EB5
0xc1e9e  ldloc.2
0xc1e9f  ldarg.0
0xc1ea0  ldc.i4.0
0xc1ea1  ldc.i4.1
0xc1ea2  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read149_Key(bool isNullable, bool checkType)
0xc1ea7  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_activityid(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key)
0xc1eac  ldloc.3
0xc1ead  ldc.i4.0
0xc1eae  ldc.i4.1
0xc1eaf  stelem.i1
0xc1eb0  br       loc_C2A95
0xc1eb5  ldloc.3
0xc1eb6  ldc.i4.1
0xc1eb7  ldelem.i1
0xc1eb8  brtrue.s loc_C1EF7
0xc1eba  ldarg.0
0xc1ebb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1ec0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc1ec5  ldarg.0
0xc1ec6  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1968_actualdurationminutes
0xc1ecb  bne.un.s loc_C1EF7
0xc1ecd  ldarg.0
0xc1ece  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1ed3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc1ed8  ldarg.0
0xc1ed9  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc1ede  bne.un.s loc_C1EF7
0xc1ee0  ldloc.2
0xc1ee1  ldarg.0
0xc1ee2  ldc.i4.0
0xc1ee3  ldc.i4.1
0xc1ee4  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read153_CrmNumber(bool isNullable, bool checkType)
0xc1ee9  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_actualdurationminutes(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber)
0xc1eee  ldloc.3
0xc1eef  ldc.i4.1
0xc1ef0  ldc.i4.1
0xc1ef1  stelem.i1
0xc1ef2  br       loc_C2A95
0xc1ef7  ldloc.3
0xc1ef8  ldc.i4.2
0xc1ef9  ldelem.i1
0xc1efa  brtrue.s loc_C1F39
0xc1efc  ldarg.0
0xc1efd  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1f02  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc1f07  ldarg.0
0xc1f08  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1969_actualend
0xc1f0d  bne.un.s loc_C1F39
0xc1f0f  ldarg.0
0xc1f10  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1f15  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc1f1a  ldarg.0
0xc1f1b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc1f20  bne.un.s loc_C1F39
0xc1f22  ldloc.2
0xc1f23  ldarg.0
0xc1f24  ldc.i4.0
0xc1f25  ldc.i4.1
0xc1f26  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xc1f2b  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_actualend(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xc1f30  ldloc.3
0xc1f31  ldc.i4.2
0xc1f32  ldc.i4.1
0xc1f33  stelem.i1
0xc1f34  br       loc_C2A95
0xc1f39  ldloc.3
0xc1f3a  ldc.i4.3
0xc1f3b  ldelem.i1
0xc1f3c  brtrue.s loc_C1F7B
0xc1f3e  ldarg.0
0xc1f3f  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1f44  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc1f49  ldarg.0
0xc1f4a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1970_actualstart
0xc1f4f  bne.un.s loc_C1F7B
0xc1f51  ldarg.0
0xc1f52  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1f57  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc1f5c  ldarg.0
0xc1f5d  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc1f62  bne.un.s loc_C1F7B
0xc1f64  ldloc.2
0xc1f65  ldarg.0
0xc1f66  ldc.i4.0
0xc1f67  ldc.i4.1
0xc1f68  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read128_CrmDateTime(bool isNullable, bool checkType)
0xc1f6d  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_actualstart(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime)
0xc1f72  ldloc.3
0xc1f73  ldc.i4.3
0xc1f74  ldc.i4.1
0xc1f75  stelem.i1
0xc1f76  br       loc_C2A95
0xc1f7b  ldloc.3
0xc1f7c  ldc.i4.4
0xc1f7d  ldelem.i1
0xc1f7e  brtrue.s loc_C1FC0
0xc1f80  ldarg.0
0xc1f81  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1f86  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc1f8b  ldarg.0
0xc1f8c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2602_billingcode
0xc1f91  bne.un.s loc_C1FC0
0xc1f93  ldarg.0
0xc1f94  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1f99  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc1f9e  ldarg.0
0xc1f9f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc1fa4  bne.un.s loc_C1FC0
0xc1fa6  ldloc.2
0xc1fa7  ldarg.0
0xc1fa8  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1fad  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xc1fb2  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_billingcode(string)
0xc1fb7  ldloc.3
0xc1fb8  ldc.i4.4
0xc1fb9  ldc.i4.1
0xc1fba  stelem.i1
0xc1fbb  br       loc_C2A95
0xc1fc0  ldloc.3
0xc1fc1  ldc.i4.5
0xc1fc2  ldelem.i1
0xc1fc3  brtrue.s loc_C2005
0xc1fc5  ldarg.0
0xc1fc6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1fcb  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc1fd0  ldarg.0
0xc1fd1  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1971_category
0xc1fd6  bne.un.s loc_C2005
0xc1fd8  ldarg.0
0xc1fd9  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1fde  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc1fe3  ldarg.0
0xc1fe4  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc1fe9  bne.un.s loc_C2005
0xc1feb  ldloc.2
0xc1fec  ldarg.0
0xc1fed  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc1ff2  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xc1ff7  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_category(string)
0xc1ffc  ldloc.3
0xc1ffd  ldc.i4.5
0xc1ffe  ldc.i4.1
0xc1fff  stelem.i1
0xc2000  br       loc_C2A95
0xc2005  ldloc.3
0xc2006  ldc.i4.6
0xc2007  ldelem.i1
0xc2008  brtrue.s loc_C204A
0xc200a  ldarg.0
0xc200b  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc2010  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc2015  ldarg.0
0xc2016  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2603_coverpagename
0xc201b  bne.un.s loc_C204A
0xc201d  ldarg.0
0xc201e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc2023  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc2028  ldarg.0
0xc2029  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc202e  bne.un.s loc_C204A
0xc2030  ldloc.2
0xc2031  ldarg.0
0xc2032  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc2037  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0xc203c  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_coverpagename(string)
0xc2041  ldloc.3
0xc2042  ldc.i4.6
0xc2043  ldc.i4.1
0xc2044  stelem.i1
0xc2045  br       loc_C2A95
0xc204a  ldloc.3
0xc204b  ldc.i4.7
0xc204c  ldelem.i1
0xc204d  brtrue.s loc_C208C
0xc204f  ldarg.0
0xc2050  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc2055  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xc205a  ldarg.0
0xc205b  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1808_createdby
0xc2060  bne.un.s loc_C208C
0xc2062  ldarg.0
0xc2063  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0xc2068  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xc206d  ldarg.0
0xc206e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id2_Item
0xc2073  bne.un.s loc_C208C
0xc2075  ldloc.2
0xc2076  ldarg.0
0xc2077  ldc.i4.0
0xc2078  ldc.i4.1
0xc2079  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read126_Lookup(bool isNullable, bool checkType)
0xc207e  callvirt instance void [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.fax::set_createdby(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup)
0xc2083  ldloc.3
0xc2084  ldc.i4.7
0xc2085  ldc.i4.1
0xc2086  stelem.i1
  ... truncated ...
```
