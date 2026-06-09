# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::GetObjectData

- ea: `0x13020`
- end: `0x1328b`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::GetObjectData`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `broker_com_uri`

## callees

- `0x10d90`
- `0x10da0`
- `0x10e50`
- `0x10e60`
- `0x10e70`
- `0x10e80`
- `0x10fc0`
- `0x10fd0`
- `0x10fe0`
- `0x10ff0`
- `0x11000`
- `0x11010`
- `0x11020`
- `0x11030`
- `0x11040`
- `0x11070`
- `0x110a0`
- `0x125e0`
- `0x12600`
- `0x12620`
- `0x12640`
- `0x12660`
- `0x12680`
- `0x126a0`
- `0x126c0`
- `0x126e0`
- `0x12700`
- `0x12720`
- `0x12740`
- `0x12760`
- `0x12780`
- `0x13020`
- `0x13290`
- `0x13930`
- `0x13950`

## string_xrefs

- `0x13264`: `SessionToken`

## pseudocode

```c

```

## disassembly

```asm
0x13020  ldarg.1
0x13021  ldtoken  [System.IdentityModel]System.IdentityModel.Tokens.SessionSecurityToken
0x13026  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1302b  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::SetType(class [mscorlib]System.Type)
0x13030  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x13035  stloc.0
0x13036  call     class Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Instance()
0x1303b  stloc.1
0x1303c  ldloc.0
0x1303d  ldloc.1
0x1303e  call     class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::CreateBinaryWriter(class [mscorlib]System.IO.Stream, class [System.Runtime.Serialization]System.Xml.IXmlDictionary)
0x13043  stloc.2
0x13044  ldarg.0
0x13045  call     instance bool Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_IsSecurityContextSecurityTokenWrapper()
0x1304a  brfalse.s loc_13060
0x1304c  ldloc.2
0x1304d  ldloc.1
0x1304e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_SecurityContextToken()
0x13053  ldloc.1
0x13054  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13059  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x1305e  br.s     loc_130B6
0x13060  ldloc.2
0x13061  ldloc.1
0x13062  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_SessionToken()
0x13067  ldloc.1
0x13068  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1306d  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x13072  ldarg.0
0x13073  call     instance bool Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_IsPersistent()
0x13078  brfalse.s loc_13091
0x1307a  ldloc.2
0x1307b  ldloc.1
0x1307c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_PersistentTrue()
0x13081  ldloc.1
0x13082  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13087  ldstr    asc_1DBD8// ""
0x1308c  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x13091  ldarg.0
0x13092  call     instance string Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_Context()
0x13097  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1309c  brtrue.s loc_130B6
0x1309e  ldloc.2
0x1309f  ldloc.1
0x130a0  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Context()
0x130a5  ldloc.1
0x130a6  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x130ab  ldarg.0
0x130ac  call     instance string Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_Context()
0x130b1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x130b6  ldloc.2
0x130b7  ldloc.1
0x130b8  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Version()
0x130bd  ldloc.1
0x130be  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x130c3  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x130c8  ldloc.2
0x130c9  ldstr    a1// "1"
0x130ce  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x130d3  ldloc.2
0x130d4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x130d9  ldloc.2
0x130da  ldloc.1
0x130db  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_SecureConversationVersion()
0x130e0  ldloc.1
0x130e1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x130e6  ldarg.0
0x130e7  call     instance class [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_Version()
0x130ec  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString [System.ServiceModel]System.ServiceModel.Security.SecureConversationVersion::get_Namespace()
0x130f1  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryString::get_Value()
0x130f6  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x130fb  ldloc.2
0x130fc  ldloc.1
0x130fd  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Id()
0x13102  ldloc.1
0x13103  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13108  ldarg.0
0x13109  call     instance string Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_Id()
0x1310e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x13113  ldloc.2
0x13114  ldloc.1
0x13115  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ContextId()
0x1311a  ldloc.1
0x1311b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13120  ldarg.0
0x13121  call     instance class [System.Runtime.Serialization]System.Xml.UniqueId Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_ContextId()
0x13126  callvirt instance string [mscorlib]System.Object::ToString()
0x1312b  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementStringAsUniqueId(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, string id)
0x13130  ldarg.0
0x13131  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey> Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_SecurityKeys()
0x13136  call     T0x2B000029
0x1313b  callvirt instance unsigned int8[] [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey::GetSymmetricKey()
0x13140  stloc.3
0x13141  ldloc.2
0x13142  ldloc.1
0x13143  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Key()
0x13148  ldloc.1
0x13149  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1314e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x13153  ldloc.2
0x13154  ldloc.3
0x13155  ldc.i4.0
0x13156  ldloc.3
0x13157  ldlen
0x13158  conv.i4
0x13159  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteBase64(unsigned int8[], int32, int32)
0x1315e  ldloc.2
0x1315f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x13164  ldarg.0
0x13165  call     instance object Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_KeyGeneration()
0x1316a  brfalse.s loc_13189
0x1316c  ldloc.2
0x1316d  ldloc.1
0x1316e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_KeyGeneration()
0x13173  ldloc.1
0x13174  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13179  ldarg.0
0x1317a  call     instance object Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_KeyGeneration()
0x1317f  callvirt instance string [mscorlib]System.Object::ToString()
0x13184  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementStringAsUniqueId(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, string id)
0x13189  ldloc.2
0x1318a  ldloc.1
0x1318b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EffectiveTime()
0x13190  ldloc.1
0x13191  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13196  ldarg.0
0x13197  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_ValidFrom()
0x1319c  stloc.s  4
0x1319e  ldloca.s 4
0x131a0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x131a5  stloc.s  4
0x131a7  ldloca.s 4
0x131a9  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x131ae  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x131b3  ldloc.2
0x131b4  ldloc.1
0x131b5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ExpiryTime()
0x131ba  ldloc.1
0x131bb  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x131c0  ldarg.0
0x131c1  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_ValidTo()
0x131c6  stloc.s  4
0x131c8  ldloca.s 4
0x131ca  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x131cf  stloc.s  4
0x131d1  ldloca.s 4
0x131d3  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x131d8  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x131dd  ldloc.2
0x131de  ldloc.1
0x131df  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_KeyEffectiveTime()
0x131e4  ldloc.1
0x131e5  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x131ea  ldarg.0
0x131eb  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_KeyEffectiveTime()
0x131f0  stloc.s  4
0x131f2  ldloca.s 4
0x131f4  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x131f9  stloc.s  4
0x131fb  ldloca.s 4
0x131fd  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x13202  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x13207  ldloc.2
0x13208  ldloc.1
0x13209  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_KeyExpiryTime()
0x1320e  ldloc.1
0x1320f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13214  ldarg.0
0x13215  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_KeyExpirationTime()
0x1321a  stloc.s  4
0x1321c  ldloca.s 4
0x1321e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x13223  stloc.s  4
0x13225  ldloca.s 4
0x13227  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1322c  call     void Microsoft.Crm.Authentication.Claims.WifTransform.XmlUtil::WriteElementContentAsInt64(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter writer, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString localName, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString ns, int64 value)
0x13231  ldarg.0
0x13232  ldloc.2
0x13233  ldloc.1
0x13234  ldarg.0
0x13235  call     instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_ClaimsPrincipal()
0x1323a  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WritePrincipal(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary dictionary, class [mscorlib]System.Security.Claims.ClaimsPrincipal principal)
0x1323f  ldloc.2
0x13240  ldloc.1
0x13241  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EndpointId()
0x13246  ldloc.1
0x13247  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1324c  ldarg.0
0x1324d  call     instance string Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::get_EndpointId()
0x13252  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteElementString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x13257  ldloc.2
0x13258  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1325d  ldloc.2
0x1325e  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x13263  ldarg.1
0x13264  ldstr    aSessiontoken// "SessionToken"
0x13269  ldloc.0
0x1326a  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x1326f  callvirt instance void [mscorlib]System.Runtime.Serialization.SerializationInfo::AddValue(string, object)
0x13274  leave.s  loc_1328A
0x13276  ldloc.2
0x13277  brfalse.s loc_1327F
0x13279  ldloc.2
0x1327a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1327f  endfinally
0x13280  ldloc.0
0x13281  brfalse.s loc_13289
0x13283  ldloc.0
0x13284  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13289  endfinally
0x1328a  ret
```
