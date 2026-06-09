# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write446_activitymimeattachment

- ea: `0x2d3a0`
- end: `0x2d4af`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write446_activitymimeattachment`
- size: `271`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x38040`
- `0x575b0`

## callees

- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x2d3a0`

## string_xrefs

- `0x2d3e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d3f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d40d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d425`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d43d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d453`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d469`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d481`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2d497`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x2d3a0  ldarg.3
0x2d3a1  brtrue.s loc_2D3B0
0x2d3a3  ldarg.s  4
0x2d3a5  brfalse.s loc_2D3AF
0x2d3a7  ldarg.0
0x2d3a8  ldarg.1
0x2d3a9  ldarg.2
0x2d3aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2d3af  ret
0x2d3b0  ldarg.s  5
0x2d3b2  brtrue.s loc_2D3D0
0x2d3b4  ldarg.3
0x2d3b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2d3ba  stloc.0
0x2d3bb  ldloc.0
0x2d3bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment
0x2d3c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2d3c6  beq.s    loc_2D3D0
0x2d3c8  ldarg.0
0x2d3c9  ldarg.3
0x2d3ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2d3cf  throw
0x2d3d0  ldarg.0
0x2d3d1  ldarg.1
0x2d3d2  ldarg.2
0x2d3d3  ldarg.3
0x2d3d4  ldc.i4.0
0x2d3d5  ldnull
0x2d3d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2d3db  ldarg.s  5
0x2d3dd  brfalse.s loc_2D3EF
0x2d3df  ldarg.0
0x2d3e0  ldstr    aActivitymimeat// "activitymimeattachment"
0x2d3e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d3ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2d3ef  ldarg.0
0x2d3f0  ldstr    aActivityid_0// "activityid"
0x2d3f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d3fa  ldarg.3
0x2d3fb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_activityid()
0x2d400  ldc.i4.0
0x2d401  ldc.i4.0
0x2d402  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2d407  ldarg.0
0x2d408  ldstr    aActivitymimeat_0// "activitymimeattachmentid"
0x2d40d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d412  ldarg.3
0x2d413  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_activitymimeattachmentid()
0x2d418  ldc.i4.0
0x2d419  ldc.i4.0
0x2d41a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2d41f  ldarg.0
0x2d420  ldstr    aAttachmentnumb// "attachmentnumber"
0x2d425  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d42a  ldarg.3
0x2d42b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_attachmentnumber()
0x2d430  ldc.i4.0
0x2d431  ldc.i4.0
0x2d432  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2d437  ldarg.0
0x2d438  ldstr    aBody// "body"
0x2d43d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d442  ldarg.3
0x2d443  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_body()
0x2d448  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d44d  ldarg.0
0x2d44e  ldstr    aFilename// "filename"
0x2d453  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d458  ldarg.3
0x2d459  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_filename()
0x2d45e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d463  ldarg.0
0x2d464  ldstr    aFilesize// "filesize"
0x2d469  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d46e  ldarg.3
0x2d46f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_filesize()
0x2d474  ldc.i4.0
0x2d475  ldc.i4.0
0x2d476  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2d47b  ldarg.0
0x2d47c  ldstr    aMimetype// "mimetype"
0x2d481  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d486  ldarg.3
0x2d487  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_mimetype()
0x2d48c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d491  ldarg.0
0x2d492  ldstr    aSubject// "subject"
0x2d497  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2d49c  ldarg.3
0x2d49d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activitymimeattachment::get_subject()
0x2d4a2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2d4a7  ldarg.0
0x2d4a8  ldarg.3
0x2d4a9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2d4ae  ret
```
