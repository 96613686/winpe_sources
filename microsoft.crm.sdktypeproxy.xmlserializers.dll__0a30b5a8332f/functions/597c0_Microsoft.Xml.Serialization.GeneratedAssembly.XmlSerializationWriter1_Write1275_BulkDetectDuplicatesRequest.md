# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1275_BulkDetectDuplicatesRequest

- ea: `0x597c0`
- end: `0x5999e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1275_BulkDetectDuplicatesRequest`
- size: `478`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x5cf0`
- `0x6600`
- `0x2fdf0`
- `0x597c0`

## string_xrefs

- `0x59805`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5981f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59835`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5985a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59872`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59888`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x598a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x598c8`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x598df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59920`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59937`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5996e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x59984`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5989e`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x597c0  ldarg.3
0x597c1  brtrue.s loc_597D0
0x597c3  ldarg.s  4
0x597c5  brfalse.s loc_597CF
0x597c7  ldarg.0
0x597c8  ldarg.1
0x597c9  ldarg.2
0x597ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x597cf  ret
0x597d0  ldarg.s  5
0x597d2  brtrue.s loc_597F0
0x597d4  ldarg.3
0x597d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x597da  stloc.0
0x597db  ldloc.0
0x597dc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest
0x597e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x597e6  beq.s    loc_597F0
0x597e8  ldarg.0
0x597e9  ldarg.3
0x597ea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x597ef  throw
0x597f0  ldarg.0
0x597f1  ldarg.1
0x597f2  ldarg.2
0x597f3  ldarg.3
0x597f4  ldc.i4.0
0x597f5  ldnull
0x597f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x597fb  ldarg.s  5
0x597fd  brfalse.s loc_5980F
0x597ff  ldarg.0
0x59800  ldstr    aBulkdetectdupl// "BulkDetectDuplicatesRequest"
0x59805  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5980a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x5980f  ldarg.3
0x59810  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x59815  stloc.1
0x59816  ldloc.1
0x59817  brfalse.s loc_59854
0x59819  ldarg.0
0x5981a  ldstr    aOptionalparame_0// "OptionalParameters"
0x5981f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59824  ldnull
0x59825  ldc.i4.0
0x59826  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5982b  ldc.i4.0
0x5982c  stloc.2
0x5982d  br.s     loc_59848
0x5982f  ldarg.0
0x59830  ldstr    aOptionalparame// "OptionalParameter"
0x59835  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5983a  ldloc.1
0x5983b  ldloc.2
0x5983c  ldelem.ref
0x5983d  ldc.i4.1
0x5983e  ldc.i4.0
0x5983f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x59844  ldloc.2
0x59845  ldc.i4.1
0x59846  add
0x59847  stloc.2
0x59848  ldloc.2
0x59849  ldloc.1
0x5984a  ldlen
0x5984b  conv.i4
0x5984c  blt.s    loc_5982F
0x5984e  ldarg.0
0x5984f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59854  ldarg.0
0x59855  ldstr    aQuery_0// "Query"
0x5985a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5985f  ldarg.3
0x59860  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_Query()
0x59865  ldc.i4.0
0x59866  ldc.i4.0
0x59867  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write577_QueryBase(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase o, bool isNullable, bool needType)
0x5986c  ldarg.0
0x5986d  ldstr    aJobname// "JobName"
0x59872  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59877  ldarg.3
0x59878  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_JobName()
0x5987d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x59882  ldarg.0
0x59883  ldstr    aSendemailnotif// "SendEmailNotification"
0x59888  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5988d  ldarg.3
0x5988e  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_SendEmailNotification()
0x59893  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x59898  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5989d  ldarg.0
0x5989e  ldstr    aTemplateid_0// "TemplateId"
0x598a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x598a8  ldarg.3
0x598a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_TemplateId()
0x598ae  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x598b3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x598b8  ldarg.3
0x598b9  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_ToRecipients()
0x598be  stloc.3
0x598bf  ldloc.3
0x598c0  brfalse.s loc_5990E
0x598c2  ldarg.0
0x598c3  ldstr    aTorecipients_0// "ToRecipients"
0x598c8  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x598cd  ldnull
0x598ce  ldc.i4.0
0x598cf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x598d4  ldc.i4.0
0x598d5  stloc.s  4
0x598d7  br.s     loc_59901
0x598d9  ldarg.0
0x598da  ldstr    aGuid// "guid"
0x598df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x598e4  ldloc.3
0x598e5  ldloc.s  4
0x598e7  ldelema  [mscorlib]System.Guid
0x598ec  ldobj    [mscorlib]System.Guid
0x598f1  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x598f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x598fb  ldloc.s  4
0x598fd  ldc.i4.1
0x598fe  add
0x598ff  stloc.s  4
0x59901  ldloc.s  4
0x59903  ldloc.3
0x59904  ldlen
0x59905  conv.i4
0x59906  blt.s    loc_598D9
0x59908  ldarg.0
0x59909  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x5990e  ldarg.3
0x5990f  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_CCRecipients()
0x59914  stloc.s  5
0x59916  ldloc.s  5
0x59918  brfalse.s loc_59968
0x5991a  ldarg.0
0x5991b  ldstr    aCcrecipients// "CCRecipients"
0x59920  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59925  ldnull
0x59926  ldc.i4.0
0x59927  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5992c  ldc.i4.0
0x5992d  stloc.s  6
0x5992f  br.s     loc_5995A
0x59931  ldarg.0
0x59932  ldstr    aGuid// "guid"
0x59937  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5993c  ldloc.s  5
0x5993e  ldloc.s  6
0x59940  ldelema  [mscorlib]System.Guid
0x59945  ldobj    [mscorlib]System.Guid
0x5994a  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x5994f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x59954  ldloc.s  6
0x59956  ldc.i4.1
0x59957  add
0x59958  stloc.s  6
0x5995a  ldloc.s  6
0x5995c  ldloc.s  5
0x5995e  ldlen
0x5995f  conv.i4
0x59960  blt.s    loc_59931
0x59962  ldarg.0
0x59963  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x59968  ldarg.0
0x59969  ldstr    aRecurrencepatt_0// "RecurrencePattern"
0x5996e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59973  ldarg.3
0x59974  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_RecurrencePattern()
0x59979  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5997e  ldarg.0
0x5997f  ldstr    aRecurrencestar_0// "RecurrenceStartTime"
0x59984  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x59989  ldarg.3
0x5998a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.BulkDetectDuplicatesRequest::get_RecurrenceStartTime()
0x5998f  ldc.i4.0
0x59990  ldc.i4.0
0x59991  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x59996  ldarg.0
0x59997  ldarg.3
0x59998  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x5999d  ret
```
