# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1616_CorrelationToken

- ea: `0x67fc0`
- end: `0x68133`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1616_CorrelationToken`
- size: `371`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

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

- `0x5cf0`
- `0x67fc0`

## string_xrefs

- `0x68000`: `CorrelationToken`
- `0x68005`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x680e3`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x680fe`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x68116`: `http://schemas.microsoft.com/crm/2007/CoreTypes`
- `0x68027`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x6807a`: `http://schemas.xmlsoap.org/soap/envelope/`
- `0x680f9`: `CorrelationUpdatedTime`

## pseudocode

```c

```

## disassembly

```asm
0x67fc0  ldarg.3
0x67fc1  brtrue.s loc_67FD0
0x67fc3  ldarg.s  4
0x67fc5  brfalse.s loc_67FCF
0x67fc7  ldarg.0
0x67fc8  ldarg.1
0x67fc9  ldarg.2
0x67fca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x67fcf  ret
0x67fd0  ldarg.s  5
0x67fd2  brtrue.s loc_67FF0
0x67fd4  ldarg.3
0x67fd5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x67fda  stloc.0
0x67fdb  ldloc.0
0x67fdc  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken
0x67fe1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67fe6  beq.s    loc_67FF0
0x67fe8  ldarg.0
0x67fe9  ldarg.3
0x67fea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x67fef  throw
0x67ff0  ldarg.0
0x67ff1  ldarg.1
0x67ff2  ldarg.2
0x67ff3  ldarg.3
0x67ff4  ldc.i4.0
0x67ff5  ldnull
0x67ff6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x67ffb  ldarg.s  5
0x67ffd  brfalse.s loc_6800F
0x67fff  ldarg.0
0x68000  ldstr    aCorrelationtok// "CorrelationToken"
0x68005  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x6800a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x6800f  ldarg.3
0x68010  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand()
0x68015  ldstr    a0// "0"
0x6801a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x6801f  brfalse.s loc_68037
0x68021  ldarg.0
0x68022  ldstr    aMustunderstand// "mustUnderstand"
0x68027  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x6802c  ldarg.3
0x6802d  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand()
0x68032  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x68037  ldarg.3
0x68038  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand12()
0x6803d  ldstr    a0// "0"
0x68042  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x68047  brfalse.s loc_6805F
0x68049  ldarg.0
0x6804a  ldstr    aMustunderstand// "mustUnderstand"
0x6804f  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x68054  ldarg.3
0x68055  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedMustUnderstand12()
0x6805a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6805f  ldarg.3
0x68060  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x68065  brfalse.s loc_6808A
0x68067  ldarg.3
0x68068  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x6806d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x68072  brfalse.s loc_6808A
0x68074  ldarg.0
0x68075  ldstr    aActor// "actor"
0x6807a  ldstr    aHttpSchemasXml// "http://schemas.xmlsoap.org/soap/envelop"...
0x6807f  ldarg.3
0x68080  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Actor()
0x68085  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x6808a  ldarg.3
0x6808b  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x68090  brfalse.s loc_680B5
0x68092  ldarg.3
0x68093  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x68098  callvirt instance int32 [mscorlib]System.String::get_Length()
0x6809d  brfalse.s loc_680B5
0x6809f  ldarg.0
0x680a0  ldstr    aRole// "role"
0x680a5  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x680aa  ldarg.3
0x680ab  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_Role()
0x680b0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x680b5  ldarg.3
0x680b6  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedRelay()
0x680bb  ldstr    a0// "0"
0x680c0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x680c5  brfalse.s loc_680DD
0x680c7  ldarg.0
0x680c8  ldstr    aRelay// "relay"
0x680cd  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2003/05/soap-envelope"
0x680d2  ldarg.3
0x680d3  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.SoapHeader::get_EncodedRelay()
0x680d8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteAttribute(string, string, string)
0x680dd  ldarg.0
0x680de  ldstr    aCorrelationid_0// "CorrelationId"
0x680e3  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x680e8  ldarg.3
0x680e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationId()
0x680ee  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x680f3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x680f8  ldarg.0
0x680f9  ldstr    aCorrelationupd_0// "CorrelationUpdatedTime"
0x680fe  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x68103  ldarg.3
0x68104  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_CorrelationUpdatedTime()
0x68109  ldc.i4.0
0x6810a  ldc.i4.0
0x6810b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x68110  ldarg.0
0x68111  ldstr    aDepth// "Depth"
0x68116  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/crm/2007/C"...
0x6811b  ldarg.3
0x6811c  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken::get_Depth()
0x68121  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x68126  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x6812b  ldarg.0
0x6812c  ldarg.3
0x6812d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x68132  ret
```
