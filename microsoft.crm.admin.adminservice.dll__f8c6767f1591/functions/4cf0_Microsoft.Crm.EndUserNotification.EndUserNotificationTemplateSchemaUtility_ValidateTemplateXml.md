# Microsoft.Crm.EndUserNotification.EndUserNotificationTemplateSchemaUtility::ValidateTemplateXml

- ea: `0x4cf0`
- end: `0x4d6a`
- name: `Microsoft.Crm.EndUserNotification.EndUserNotificationTemplateSchemaUtility::ValidateTemplateXml`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7300`
- `0x73a0`

## callees

- `0x4ce0`
- `0x4cf0`
- `0x4da0`

## string_xrefs

- `0x4d07`: `TemplateXml: `
- `0x4d32`: `EndUserNotificationTemplate/EmailContent/Subject`
- `0x4d5e`: `TemplateXml: "Subject" can not have a new line character.`

## pseudocode

```c

```

## disassembly

```asm
0x4cf0  ldarg.0
0x4cf1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4cf6  brtrue.s loc_4D69
0x4cf8  newobj   instance void Microsoft.Crm.EndUserNotification.EndUserNotificationTemplateSchemaUtility::.ctor()
0x4cfd  ldarg.0
0x4cfe  call     instance string Microsoft.Crm.EndUserNotification.EndUserNotificationTemplateSchemaUtility::ValidateSchema(string endUserNotificationTemplateXml)
0x4d03  stloc.0
0x4d04  leave.s  loc_4D1D
0x4d06  stloc.2
0x4d07  ldstr    aTemplatexml// "TemplateXml: "
0x4d0c  ldloc.2
0x4d0d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4d12  call     string [mscorlib]System.String::Concat(string, string)
0x4d17  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4d1c  throw
0x4d1d  ldloc.0
0x4d1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d23  brtrue.s loc_4D2C
0x4d25  ldloc.0
0x4d26  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4d2b  throw
0x4d2c  ldarg.0
0x4d2d  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4d32  ldstr    aEndusernotific// "EndUserNotificationTemplate/EmailConten"...
0x4d37  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4d3c  stloc.1
0x4d3d  ldloc.1
0x4d3e  brfalse.s loc_4D69
0x4d40  ldloc.1
0x4d41  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4d46  ldc.i4.2
0x4d47  newarr   [mscorlib]System.Char
0x4d4c  dup
0x4d4d  ldc.i4.0
0x4d4e  ldc.i4.s 0xA
0x4d50  stelem.i2
0x4d51  dup
0x4d52  ldc.i4.1
0x4d53  ldc.i4.s 0xD
0x4d55  stelem.i2
0x4d56  callvirt instance int32 [mscorlib]System.String::IndexOfAny(char[])
0x4d5b  ldc.i4.0
0x4d5c  blt.s    loc_4D69
0x4d5e  ldstr    aTemplatexmlSub// "TemplateXml: \"Subject\" can not have a"...
0x4d63  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x4d68  throw
0x4d69  ret
```
