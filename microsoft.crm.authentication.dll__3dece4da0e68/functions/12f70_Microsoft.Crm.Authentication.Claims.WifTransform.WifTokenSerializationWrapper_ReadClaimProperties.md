# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadClaimProperties

- ea: `0x12f70`
- end: `0x13019`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadClaimProperties`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x12e90`

## callees

- `0x11e60`
- `0x11ec0`
- `0x11ed0`
- `0x11f50`
- `0x12f70`

## string_xrefs

- `0x12f71`: `dictionaryReader`

## pseudocode

```c

```

## disassembly

```asm
0x12f70  ldarg.0
0x12f71  ldstr    aDictionaryread// "dictionaryReader"
0x12f76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12f7b  ldarg.1
0x12f7c  ldstr    aDictionary// "dictionary"
0x12f81  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12f86  ldarg.2
0x12f87  ldstr    aProperties// "properties"
0x12f8c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12f91  ldarg.0
0x12f92  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x12f97  br.s     loc_12FFE
0x12f99  ldarg.0
0x12f9a  ldarg.1
0x12f9b  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimPropertyName()
0x12fa0  ldarg.1
0x12fa1  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12fa6  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12fab  stloc.0
0x12fac  ldarg.0
0x12fad  ldarg.1
0x12fae  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimPropertyValue()
0x12fb3  ldarg.1
0x12fb4  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x12fb9  callvirt instance string [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::GetAttribute(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x12fbe  stloc.1
0x12fbf  ldloc.0
0x12fc0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12fc5  brfalse.s loc_12FD2
0x12fc7  ldstr    aTheClaimproper// "The ClaimProperty key cannot be a null "...
0x12fcc  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x12fd1  throw
0x12fd2  ldloc.1
0x12fd3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12fd8  brfalse.s loc_12FE5
0x12fda  ldstr    aTheClaimvalueC// "The ClaimValue cannot be null."
0x12fdf  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x12fe4  throw
0x12fe5  ldarg.2
0x12fe6  ldloc.0
0x12fe7  ldloc.1
0x12fe8  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::.ctor(var<u1>, !!T0)
0x12fed  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::Add(var<u1>)
0x12ff2  ldarg.0
0x12ff3  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::ReadFullStartElement()
0x12ff8  ldarg.0
0x12ff9  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x12ffe  ldarg.0
0x12fff  ldarg.1
0x13000  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_ClaimProperty()
0x13005  ldarg.1
0x13006  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryString Microsoft.Crm.Authentication.Claims.WifTransform.WifSessionDictionary::get_EmptyString()
0x1300b  callvirt instance bool [System.Runtime.Serialization]System.Xml.XmlDictionaryReader::IsStartElement(class [System.Runtime.Serialization]System.Xml.XmlDictionaryString, class [System.Runtime.Serialization]System.Xml.XmlDictionaryString)
0x13010  brtrue.s loc_12F99
0x13012  ldarg.0
0x13013  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadEndElement()
0x13018  ret
```
