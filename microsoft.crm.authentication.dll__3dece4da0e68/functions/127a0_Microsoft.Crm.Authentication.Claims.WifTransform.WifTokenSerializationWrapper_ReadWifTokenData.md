# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadWifTokenData

- ea: `0x127a0`
- end: `0x12c63`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadWifTokenData`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x12580`

## callees

- `0x11cd0`
- `0x11ce0`
- `0x11d00`
- `0x11d70`
- `0x11da0`
- `0x11db0`
- `0x11dc0`
- `0x11dd0`
- `0x11f20`
- `0x11f50`
- `0x11f60`
- `0x11f70`
- `0x11f80`
- `0x11f90`
- `0x11fa0`
- `0x11fd0`
- `0x11fe0`
- `0x12000`
- `0x125d0`
- `0x125f0`
- `0x12610`
- `0x12630`
- `0x12650`
- `0x12660`
- `0x12670`
- `0x12690`
- `0x126b0`
- `0x126d0`
- `0x126f0`
- `0x12710`
- `0x12730`
- `0x12750`
- `0x12770`
- `0x12790`
- `0x127a0`
- `0x12c70`
- `0x13970`

## string_xrefs

- `0x127a7`: `tokenData`
- `0x12824`: `The SecurityToken was not well formed. Expecting element name '{0}', found '{1}'.`
- `0x129d2`: `The SecurityToken was not well formed. Expecting element name '{0}', found '{1}'.`
- `0x12a24`: `The SecurityToken was not well formed. Expecting element name '{0}', found '{1}'.`
- `0x12aa8`: `The SecurityToken was not well formed. Expecting element name '{0}', found '{1}'.`
- `0x12b00`: `The SecurityToken was not well formed. Expecting element name '{0}', found '{1}'.`
- `0x12b58`: `The SecurityToken was not well formed. Expecting element name '{0}', found '{1}'.`
- `0x12bb0`: `The SecurityToken was not well formed. Expecting element name '{0}', found '{1}'.`
- `0x128cd`: `The SecurityToken was not well formed. This version was unexpected '{0}', acceptable version is '{1}'.`
- `0x12936`: `The SecurityToken was not well formed. This version was unexpected '{0}', acceptable version is '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x127a0  ldarg.1
0x127a1  brfalse.s loc_127A7
0x127a3  ldarg.1
0x127a4  ldlen
0x127a5  brtrue.s loc_127B2
0x127a7  ldstr    aTokendata// "tokenData"
0x127ac  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x127b1  throw
0x127b2  call     class Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Instance()
0x127b7  stloc.0
0x127b8  ldarg.1
0x127b9  ldc.i4.0
0x127ba  ldarg.1
0x127bb  ldlen
0x127bc  conv.i4
0x127bd  ldloc.0
0x127be  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_Max()
0x127c3  ldnull
0x127c4  ldnull
0x127c5  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::CreateBinaryReader(unsigned int8[], int32, int32, class [System.Runtime.Serialization]System.Xml.IXmlDictionary, class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas, class [System.Runtime.Serialization]System.Xml.XmlBinaryReaderSession, class [System.Runtime.Serialization]System.Xml.OnXmlDictionaryReaderClose)
0x127ca  stloc.1
0x127cb  ldarg.0
0x127cc  ldc.i4.0
0x127cd  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_IsSecurityContextSecurityTokenWrapper(bool value)
0x127d2  ldarg.0
0x127d3  ldc.i4.1
0x127d4  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_IsPersistent(bool value)
0x127d9  ldarg.0
0x127da  ldc.i4.0
0x127db  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_IsSessionMode(bool value)
0x127e0  ldarg.0
0x127e1  ldsfld   string [mscorlib]System.String::Empty
0x127e6  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_Context(string value)
0x127eb  ldloc.1
0x127ec  ldloc.0
0x127ed  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_SecurityContextToken()
0x127f2  ldloc.0
0x127f3  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x127f8  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x127fd  brfalse.s loc_1280B
0x127ff  ldarg.0
0x12800  ldc.i4.1
0x12801  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_IsSecurityContextSecurityTokenWrapper(bool value)
0x12806  br       loc_128B4
0x1280b  ldloc.1
0x1280c  ldloc.0
0x1280d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_SessionToken()
0x12812  ldloc.0
0x12813  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12818  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x1281d  brtrue.s loc_12851
0x1281f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12824  ldstr    aTheSecuritytok_0// "The SecurityToken was not well formed. "...
0x12829  ldc.i4.2
0x1282a  newarr   [mscorlib]System.Object
0x1282f  dup
0x12830  ldc.i4.0
0x12831  ldloc.0
0x12832  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_SecurityContextToken()
0x12837  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x1283c  stelem.ref
0x1283d  dup
0x1283e  ldc.i4.1
0x1283f  ldloc.1
0x12840  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x12845  stelem.ref
0x12846  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1284b  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x12850  throw
0x12851  ldloc.1
0x12852  ldloc.0
0x12853  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_PersistentTrue()
0x12858  ldloc.0
0x12859  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1285e  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12863  brtrue.s loc_1286C
0x12865  ldarg.0
0x12866  ldc.i4.0
0x12867  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_IsPersistent(bool value)
0x1286c  ldloc.1
0x1286d  ldloc.0
0x1286e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_SessionModeTrue()
0x12873  ldloc.0
0x12874  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12879  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x1287e  brfalse.s loc_12887
0x12880  ldarg.0
0x12881  ldc.i4.1
0x12882  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_IsSessionMode(bool value)
0x12887  ldloc.1
0x12888  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadFullStartElement()
0x1288d  ldloc.1
0x1288e  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12893  pop
0x12894  ldloc.1
0x12895  ldloc.0
0x12896  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Context()
0x1289b  ldloc.0
0x1289c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x128a1  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x128a6  brfalse.s loc_128B4
0x128a8  ldarg.0
0x128a9  ldloc.1
0x128aa  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementContentAsString()
0x128af  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_Context(string value)
0x128b4  ldloc.1
0x128b5  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x128ba  stloc.2
0x128bb  ldloc.2
0x128bc  ldstr    a1// "1"
0x128c1  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x128c6  brfalse.s loc_128EF
0x128c8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x128cd  ldstr    aTheSecuritytok_1// "The SecurityToken was not well formed. "...
0x128d2  ldc.i4.2
0x128d3  newarr   [mscorlib]System.Object
0x128d8  dup
0x128d9  ldc.i4.0
0x128da  ldloc.2
0x128db  stelem.ref
0x128dc  dup
0x128dd  ldc.i4.1
0x128de  ldstr    a1// "1"
0x128e3  stelem.ref
0x128e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x128e9  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x128ee  throw
0x128ef  ldloc.1
0x128f0  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x128f5  stloc.3
0x128f6  ldloc.3
0x128f7  call     class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_WSSecureConversationFeb2005()
0x128fc  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_Namespace()
0x12901  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x12906  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1290b  brfalse.s loc_1291A
0x1290d  ldarg.0
0x1290e  call     class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_WSSecureConversationFeb2005()
0x12913  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_Version(class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion value)
0x12918  br.s     loc_12963
0x1291a  ldloc.3
0x1291b  call     class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_WSSecureConversation13()
0x12920  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_Namespace()
0x12925  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x1292a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1292f  brtrue.s loc_12958
0x12931  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12936  ldstr    aTheSecuritytok_1// "The SecurityToken was not well formed. "...
0x1293b  ldc.i4.2
0x1293c  newarr   [mscorlib]System.Object
0x12941  dup
0x12942  ldc.i4.0
0x12943  ldloc.3
0x12944  stelem.ref
0x12945  dup
0x12946  ldc.i4.1
0x12947  ldstr    a1// "1"
0x1294c  stelem.ref
0x1294d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12952  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x12957  throw
0x12958  ldarg.0
0x12959  call     class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_WSSecureConversation13()
0x1295e  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_Version(class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion value)
0x12963  ldloc.1
0x12964  ldloc.0
0x12965  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Id()
0x1296a  ldloc.0
0x1296b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12970  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12975  brfalse.s loc_12983
0x12977  ldarg.0
0x12978  ldloc.1
0x12979  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x1297e  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_Id(string value)
0x12983  ldarg.0
0x12984  call     instance string Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_Id()
0x12989  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1298e  brfalse.s loc_129B9
0x12990  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12995  ldstr    aTheSessionCook// "The session cookie must contain an non "...
0x1299a  ldc.i4.1
0x1299b  newarr   [mscorlib]System.Object
0x129a0  dup
0x129a1  ldc.i4.0
0x129a2  ldloc.0
0x129a3  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Id()
0x129a8  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x129ad  stelem.ref
0x129ae  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x129b3  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x129b8  throw
0x129b9  ldloc.1
0x129ba  ldloc.0
0x129bb  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ContextId()
0x129c0  ldloc.0
0x129c1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x129c6  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x129cb  brtrue.s loc_129FF
0x129cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x129d2  ldstr    aTheSecuritytok_0// "The SecurityToken was not well formed. "...
0x129d7  ldc.i4.2
0x129d8  newarr   [mscorlib]System.Object
0x129dd  dup
0x129de  ldc.i4.0
0x129df  ldloc.0
0x129e0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ContextId()
0x129e5  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x129ea  stelem.ref
0x129eb  dup
0x129ec  ldc.i4.1
0x129ed  ldloc.1
0x129ee  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x129f3  stelem.ref
0x129f4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x129f9  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x129fe  throw
0x129ff  ldarg.0
0x12a00  ldloc.1
0x12a01  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadElementContentAsUniqueId()
0x12a06  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_ContextId(class [System.Runtime.Serialization]System.Xml.UniqueId value)
0x12a0b  ldloc.1
0x12a0c  ldloc.0
0x12a0d  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Key()
0x12a12  ldloc.0
0x12a13  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12a18  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12a1d  brtrue.s loc_12A51
0x12a1f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12a24  ldstr    aTheSecuritytok_0// "The SecurityToken was not well formed. "...
0x12a29  ldc.i4.2
0x12a2a  newarr   [mscorlib]System.Object
0x12a2f  dup
0x12a30  ldc.i4.0
0x12a31  ldloc.0
0x12a32  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_Key()
0x12a37  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x12a3c  stelem.ref
0x12a3d  dup
0x12a3e  ldc.i4.1
0x12a3f  ldloc.1
0x12a40  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x12a45  stelem.ref
0x12a46  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12a4b  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x12a50  throw
0x12a51  ldloc.1
0x12a52  callvirt instance unsigned int8[] [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadElementContentAsBase64()
0x12a57  stloc.s  4
0x12a59  ldarg.0
0x12a5a  ldc.i4.1
0x12a5b  newarr   [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey
0x12a60  dup
0x12a61  ldc.i4.0
0x12a62  ldloc.s  4
0x12a64  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.InMemorySymmetricSecurityKey::.ctor(unsigned int8[])
0x12a69  stelem.ref
0x12a6a  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_SecurityKeys(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey> value)
0x12a6f  ldloc.1
0x12a70  ldloc.0
0x12a71  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_KeyGeneration()
0x12a76  ldloc.0
0x12a77  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12a7c  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12a81  brfalse.s loc_12A8F
0x12a83  ldarg.0
0x12a84  ldloc.1
0x12a85  callvirt instance class [System.Runtime.Serialization]System.Xml.UniqueId [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadElementContentAsUniqueId()
0x12a8a  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_KeyGeneration(object value)
0x12a8f  ldloc.1
0x12a90  ldloc.0
0x12a91  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EffectiveTime()
0x12a96  ldloc.0
0x12a97  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12a9c  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12aa1  brtrue.s loc_12AD5
0x12aa3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12aa8  ldstr    aTheSecuritytok_0// "The SecurityToken was not well formed. "...
0x12aad  ldc.i4.2
0x12aae  newarr   [mscorlib]System.Object
0x12ab3  dup
0x12ab4  ldc.i4.0
0x12ab5  ldloc.0
0x12ab6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EffectiveTime()
0x12abb  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x12ac0  stelem.ref
0x12ac1  dup
0x12ac2  ldc.i4.1
0x12ac3  ldloc.1
0x12ac4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x12ac9  stelem.ref
0x12aca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12acf  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x12ad4  throw
0x12ad5  ldarg.0
0x12ad6  ldloc.1
0x12ad7  call     int64 Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::ReadElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReader reader)
0x12adc  ldc.i4.1
0x12add  newobj   instance void [mscorlib]System.DateTime::.ctor(int64, valuetype [mscorlib]System.DateTimeKind)
0x12ae2  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::set_ValidFrom(valuetype [mscorlib]System.DateTime value)
  ... truncated ...
```
