# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write382_displaystring

- ea: `0x27ee0`
- end: `0x2804f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write382_displaystring`
- size: `367`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x376a0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x27ee0`

## string_xrefs

- `0x27f25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27f35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27f4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27f65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27f7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27f91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27fa9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27fbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27fd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27fef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28007`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2801f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28037`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x27f30`: `createdby`
- `0x27f48`: `createdon`
- `0x27f60`: `customcomment`

## pseudocode

```c

```

## disassembly

```asm
0x27ee0  ldarg.3
0x27ee1  brtrue.s loc_27EF0
0x27ee3  ldarg.s  4
0x27ee5  brfalse.s loc_27EEF
0x27ee7  ldarg.0
0x27ee8  ldarg.1
0x27ee9  ldarg.2
0x27eea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x27eef  ret
0x27ef0  ldarg.s  5
0x27ef2  brtrue.s loc_27F10
0x27ef4  ldarg.3
0x27ef5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x27efa  stloc.0
0x27efb  ldloc.0
0x27efc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring
0x27f01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x27f06  beq.s    loc_27F10
0x27f08  ldarg.0
0x27f09  ldarg.3
0x27f0a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x27f0f  throw
0x27f10  ldarg.0
0x27f11  ldarg.1
0x27f12  ldarg.2
0x27f13  ldarg.3
0x27f14  ldc.i4.0
0x27f15  ldnull
0x27f16  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x27f1b  ldarg.s  5
0x27f1d  brfalse.s loc_27F2F
0x27f1f  ldarg.0
0x27f20  ldstr    aDisplaystring// "displaystring"
0x27f25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27f2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x27f2f  ldarg.0
0x27f30  ldstr    aCreatedby// "createdby"
0x27f35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27f3a  ldarg.3
0x27f3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_createdby()
0x27f40  ldc.i4.0
0x27f41  ldc.i4.0
0x27f42  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x27f47  ldarg.0
0x27f48  ldstr    aCreatedon// "createdon"
0x27f4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27f52  ldarg.3
0x27f53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_createdon()
0x27f58  ldc.i4.0
0x27f59  ldc.i4.0
0x27f5a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x27f5f  ldarg.0
0x27f60  ldstr    aCustomcomment// "customcomment"
0x27f65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27f6a  ldarg.3
0x27f6b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_customcomment()
0x27f70  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27f75  ldarg.0
0x27f76  ldstr    aCustomdisplays// "customdisplaystring"
0x27f7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27f80  ldarg.3
0x27f81  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_customdisplaystring()
0x27f86  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27f8b  ldarg.0
0x27f8c  ldstr    aDisplaystringi// "displaystringid"
0x27f91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27f96  ldarg.3
0x27f97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_displaystringid()
0x27f9c  ldc.i4.0
0x27f9d  ldc.i4.0
0x27f9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x27fa3  ldarg.0
0x27fa4  ldstr    aDisplaystringk// "displaystringkey"
0x27fa9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27fae  ldarg.3
0x27faf  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_displaystringkey()
0x27fb4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x27fb9  ldarg.0
0x27fba  ldstr    aFormatparamete// "formatparameters"
0x27fbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27fc4  ldarg.3
0x27fc5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_formatparameters()
0x27fca  ldc.i4.0
0x27fcb  ldc.i4.0
0x27fcc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27fd1  ldarg.0
0x27fd2  ldstr    aLanguagecode_0// "languagecode"
0x27fd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27fdc  ldarg.3
0x27fdd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_languagecode()
0x27fe2  ldc.i4.0
0x27fe3  ldc.i4.0
0x27fe4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x27fe9  ldarg.0
0x27fea  ldstr    aModifiedby// "modifiedby"
0x27fef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x27ff4  ldarg.3
0x27ff5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_modifiedby()
0x27ffa  ldc.i4.0
0x27ffb  ldc.i4.0
0x27ffc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28001  ldarg.0
0x28002  ldstr    aModifiedon// "modifiedon"
0x28007  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2800c  ldarg.3
0x2800d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_modifiedon()
0x28012  ldc.i4.0
0x28013  ldc.i4.0
0x28014  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28019  ldarg.0
0x2801a  ldstr    aOrganizationid// "organizationid"
0x2801f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28024  ldarg.3
0x28025  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_organizationid()
0x2802a  ldc.i4.0
0x2802b  ldc.i4.0
0x2802c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28031  ldarg.0
0x28032  ldstr    aPublisheddispl// "publisheddisplaystring"
0x28037  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2803c  ldarg.3
0x2803d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.displaystring::get_publisheddisplaystring()
0x28042  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28047  ldarg.0
0x28048  ldarg.3
0x28049  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2804e  ret
```
