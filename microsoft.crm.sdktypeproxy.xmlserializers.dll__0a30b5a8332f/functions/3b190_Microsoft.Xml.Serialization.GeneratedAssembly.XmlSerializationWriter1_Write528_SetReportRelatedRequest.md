# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write528_SetReportRelatedRequest

- ea: `0x3b190`
- end: `0x3b336`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write528_SetReportRelatedRequest`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x3b190`

## string_xrefs

- `0x3b1d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b1ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b205`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b22a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b24f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b266`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b29e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b2b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b2ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3b306`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x3b190  ldarg.3
0x3b191  brtrue.s loc_3B1A0
0x3b193  ldarg.s  4
0x3b195  brfalse.s loc_3B19F
0x3b197  ldarg.0
0x3b198  ldarg.1
0x3b199  ldarg.2
0x3b19a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3b19f  ret
0x3b1a0  ldarg.s  5
0x3b1a2  brtrue.s loc_3B1C0
0x3b1a4  ldarg.3
0x3b1a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3b1aa  stloc.0
0x3b1ab  ldloc.0
0x3b1ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetReportRelatedRequest
0x3b1b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b1b6  beq.s    loc_3B1C0
0x3b1b8  ldarg.0
0x3b1b9  ldarg.3
0x3b1ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3b1bf  throw
0x3b1c0  ldarg.0
0x3b1c1  ldarg.1
0x3b1c2  ldarg.2
0x3b1c3  ldarg.3
0x3b1c4  ldc.i4.0
0x3b1c5  ldnull
0x3b1c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3b1cb  ldarg.s  5
0x3b1cd  brfalse.s loc_3B1DF
0x3b1cf  ldarg.0
0x3b1d0  ldstr    aSetreportrelat// "SetReportRelatedRequest"
0x3b1d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b1da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3b1df  ldarg.3
0x3b1e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3b1e5  stloc.1
0x3b1e6  ldloc.1
0x3b1e7  brfalse.s loc_3B224
0x3b1e9  ldarg.0
0x3b1ea  ldstr    aOptionalparame_0// "OptionalParameters"
0x3b1ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b1f4  ldnull
0x3b1f5  ldc.i4.0
0x3b1f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3b1fb  ldc.i4.0
0x3b1fc  stloc.2
0x3b1fd  br.s     loc_3B218
0x3b1ff  ldarg.0
0x3b200  ldstr    aOptionalparame// "OptionalParameter"
0x3b205  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b20a  ldloc.1
0x3b20b  ldloc.2
0x3b20c  ldelem.ref
0x3b20d  ldc.i4.1
0x3b20e  ldc.i4.0
0x3b20f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3b214  ldloc.2
0x3b215  ldc.i4.1
0x3b216  add
0x3b217  stloc.2
0x3b218  ldloc.2
0x3b219  ldloc.1
0x3b21a  ldlen
0x3b21b  conv.i4
0x3b21c  blt.s    loc_3B1FF
0x3b21e  ldarg.0
0x3b21f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3b224  ldarg.0
0x3b225  ldstr    aReportid_0// "ReportId"
0x3b22a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b22f  ldarg.3
0x3b230  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetReportRelatedRequest::get_ReportId()
0x3b235  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3b23a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3b23f  ldarg.3
0x3b240  callvirt instance int32[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetReportRelatedRequest::get_Entities()
0x3b245  stloc.3
0x3b246  ldloc.3
0x3b247  brfalse.s loc_3B28C
0x3b249  ldarg.0
0x3b24a  ldstr    aEntities// "Entities"
0x3b24f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b254  ldnull
0x3b255  ldc.i4.0
0x3b256  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3b25b  ldc.i4.0
0x3b25c  stloc.s  4
0x3b25e  br.s     loc_3B27F
0x3b260  ldarg.0
0x3b261  ldstr    aInt// "int"
0x3b266  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b26b  ldloc.3
0x3b26c  ldloc.s  4
0x3b26e  ldelem.i4
0x3b26f  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3b274  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3b279  ldloc.s  4
0x3b27b  ldc.i4.1
0x3b27c  add
0x3b27d  stloc.s  4
0x3b27f  ldloc.s  4
0x3b281  ldloc.3
0x3b282  ldlen
0x3b283  conv.i4
0x3b284  blt.s    loc_3B260
0x3b286  ldarg.0
0x3b287  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3b28c  ldarg.3
0x3b28d  callvirt instance int32[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetReportRelatedRequest::get_Categories()
0x3b292  stloc.s  5
0x3b294  ldloc.s  5
0x3b296  brfalse.s loc_3B2DD
0x3b298  ldarg.0
0x3b299  ldstr    aCategories// "Categories"
0x3b29e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b2a3  ldnull
0x3b2a4  ldc.i4.0
0x3b2a5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3b2aa  ldc.i4.0
0x3b2ab  stloc.s  6
0x3b2ad  br.s     loc_3B2CF
0x3b2af  ldarg.0
0x3b2b0  ldstr    aInt// "int"
0x3b2b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b2ba  ldloc.s  5
0x3b2bc  ldloc.s  6
0x3b2be  ldelem.i4
0x3b2bf  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3b2c4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3b2c9  ldloc.s  6
0x3b2cb  ldc.i4.1
0x3b2cc  add
0x3b2cd  stloc.s  6
0x3b2cf  ldloc.s  6
0x3b2d1  ldloc.s  5
0x3b2d3  ldlen
0x3b2d4  conv.i4
0x3b2d5  blt.s    loc_3B2AF
0x3b2d7  ldarg.0
0x3b2d8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3b2dd  ldarg.3
0x3b2de  callvirt instance int32[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetReportRelatedRequest::get_Visibility()
0x3b2e3  stloc.s  7
0x3b2e5  ldloc.s  7
0x3b2e7  brfalse.s loc_3B32E
0x3b2e9  ldarg.0
0x3b2ea  ldstr    aVisibility// "Visibility"
0x3b2ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b2f4  ldnull
0x3b2f5  ldc.i4.0
0x3b2f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3b2fb  ldc.i4.0
0x3b2fc  stloc.s  8
0x3b2fe  br.s     loc_3B320
0x3b300  ldarg.0
0x3b301  ldstr    aInt// "int"
0x3b306  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3b30b  ldloc.s  7
0x3b30d  ldloc.s  8
0x3b30f  ldelem.i4
0x3b310  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x3b315  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3b31a  ldloc.s  8
0x3b31c  ldc.i4.1
0x3b31d  add
0x3b31e  stloc.s  8
0x3b320  ldloc.s  8
0x3b322  ldloc.s  7
0x3b324  ldlen
0x3b325  conv.i4
0x3b326  blt.s    loc_3B300
0x3b328  ldarg.0
0x3b329  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3b32e  ldarg.0
0x3b32f  ldarg.3
0x3b330  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3b335  ret
```
