# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1617_CrmAuthenticationToken

- ea: `0x68140`
- end: `0x682c7`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1617_CrmAuthenticationToken`
- size: `391`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x60`
- `0x120`
- `0x1e0`
- `0x2c0`
- `0x3c0`
- `0x480`
- `0x540`
- `0x6ac0`
- `0x682d0`

## callees

- `0x68140`

## string_xrefs

- `0x68180`: `CrmAuthenticationToken`
- `0x68185`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x68263`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x6827e`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x68294`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x682aa`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x681a7`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x681fa`: `http://schemas.xmlsoap.org/soap/envelope/`

## pseudocode

```c

```

## disassembly

```asm
0x68140  ldarg.3
0x68141  brtrue.s loc_68150
0x68143  ldarg.s  4
0x68145  brfalse.s loc_6814F
0x68147  ldarg.0
0x68148  ldarg.1
0x68149  ldarg.2
0x6814a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x6814f  ret
0x68150  ldarg.s  5
0x68152  brtrue.s loc_68170
0x68154  ldarg.3
0x68155  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x6815a  stloc.0
0x6815b  ldloc.0
0x6815c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken
0x68161  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x68166  beq.s    loc_68170
0x68168  ldarg.0
0x68169  ldarg.3
0x6816a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x6816f  throw
0x68170  ldarg.0
0x68171  ldarg.1
0x68172  ldarg.2
0x68173  ldarg.3
0x68174  ldc.i4.0
0x68175  ldnull
0x68176  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x6817b  ldarg.s  5
0x6817d  brfalse.s loc_6818F
0x6817f  ldarg.0
0x68180  ldstr    aCrmauthenticat// "CrmAuthenticationToken"
0x68185  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x6818a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6818f  ldarg.3
0x68190  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand()
0x68195  ldstr    a0// "0"
0x6819a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6819f  brfalse.s loc_681B7
0x681a1  ldarg.0
0x681a2  ldstr    aMustunderstand// "mustUnderstand"
0x681a7  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x681ac  ldarg.3
0x681ad  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand()
0x681b2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x681b7  ldarg.3
0x681b8  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand12()
0x681bd  ldstr    a0// "0"
0x681c2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x681c7  brfalse.s loc_681DF
0x681c9  ldarg.0
0x681ca  ldstr    aMustunderstand// "mustUnderstand"
0x681cf  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x681d4  ldarg.3
0x681d5  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand12()
0x681da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x681df  ldarg.3
0x681e0  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x681e5  brfalse.s loc_6820A
0x681e7  ldarg.3
0x681e8  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x681ed  callvirt instance int32 [mscorlib]System.String::get_Length()
0x681f2  brfalse.s loc_6820A
0x681f4  ldarg.0
0x681f5  ldstr    aActor// "actor"
0x681fa  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x681ff  ldarg.3
0x68200  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x68205  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6820a  ldarg.3
0x6820b  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x68210  brfalse.s loc_68235
0x68212  ldarg.3
0x68213  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x68218  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6821d  brfalse.s loc_68235
0x6821f  ldarg.0
0x68220  ldstr    aRole// "role"
0x68225  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x6822a  ldarg.3
0x6822b  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x68230  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x68235  ldarg.3
0x68236  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedRelay()
0x6823b  ldstr    a0// "0"
0x68240  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x68245  brfalse.s loc_6825D
0x68247  ldarg.0
0x68248  ldstr    aRelay// "relay"
0x6824d  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x68252  ldarg.3
0x68253  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedRelay()
0x68258  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6825d  ldarg.0
0x6825e  ldstr    aAuthentication// "AuthenticationType"
0x68263  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x68268  ldarg.3
0x68269  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_AuthenticationType()
0x6826e  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x68273  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x68278  ldarg.0
0x68279  ldstr    aCrmticket// "CrmTicket"
0x6827e  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x68283  ldarg.3
0x68284  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CrmTicket()
0x68289  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x6828e  ldarg.0
0x6828f  ldstr    aOrganizationna// "OrganizationName"
0x68294  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x68299  ldarg.3
0x6829a  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_OrganizationName()
0x6829f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x682a4  ldarg.0
0x682a5  ldstr    aCallerid// "CallerId"
0x682aa  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x682af  ldarg.3
0x682b0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CallerId()
0x682b5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x682ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x682bf  ldarg.0
0x682c0  ldarg.3
0x682c1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x682c6  ret
```
