# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write960_Item

- ea: `0x4d320`
- end: `0x4d428`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write960_Item`
- size: `264`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x4d320`

## string_xrefs

- `0x4d365`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4d37f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4d395`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4d3ba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4d3d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4d3f0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4d40b`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x4d320  ldarg.3
0x4d321  brtrue.s loc_4D330
0x4d323  ldarg.s  4
0x4d325  brfalse.s loc_4D32F
0x4d327  ldarg.0
0x4d328  ldarg.1
0x4d329  ldarg.2
0x4d32a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4d32f  ret
0x4d330  ldarg.s  5
0x4d332  brtrue.s loc_4D350
0x4d334  ldarg.3
0x4d335  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4d33a  stloc.0
0x4d33b  ldloc.0
0x4d33c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetDistinctValuesImportFileRequest
0x4d341  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4d346  beq.s    loc_4D350
0x4d348  ldarg.0
0x4d349  ldarg.3
0x4d34a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4d34f  throw
0x4d350  ldarg.0
0x4d351  ldarg.1
0x4d352  ldarg.2
0x4d353  ldarg.3
0x4d354  ldc.i4.0
0x4d355  ldnull
0x4d356  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4d35b  ldarg.s  5
0x4d35d  brfalse.s loc_4D36F
0x4d35f  ldarg.0
0x4d360  ldstr    aGetdistinctval// "GetDistinctValuesImportFileRequest"
0x4d365  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4d36a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4d36f  ldarg.3
0x4d370  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4d375  stloc.1
0x4d376  ldloc.1
0x4d377  brfalse.s loc_4D3B4
0x4d379  ldarg.0
0x4d37a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4d37f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4d384  ldnull
0x4d385  ldc.i4.0
0x4d386  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4d38b  ldc.i4.0
0x4d38c  stloc.2
0x4d38d  br.s     loc_4D3A8
0x4d38f  ldarg.0
0x4d390  ldstr    aOptionalparame// "OptionalParameter"
0x4d395  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4d39a  ldloc.1
0x4d39b  ldloc.2
0x4d39c  ldelem.ref
0x4d39d  ldc.i4.1
0x4d39e  ldc.i4.0
0x4d39f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4d3a4  ldloc.2
0x4d3a5  ldc.i4.1
0x4d3a6  add
0x4d3a7  stloc.2
0x4d3a8  ldloc.2
0x4d3a9  ldloc.1
0x4d3aa  ldlen
0x4d3ab  conv.i4
0x4d3ac  blt.s    loc_4D38F
0x4d3ae  ldarg.0
0x4d3af  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4d3b4  ldarg.0
0x4d3b5  ldstr    aImportfileid_0// "ImportFileId"
0x4d3ba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4d3bf  ldarg.3
0x4d3c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetDistinctValuesImportFileRequest::get_ImportFileId()
0x4d3c5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4d3ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4d3cf  ldarg.0
0x4d3d0  ldstr    aColumnnumber// "columnNumber"
0x4d3d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4d3da  ldarg.3
0x4d3db  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetDistinctValuesImportFileRequest::get_columnNumber()
0x4d3e0  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4d3e5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4d3ea  ldarg.0
0x4d3eb  ldstr    aPagenumber_0// "pageNumber"
0x4d3f0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4d3f5  ldarg.3
0x4d3f6  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetDistinctValuesImportFileRequest::get_pageNumber()
0x4d3fb  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4d400  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4d405  ldarg.0
0x4d406  ldstr    aRecordsperpage// "recordsPerPage"
0x4d40b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4d410  ldarg.3
0x4d411  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GetDistinctValuesImportFileRequest::get_recordsPerPage()
0x4d416  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x4d41b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4d420  ldarg.0
0x4d421  ldarg.3
0x4d422  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4d427  ret
```
