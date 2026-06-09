# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write815_Item

- ea: `0x46350`
- end: `0x46438`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write815_Item`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x46350`

## string_xrefs

- `0x46395`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x463af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x463c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x463ea`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x46400`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4641b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x463e5`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x46350  ldarg.3
0x46351  brtrue.s loc_46360
0x46353  ldarg.s  4
0x46355  brfalse.s loc_4635F
0x46357  ldarg.0
0x46358  ldarg.1
0x46359  ldarg.2
0x4635a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4635f  ret
0x46360  ldarg.s  5
0x46362  brtrue.s loc_46380
0x46364  ldarg.3
0x46365  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4636a  stloc.0
0x4636b  ldloc.0
0x4636c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveReportSqlFromQueryRequest
0x46371  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x46376  beq.s    loc_46380
0x46378  ldarg.0
0x46379  ldarg.3
0x4637a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4637f  throw
0x46380  ldarg.0
0x46381  ldarg.1
0x46382  ldarg.2
0x46383  ldarg.3
0x46384  ldc.i4.0
0x46385  ldnull
0x46386  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4638b  ldarg.s  5
0x4638d  brfalse.s loc_4639F
0x4638f  ldarg.0
0x46390  ldstr    aRetrievereport// "RetrieveReportSqlFromQueryRequest"
0x46395  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4639a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4639f  ldarg.3
0x463a0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x463a5  stloc.1
0x463a6  ldloc.1
0x463a7  brfalse.s loc_463E4
0x463a9  ldarg.0
0x463aa  ldstr    aOptionalparame_0// "OptionalParameters"
0x463af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x463b4  ldnull
0x463b5  ldc.i4.0
0x463b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x463bb  ldc.i4.0
0x463bc  stloc.2
0x463bd  br.s     loc_463D8
0x463bf  ldarg.0
0x463c0  ldstr    aOptionalparame// "OptionalParameter"
0x463c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x463ca  ldloc.1
0x463cb  ldloc.2
0x463cc  ldelem.ref
0x463cd  ldc.i4.1
0x463ce  ldc.i4.0
0x463cf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x463d4  ldloc.2
0x463d5  ldc.i4.1
0x463d6  add
0x463d7  stloc.2
0x463d8  ldloc.2
0x463d9  ldloc.1
0x463da  ldlen
0x463db  conv.i4
0x463dc  blt.s    loc_463BF
0x463de  ldarg.0
0x463df  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x463e4  ldarg.0
0x463e5  ldstr    aFetchxml_1// "FetchXml"
0x463ea  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x463ef  ldarg.3
0x463f0  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveReportSqlFromQueryRequest::get_FetchXml()
0x463f5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x463fa  ldarg.0
0x463fb  ldstr    aUsestoredproce// "UseStoredProcedures"
0x46400  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x46405  ldarg.3
0x46406  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveReportSqlFromQueryRequest::get_UseStoredProcedures()
0x4640b  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x46410  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x46415  ldarg.0
0x46416  ldstr    aRetrieveallcol// "RetrieveAllColumns"
0x4641b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x46420  ldarg.3
0x46421  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RetrieveReportSqlFromQueryRequest::get_RetrieveAllColumns()
0x46426  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4642b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x46430  ldarg.0
0x46431  ldarg.3
0x46432  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x46437  ret
```
