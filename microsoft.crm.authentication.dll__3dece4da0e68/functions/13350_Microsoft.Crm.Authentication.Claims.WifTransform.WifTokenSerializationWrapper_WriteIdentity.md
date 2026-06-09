# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteIdentity

- ea: `0x13350`
- end: `0x134e8`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteIdentity`
- size: `408`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x132e0`
- `0x13350`

## callees

- `0x10db0`
- `0x10df0`
- `0x10ed0`
- `0x10ee0`
- `0x10f30`
- `0x10f80`
- `0x10f90`
- `0x10fa0`
- `0x10ff0`
- `0x11060`
- `0x13350`
- `0x134f0`

## string_xrefs

- `0x13351`: `dictionaryWriter`

## pseudocode

```c

```

## disassembly

```asm
0x13350  ldarg.1
0x13351  ldstr    aDictionarywrit// "dictionaryWriter"
0x13356  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1335b  ldarg.2
0x1335c  ldstr    aDictionary// "dictionary"
0x13361  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13366  ldarg.3
0x13367  ldstr    aIdentity_0// "identity"
0x1336c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x13371  ldarg.1
0x13372  ldarg.2
0x13373  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Identity()
0x13378  ldarg.2
0x13379  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1337e  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x13383  ldarg.3
0x13384  isinst   [mscorlib]System.Security.Principal.WindowsIdentity
0x13389  stloc.0
0x1338a  ldloc.0
0x1338b  brfalse.s loc_133A5
0x1338d  ldarg.1
0x1338e  ldarg.2
0x1338f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_WindowsLogonName()
0x13394  ldarg.2
0x13395  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x1339a  ldloc.0
0x1339b  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x133a0  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x133a5  ldarg.3
0x133a6  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_AuthenticationType()
0x133ab  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x133b0  brtrue.s loc_133CA
0x133b2  ldarg.1
0x133b3  ldarg.2
0x133b4  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_AuthenticationType()
0x133b9  ldarg.2
0x133ba  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x133bf  ldarg.3
0x133c0  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_AuthenticationType()
0x133c5  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x133ca  ldarg.3
0x133cb  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Label()
0x133d0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x133d5  brtrue.s loc_133EF
0x133d7  ldarg.1
0x133d8  ldarg.2
0x133d9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Label()
0x133de  ldarg.2
0x133df  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x133e4  ldarg.3
0x133e5  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Label()
0x133ea  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x133ef  ldarg.3
0x133f0  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_NameClaimType()
0x133f5  brfalse.s loc_1340F
0x133f7  ldarg.1
0x133f8  ldarg.2
0x133f9  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_NameClaimType()
0x133fe  ldarg.2
0x133ff  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13404  ldarg.3
0x13405  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_NameClaimType()
0x1340a  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x1340f  ldarg.3
0x13410  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_RoleClaimType()
0x13415  brfalse.s loc_1342F
0x13417  ldarg.1
0x13418  ldarg.2
0x13419  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_RoleClaimType()
0x1341e  ldarg.2
0x1341f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13424  ldarg.3
0x13425  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_RoleClaimType()
0x1342a  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteAttributeString(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, string)
0x1342f  ldarg.3
0x13430  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x13435  brfalse.s loc_1345E
0x13437  ldarg.1
0x13438  ldarg.2
0x13439  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_ClaimCollection()
0x1343e  ldarg.2
0x1343f  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13444  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x13449  ldarg.3
0x1344a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> [mscorlib]System.Security.Claims.ClaimsIdentity::get_Claims()
0x1344f  stloc.1
0x13450  ldarg.1
0x13451  ldarg.2
0x13452  ldloc.1
0x13453  call     void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteClaims(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary dictionary, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [mscorlib]System.Security.Claims.Claim> claims)
0x13458  ldarg.1
0x13459  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1345e  ldarg.3
0x1345f  callvirt instance class [mscorlib]System.Security.Claims.ClaimsIdentity [mscorlib]System.Security.Claims.ClaimsIdentity::get_Actor()
0x13464  brfalse.s loc_1348C
0x13466  ldarg.1
0x13467  ldarg.2
0x13468  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_Actor()
0x1346d  ldarg.2
0x1346e  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x13473  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x13478  ldarg.0
0x13479  ldarg.1
0x1347a  ldarg.2
0x1347b  ldarg.3
0x1347c  callvirt instance class [mscorlib]System.Security.Claims.ClaimsIdentity [mscorlib]System.Security.Claims.ClaimsIdentity::get_Actor()
0x13481  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::WriteIdentity(class [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter dictionaryWriter, class Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary dictionary, class [mscorlib]System.Security.Claims.ClaimsIdentity identity)
0x13486  ldarg.1
0x13487  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1348c  ldarg.3
0x1348d  callvirt instance object [mscorlib]System.Security.Claims.ClaimsIdentity::get_BootstrapContext()
0x13492  brfalse.s loc_134E1
0x13494  ldarg.1
0x13495  ldarg.2
0x13496  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_BootstrapToken()
0x1349b  ldarg.2
0x1349c  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.NetSessionDictionary::get_EmptyString()
0x134a1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryWriter::WriteStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x134a6  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x134ab  stloc.2
0x134ac  newobj   instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::.ctor()
0x134b1  ldloc.2
0x134b2  ldarg.3
0x134b3  callvirt instance object [mscorlib]System.Security.Claims.ClaimsIdentity::get_BootstrapContext()
0x134b8  callvirt instance void [mscorlib]System.Runtime.Serialization.Formatters.Binary.BinaryFormatter::Serialize(class [mscorlib]System.IO.Stream, object)
0x134bd  ldloc.2
0x134be  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x134c3  stloc.3
0x134c4  ldarg.1
0x134c5  ldloc.3
0x134c6  ldc.i4.0
0x134c7  ldloc.3
0x134c8  ldlen
0x134c9  conv.i4
0x134ca  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteBase64(unsigned int8[], int32, int32)
0x134cf  leave.s  loc_134DB
0x134d1  ldloc.2
0x134d2  brfalse.s loc_134DA
0x134d4  ldloc.2
0x134d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x134da  endfinally
0x134db  ldarg.1
0x134dc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x134e1  ldarg.1
0x134e2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x134e7  ret
```
