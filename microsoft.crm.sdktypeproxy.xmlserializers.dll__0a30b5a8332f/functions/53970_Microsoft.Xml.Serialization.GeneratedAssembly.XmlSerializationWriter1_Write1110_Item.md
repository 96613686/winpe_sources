# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1110_Item

- ea: `0x53970`
- end: `0x53a3d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1110_Item`
- size: `205`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x53970`

## string_xrefs

- `0x539b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x539cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x539e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53a0a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x53a20`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x539b0`: `CreateWorkflowFromTemplateRequest`
- `0x53a1b`: `WorkflowTemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x53970  ldarg.3
0x53971  brtrue.s loc_53980
0x53973  ldarg.s  4
0x53975  brfalse.s loc_5397F
0x53977  ldarg.0
0x53978  ldarg.1
0x53979  ldarg.2
0x5397a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5397f  ret
0x53980  ldarg.s  5
0x53982  brtrue.s loc_539A0
0x53984  ldarg.3
0x53985  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5398a  stloc.0
0x5398b  ldloc.0
0x5398c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWorkflowFromTemplateRequest
0x53991  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53996  beq.s    loc_539A0
0x53998  ldarg.0
0x53999  ldarg.3
0x5399a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x5399f  throw
0x539a0  ldarg.0
0x539a1  ldarg.1
0x539a2  ldarg.2
0x539a3  ldarg.3
0x539a4  ldc.i4.0
0x539a5  ldnull
0x539a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x539ab  ldarg.s  5
0x539ad  brfalse.s loc_539BF
0x539af  ldarg.0
0x539b0  ldstr    aCreateworkflow// "CreateWorkflowFromTemplateRequest"
0x539b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x539ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x539bf  ldarg.3
0x539c0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x539c5  stloc.1
0x539c6  ldloc.1
0x539c7  brfalse.s loc_53A04
0x539c9  ldarg.0
0x539ca  ldstr    aOptionalparame_0// "OptionalParameters"
0x539cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x539d4  ldnull
0x539d5  ldc.i4.0
0x539d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x539db  ldc.i4.0
0x539dc  stloc.2
0x539dd  br.s     loc_539F8
0x539df  ldarg.0
0x539e0  ldstr    aOptionalparame// "OptionalParameter"
0x539e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x539ea  ldloc.1
0x539eb  ldloc.2
0x539ec  ldelem.ref
0x539ed  ldc.i4.1
0x539ee  ldc.i4.0
0x539ef  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x539f4  ldloc.2
0x539f5  ldc.i4.1
0x539f6  add
0x539f7  stloc.2
0x539f8  ldloc.2
0x539f9  ldloc.1
0x539fa  ldlen
0x539fb  conv.i4
0x539fc  blt.s    loc_539DF
0x539fe  ldarg.0
0x539ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x53a04  ldarg.0
0x53a05  ldstr    aWorkflowname// "WorkflowName"
0x53a0a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53a0f  ldarg.3
0x53a10  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWorkflowFromTemplateRequest::get_WorkflowName()
0x53a15  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x53a1a  ldarg.0
0x53a1b  ldstr    aWorkflowtempla// "WorkflowTemplateId"
0x53a20  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x53a25  ldarg.3
0x53a26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CreateWorkflowFromTemplateRequest::get_WorkflowTemplateId()
0x53a2b  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x53a30  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x53a35  ldarg.0
0x53a36  ldarg.3
0x53a37  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x53a3c  ret
```
