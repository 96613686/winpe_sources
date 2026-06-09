# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write880_QueryScheduleRequest

- ea: `0x49270`
- end: `0x493a5`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write880_QueryScheduleRequest`
- size: `309`
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
- `0x49270`

## string_xrefs

- `0x492b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x492cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x492e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4930a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49325`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4933d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4935f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49376`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x49270  ldarg.3
0x49271  brtrue.s loc_49280
0x49273  ldarg.s  4
0x49275  brfalse.s loc_4927F
0x49277  ldarg.0
0x49278  ldarg.1
0x49279  ldarg.2
0x4927a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4927f  ret
0x49280  ldarg.s  5
0x49282  brtrue.s loc_492A0
0x49284  ldarg.3
0x49285  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4928a  stloc.0
0x4928b  ldloc.0
0x4928c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest
0x49291  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x49296  beq.s    loc_492A0
0x49298  ldarg.0
0x49299  ldarg.3
0x4929a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4929f  throw
0x492a0  ldarg.0
0x492a1  ldarg.1
0x492a2  ldarg.2
0x492a3  ldarg.3
0x492a4  ldc.i4.0
0x492a5  ldnull
0x492a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x492ab  ldarg.s  5
0x492ad  brfalse.s loc_492BF
0x492af  ldarg.0
0x492b0  ldstr    aQueryscheduler// "QueryScheduleRequest"
0x492b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x492ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x492bf  ldarg.3
0x492c0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x492c5  stloc.1
0x492c6  ldloc.1
0x492c7  brfalse.s loc_49304
0x492c9  ldarg.0
0x492ca  ldstr    aOptionalparame_0// "OptionalParameters"
0x492cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x492d4  ldnull
0x492d5  ldc.i4.0
0x492d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x492db  ldc.i4.0
0x492dc  stloc.2
0x492dd  br.s     loc_492F8
0x492df  ldarg.0
0x492e0  ldstr    aOptionalparame// "OptionalParameter"
0x492e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x492ea  ldloc.1
0x492eb  ldloc.2
0x492ec  ldelem.ref
0x492ed  ldc.i4.1
0x492ee  ldc.i4.0
0x492ef  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x492f4  ldloc.2
0x492f5  ldc.i4.1
0x492f6  add
0x492f7  stloc.2
0x492f8  ldloc.2
0x492f9  ldloc.1
0x492fa  ldlen
0x492fb  conv.i4
0x492fc  blt.s    loc_492DF
0x492fe  ldarg.0
0x492ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x49304  ldarg.0
0x49305  ldstr    aResourceid// "ResourceId"
0x4930a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4930f  ldarg.3
0x49310  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::get_ResourceId()
0x49315  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4931a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4931f  ldarg.0
0x49320  ldstr    aStart// "Start"
0x49325  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4932a  ldarg.3
0x4932b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::get_Start()
0x49330  ldc.i4.0
0x49331  ldc.i4.0
0x49332  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x49337  ldarg.0
0x49338  ldstr    aEnd// "End"
0x4933d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49342  ldarg.3
0x49343  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::get_End()
0x49348  ldc.i4.0
0x49349  ldc.i4.0
0x4934a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x4934f  ldarg.3
0x49350  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeCode[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QueryScheduleRequest::get_TimeCodes()
0x49355  stloc.3
0x49356  ldloc.3
0x49357  brfalse.s loc_4939D
0x49359  ldarg.0
0x4935a  ldstr    aTimecodes// "TimeCodes"
0x4935f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49364  ldnull
0x49365  ldc.i4.0
0x49366  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4936b  ldc.i4.0
0x4936c  stloc.s  4
0x4936e  br.s     loc_49390
0x49370  ldarg.0
0x49371  ldstr    aTimecode// "TimeCode"
0x49376  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4937b  ldarg.0
0x4937c  ldloc.3
0x4937d  ldloc.s  4
0x4937f  ldelem.i4
0x49380  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write879_TimeCode(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TimeCode v)
0x49385  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x4938a  ldloc.s  4
0x4938c  ldc.i4.1
0x4938d  add
0x4938e  stloc.s  4
0x49390  ldloc.s  4
0x49392  ldloc.3
0x49393  ldlen
0x49394  conv.i4
0x49395  blt.s    loc_49370
0x49397  ldarg.0
0x49398  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4939d  ldarg.0
0x4939e  ldarg.3
0x4939f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x493a4  ret
```
