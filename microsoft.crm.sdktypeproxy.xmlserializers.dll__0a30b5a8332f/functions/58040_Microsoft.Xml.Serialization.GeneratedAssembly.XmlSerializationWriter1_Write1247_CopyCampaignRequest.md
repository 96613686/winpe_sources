# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1247_CopyCampaignRequest

- ea: `0x58040`
- end: `0x58112`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1247_CopyCampaignRequest`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x58040`

## string_xrefs

- `0x58085`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5809f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x580b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x580da`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x580f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x58080`: `CopyCampaignRequest`
- `0x580f0`: `SaveAsTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x58040  ldarg.3
0x58041  brtrue.s loc_58050
0x58043  ldarg.s  4
0x58045  brfalse.s loc_5804F
0x58047  ldarg.0
0x58048  ldarg.1
0x58049  ldarg.2
0x5804a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5804f  ret
0x58050  ldarg.s  5
0x58052  brtrue.s loc_58070
0x58054  ldarg.3
0x58055  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5805a  stloc.0
0x5805b  ldloc.0
0x5805c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CopyCampaignRequest
0x58061  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x58066  beq.s    loc_58070
0x58068  ldarg.0
0x58069  ldarg.3
0x5806a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x5806f  throw
0x58070  ldarg.0
0x58071  ldarg.1
0x58072  ldarg.2
0x58073  ldarg.3
0x58074  ldc.i4.0
0x58075  ldnull
0x58076  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x5807b  ldarg.s  5
0x5807d  brfalse.s loc_5808F
0x5807f  ldarg.0
0x58080  ldstr    aCopycampaignre// "CopyCampaignRequest"
0x58085  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5808a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x5808f  ldarg.3
0x58090  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x58095  stloc.1
0x58096  ldloc.1
0x58097  brfalse.s loc_580D4
0x58099  ldarg.0
0x5809a  ldstr    aOptionalparame_0// "OptionalParameters"
0x5809f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x580a4  ldnull
0x580a5  ldc.i4.0
0x580a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x580ab  ldc.i4.0
0x580ac  stloc.2
0x580ad  br.s     loc_580C8
0x580af  ldarg.0
0x580b0  ldstr    aOptionalparame// "OptionalParameter"
0x580b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x580ba  ldloc.1
0x580bb  ldloc.2
0x580bc  ldelem.ref
0x580bd  ldc.i4.1
0x580be  ldc.i4.0
0x580bf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x580c4  ldloc.2
0x580c5  ldc.i4.1
0x580c6  add
0x580c7  stloc.2
0x580c8  ldloc.2
0x580c9  ldloc.1
0x580ca  ldlen
0x580cb  conv.i4
0x580cc  blt.s    loc_580AF
0x580ce  ldarg.0
0x580cf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x580d4  ldarg.0
0x580d5  ldstr    aBasecampaign// "BaseCampaign"
0x580da  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x580df  ldarg.3
0x580e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CopyCampaignRequest::get_BaseCampaign()
0x580e5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x580ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x580ef  ldarg.0
0x580f0  ldstr    aSaveastemplate// "SaveAsTemplate"
0x580f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x580fa  ldarg.3
0x580fb  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.CopyCampaignRequest::get_SaveAsTemplate()
0x58100  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x58105  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5810a  ldarg.0
0x5810b  ldarg.3
0x5810c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x58111  ret
```
