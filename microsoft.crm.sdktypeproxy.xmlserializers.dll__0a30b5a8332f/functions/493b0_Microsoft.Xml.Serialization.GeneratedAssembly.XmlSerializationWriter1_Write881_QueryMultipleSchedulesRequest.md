# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write881_QueryMultipleSchedulesRequest

- ea: `0x493b0`
- end: `0x49524`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write881_QueryMultipleSchedulesRequest`
- size: `372`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x5c90`
- `0x5cf0`
- `0x2fdf0`
- `0x493b0`

## string_xrefs

- `0x493f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4940f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49425`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49454`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4946b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x494a0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x494b8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x494dc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x494f3`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x493b0  ldarg.3
0x493b1  brtrue.s loc_493C0
0x493b3  ldarg.s  4
0x493b5  brfalse.s loc_493BF
0x493b7  ldarg.0
0x493b8  ldarg.1
0x493b9  ldarg.2
0x493ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x493bf  ret
0x493c0  ldarg.s  5
0x493c2  brtrue.s loc_493E0
0x493c4  ldarg.3
0x493c5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x493ca  stloc.0
0x493cb  ldloc.0
0x493cc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryMultipleSchedulesRequest
0x493d1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x493d6  beq.s    loc_493E0
0x493d8  ldarg.0
0x493d9  ldarg.3
0x493da  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x493df  throw
0x493e0  ldarg.0
0x493e1  ldarg.1
0x493e2  ldarg.2
0x493e3  ldarg.3
0x493e4  ldc.i4.0
0x493e5  ldnull
0x493e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x493eb  ldarg.s  5
0x493ed  brfalse.s loc_493FF
0x493ef  ldarg.0
0x493f0  ldstr    aQuerymultiples// "QueryMultipleSchedulesRequest"
0x493f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x493fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x493ff  ldarg.3
0x49400  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x49405  stloc.1
0x49406  ldloc.1
0x49407  brfalse.s loc_49444
0x49409  ldarg.0
0x4940a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4940f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49414  ldnull
0x49415  ldc.i4.0
0x49416  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4941b  ldc.i4.0
0x4941c  stloc.2
0x4941d  br.s     loc_49438
0x4941f  ldarg.0
0x49420  ldstr    aOptionalparame// "OptionalParameter"
0x49425  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4942a  ldloc.1
0x4942b  ldloc.2
0x4942c  ldelem.ref
0x4942d  ldc.i4.1
0x4942e  ldc.i4.0
0x4942f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x49434  ldloc.2
0x49435  ldc.i4.1
0x49436  add
0x49437  stloc.2
0x49438  ldloc.2
0x49439  ldloc.1
0x4943a  ldlen
0x4943b  conv.i4
0x4943c  blt.s    loc_4941F
0x4943e  ldarg.0
0x4943f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x49444  ldarg.3
0x49445  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryMultipleSchedulesRequest::get_ResourceIds()
0x4944a  stloc.3
0x4944b  ldloc.3
0x4944c  brfalse.s loc_4949A
0x4944e  ldarg.0
0x4944f  ldstr    aResourceids// "ResourceIds"
0x49454  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49459  ldnull
0x4945a  ldc.i4.0
0x4945b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x49460  ldc.i4.0
0x49461  stloc.s  4
0x49463  br.s     loc_4948D
0x49465  ldarg.0
0x49466  ldstr    aGuid// "guid"
0x4946b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49470  ldloc.3
0x49471  ldloc.s  4
0x49473  ldelema  [mscorlib]System.Guid
0x49478  ldobj    [mscorlib]System.Guid
0x4947d  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x49482  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x49487  ldloc.s  4
0x49489  ldc.i4.1
0x4948a  add
0x4948b  stloc.s  4
0x4948d  ldloc.s  4
0x4948f  ldloc.3
0x49490  ldlen
0x49491  conv.i4
0x49492  blt.s    loc_49465
0x49494  ldarg.0
0x49495  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4949a  ldarg.0
0x4949b  ldstr    aStart// "Start"
0x494a0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x494a5  ldarg.3
0x494a6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryMultipleSchedulesRequest::get_Start()
0x494ab  ldc.i4.0
0x494ac  ldc.i4.0
0x494ad  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x494b2  ldarg.0
0x494b3  ldstr    aEnd// "End"
0x494b8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x494bd  ldarg.3
0x494be  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryMultipleSchedulesRequest::get_End()
0x494c3  ldc.i4.0
0x494c4  ldc.i4.0
0x494c5  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x494ca  ldarg.3
0x494cb  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeCode[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryMultipleSchedulesRequest::get_TimeCodes()
0x494d0  stloc.s  5
0x494d2  ldloc.s  5
0x494d4  brfalse.s loc_4951C
0x494d6  ldarg.0
0x494d7  ldstr    aTimecodes// "TimeCodes"
0x494dc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x494e1  ldnull
0x494e2  ldc.i4.0
0x494e3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x494e8  ldc.i4.0
0x494e9  stloc.s  6
0x494eb  br.s     loc_4950E
0x494ed  ldarg.0
0x494ee  ldstr    aTimecode// "TimeCode"
0x494f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x494f8  ldarg.0
0x494f9  ldloc.s  5
0x494fb  ldloc.s  6
0x494fd  ldelem.i4
0x494fe  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write879_TimeCode(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeCode v)
0x49503  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x49508  ldloc.s  6
0x4950a  ldc.i4.1
0x4950b  add
0x4950c  stloc.s  6
0x4950e  ldloc.s  6
0x49510  ldloc.s  5
0x49512  ldlen
0x49513  conv.i4
0x49514  blt.s    loc_494ED
0x49516  ldarg.0
0x49517  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4951c  ldarg.0
0x4951d  ldarg.3
0x4951e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x49523  ret
```
