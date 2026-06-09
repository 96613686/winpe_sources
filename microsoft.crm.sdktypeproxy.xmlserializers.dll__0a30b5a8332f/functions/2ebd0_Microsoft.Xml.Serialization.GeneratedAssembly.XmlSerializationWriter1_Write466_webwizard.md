# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write466_webwizard

- ea: `0x2ebd0`
- end: `0x2ed59`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write466_webwizard`
- size: `393`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x383c0`
- `0x578c0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x2ebd0`

## string_xrefs

- `0x2ec15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ec25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ec3b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ec53`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ec6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ec83`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ec9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ecb3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ecc9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ece1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ecf9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ed0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ed27`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ed3f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ec36`: `createdby`
- `0x2ec4e`: `createdon`
- `0x2ec20`: `accessprivileges`

## pseudocode

```c

```

## disassembly

```asm
0x2ebd0  ldarg.3
0x2ebd1  brtrue.s loc_2EBE0
0x2ebd3  ldarg.s  4
0x2ebd5  brfalse.s loc_2EBDF
0x2ebd7  ldarg.0
0x2ebd8  ldarg.1
0x2ebd9  ldarg.2
0x2ebda  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2ebdf  ret
0x2ebe0  ldarg.s  5
0x2ebe2  brtrue.s loc_2EC00
0x2ebe4  ldarg.3
0x2ebe5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2ebea  stloc.0
0x2ebeb  ldloc.0
0x2ebec  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard
0x2ebf1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ebf6  beq.s    loc_2EC00
0x2ebf8  ldarg.0
0x2ebf9  ldarg.3
0x2ebfa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2ebff  throw
0x2ec00  ldarg.0
0x2ec01  ldarg.1
0x2ec02  ldarg.2
0x2ec03  ldarg.3
0x2ec04  ldc.i4.0
0x2ec05  ldnull
0x2ec06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2ec0b  ldarg.s  5
0x2ec0d  brfalse.s loc_2EC1F
0x2ec0f  ldarg.0
0x2ec10  ldstr    aWebwizard// "webwizard"
0x2ec15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ec1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2ec1f  ldarg.0
0x2ec20  ldstr    aAccessprivileg// "accessprivileges"
0x2ec25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ec2a  ldarg.3
0x2ec2b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_accessprivileges()
0x2ec30  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ec35  ldarg.0
0x2ec36  ldstr    aCreatedby// "createdby"
0x2ec3b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ec40  ldarg.3
0x2ec41  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_createdby()
0x2ec46  ldc.i4.0
0x2ec47  ldc.i4.0
0x2ec48  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ec4d  ldarg.0
0x2ec4e  ldstr    aCreatedon// "createdon"
0x2ec53  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ec58  ldarg.3
0x2ec59  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_createdon()
0x2ec5e  ldc.i4.0
0x2ec5f  ldc.i4.0
0x2ec60  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ec65  ldarg.0
0x2ec66  ldstr    aIsstaticpagese// "isstaticpagesequence"
0x2ec6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ec70  ldarg.3
0x2ec71  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_isstaticpagesequence()
0x2ec76  ldc.i4.0
0x2ec77  ldc.i4.0
0x2ec78  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2ec7d  ldarg.0
0x2ec7e  ldstr    aModifiedby// "modifiedby"
0x2ec83  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ec88  ldarg.3
0x2ec89  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_modifiedby()
0x2ec8e  ldc.i4.0
0x2ec8f  ldc.i4.0
0x2ec90  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ec95  ldarg.0
0x2ec96  ldstr    aModifiedon// "modifiedon"
0x2ec9b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eca0  ldarg.3
0x2eca1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_modifiedon()
0x2eca6  ldc.i4.0
0x2eca7  ldc.i4.0
0x2eca8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2ecad  ldarg.0
0x2ecae  ldstr    aName// "name"
0x2ecb3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ecb8  ldarg.3
0x2ecb9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_name()
0x2ecbe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ecc3  ldarg.0
0x2ecc4  ldstr    aOrganizationid// "organizationid"
0x2ecc9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ecce  ldarg.3
0x2eccf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_organizationid()
0x2ecd4  ldc.i4.0
0x2ecd5  ldc.i4.0
0x2ecd6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ecdb  ldarg.0
0x2ecdc  ldstr    aStartpageseque// "startpagesequencenumber"
0x2ece1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ece6  ldarg.3
0x2ece7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_startpagesequencenumber()
0x2ecec  ldc.i4.0
0x2eced  ldc.i4.0
0x2ecee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2ecf3  ldarg.0
0x2ecf4  ldstr    aTitleresources// "titleresourcestring"
0x2ecf9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ecfe  ldarg.3
0x2ecff  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_titleresourcestring()
0x2ed04  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ed09  ldarg.0
0x2ed0a  ldstr    aWebwizardid// "webwizardid"
0x2ed0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ed14  ldarg.3
0x2ed15  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_webwizardid()
0x2ed1a  ldc.i4.0
0x2ed1b  ldc.i4.0
0x2ed1c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2ed21  ldarg.0
0x2ed22  ldstr    aWizardpageheig// "wizardpageheight"
0x2ed27  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ed2c  ldarg.3
0x2ed2d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_wizardpageheight()
0x2ed32  ldc.i4.0
0x2ed33  ldc.i4.0
0x2ed34  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2ed39  ldarg.0
0x2ed3a  ldstr    aWizardpagewidt// "wizardpagewidth"
0x2ed3f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ed44  ldarg.3
0x2ed45  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.webwizard::get_wizardpagewidth()
0x2ed4a  ldc.i4.0
0x2ed4b  ldc.i4.0
0x2ed4c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2ed51  ldarg.0
0x2ed52  ldarg.3
0x2ed53  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2ed58  ret
```
