# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write122_CrmAuthenticationToken

- ea: `0x650`
- end: `0x7d7`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write122_CrmAuthenticationToken`
- size: `391`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x600`
- `0x1940`
- `0x6a1c0`

## callees

- `0x650`

## string_xrefs

- `0x690`: `CrmAuthenticationToken`
- `0x695`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x773`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x78e`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x7a4`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x7ba`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x6b7`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x70a`: `http://schemas.xmlsoap.org/soap/envelope/`

## pseudocode

```c

```

## disassembly

```asm
0x650  ldarg.3
0x651  brtrue.s loc_660
0x653  ldarg.s  4
0x655  brfalse.s loc_65F
0x657  ldarg.0
0x658  ldarg.1
0x659  ldarg.2
0x65a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x65f  ret
0x660  ldarg.s  5
0x662  brtrue.s loc_680
0x664  ldarg.3
0x665  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x66a  stloc.0
0x66b  ldloc.0
0x66c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken
0x671  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x676  beq.s    loc_680
0x678  ldarg.0
0x679  ldarg.3
0x67a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x67f  throw
0x680  ldarg.0
0x681  ldarg.1
0x682  ldarg.2
0x683  ldarg.3
0x684  ldc.i4.0
0x685  ldnull
0x686  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x68b  ldarg.s  5
0x68d  brfalse.s loc_69F
0x68f  ldarg.0
0x690  ldstr    aCrmauthenticat// "CrmAuthenticationToken"
0x695  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x69a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x69f  ldarg.3
0x6a0  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand()
0x6a5  ldstr    a0// "0"
0x6aa  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6af  brfalse.s loc_6C7
0x6b1  ldarg.0
0x6b2  ldstr    aMustunderstand// "mustUnderstand"
0x6b7  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x6bc  ldarg.3
0x6bd  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand()
0x6c2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6c7  ldarg.3
0x6c8  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand12()
0x6cd  ldstr    a0// "0"
0x6d2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6d7  brfalse.s loc_6EF
0x6d9  ldarg.0
0x6da  ldstr    aMustunderstand// "mustUnderstand"
0x6df  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x6e4  ldarg.3
0x6e5  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand12()
0x6ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6ef  ldarg.3
0x6f0  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x6f5  brfalse.s loc_71A
0x6f7  ldarg.3
0x6f8  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x6fd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x702  brfalse.s loc_71A
0x704  ldarg.0
0x705  ldstr    aActor// "actor"
0x70a  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x70f  ldarg.3
0x710  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x715  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x71a  ldarg.3
0x71b  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x720  brfalse.s loc_745
0x722  ldarg.3
0x723  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x728  callvirt instance int32 [mscorlib]System.String::get_Length()
0x72d  brfalse.s loc_745
0x72f  ldarg.0
0x730  ldstr    aRole// "role"
0x735  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x73a  ldarg.3
0x73b  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x740  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x745  ldarg.3
0x746  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedRelay()
0x74b  ldstr    a0// "0"
0x750  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x755  brfalse.s loc_76D
0x757  ldarg.0
0x758  ldstr    aRelay// "relay"
0x75d  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x762  ldarg.3
0x763  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedRelay()
0x768  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x76d  ldarg.0
0x76e  ldstr    aAuthentication// "AuthenticationType"
0x773  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x778  ldarg.3
0x779  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_AuthenticationType()
0x77e  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x783  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x788  ldarg.0
0x789  ldstr    aCrmticket// "CrmTicket"
0x78e  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x793  ldarg.3
0x794  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CrmTicket()
0x799  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x79e  ldarg.0
0x79f  ldstr    aOrganizationna// "OrganizationName"
0x7a4  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x7a9  ldarg.3
0x7aa  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_OrganizationName()
0x7af  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x7b4  ldarg.0
0x7b5  ldstr    aCallerid// "CallerId"
0x7ba  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x7bf  ldarg.3
0x7c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmAuthenticationToken::get_CallerId()
0x7c5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x7ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x7cf  ldarg.0
0x7d0  ldarg.3
0x7d1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x7d6  ret
```
