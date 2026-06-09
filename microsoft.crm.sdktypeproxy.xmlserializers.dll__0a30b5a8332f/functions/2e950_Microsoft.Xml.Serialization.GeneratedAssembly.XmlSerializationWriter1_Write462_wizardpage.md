# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write462_wizardpage

- ea: `0x2e950`
- end: `0x2ea93`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write462_wizardpage`
- size: `323`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x382e0`
- `0x577e0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x2e950`

## string_xrefs

- `0x2e995`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e9a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e9bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e9d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e9ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ea05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ea1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ea33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ea4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ea61`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ea79`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2e9a0`: `createdby`
- `0x2e9b8`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x2e950  ldarg.3
0x2e951  brtrue.s loc_2E960
0x2e953  ldarg.s  4
0x2e955  brfalse.s loc_2E95F
0x2e957  ldarg.0
0x2e958  ldarg.1
0x2e959  ldarg.2
0x2e95a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2e95f  ret
0x2e960  ldarg.s  5
0x2e962  brtrue.s loc_2E980
0x2e964  ldarg.3
0x2e965  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2e96a  stloc.0
0x2e96b  ldloc.0
0x2e96c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage
0x2e971  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2e976  beq.s    loc_2E980
0x2e978  ldarg.0
0x2e979  ldarg.3
0x2e97a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2e97f  throw
0x2e980  ldarg.0
0x2e981  ldarg.1
0x2e982  ldarg.2
0x2e983  ldarg.3
0x2e984  ldc.i4.0
0x2e985  ldnull
0x2e986  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2e98b  ldarg.s  5
0x2e98d  brfalse.s loc_2E99F
0x2e98f  ldarg.0
0x2e990  ldstr    aWizardpage// "wizardpage"
0x2e995  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e99a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2e99f  ldarg.0
0x2e9a0  ldstr    aCreatedby// "createdby"
0x2e9a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e9aa  ldarg.3
0x2e9ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_createdby()
0x2e9b0  ldc.i4.0
0x2e9b1  ldc.i4.0
0x2e9b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e9b7  ldarg.0
0x2e9b8  ldstr    aCreatedon// "createdon"
0x2e9bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e9c2  ldarg.3
0x2e9c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_createdon()
0x2e9c8  ldc.i4.0
0x2e9c9  ldc.i4.0
0x2e9ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e9cf  ldarg.0
0x2e9d0  ldstr    aModifiedby// "modifiedby"
0x2e9d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e9da  ldarg.3
0x2e9db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_modifiedby()
0x2e9e0  ldc.i4.0
0x2e9e1  ldc.i4.0
0x2e9e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2e9e7  ldarg.0
0x2e9e8  ldstr    aModifiedon// "modifiedon"
0x2e9ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2e9f2  ldarg.3
0x2e9f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_modifiedon()
0x2e9f8  ldc.i4.0
0x2e9f9  ldc.i4.0
0x2e9fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2e9ff  ldarg.0
0x2ea00  ldstr    aOrganizationid// "organizationid"
0x2ea05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ea0a  ldarg.3
0x2ea0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_organizationid()
0x2ea10  ldc.i4.0
0x2ea11  ldc.i4.0
0x2ea12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ea17  ldarg.0
0x2ea18  ldstr    aPagedatatopost// "pagedatatopost"
0x2ea1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ea22  ldarg.3
0x2ea23  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_pagedatatopost()
0x2ea28  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ea2d  ldarg.0
0x2ea2e  ldstr    aPagesequencenu// "pagesequencenumber"
0x2ea33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ea38  ldarg.3
0x2ea39  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_pagesequencenumber()
0x2ea3e  ldc.i4.0
0x2ea3f  ldc.i4.0
0x2ea40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2ea45  ldarg.0
0x2ea46  ldstr    aPageurl// "pageurl"
0x2ea4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ea50  ldarg.3
0x2ea51  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_pageurl()
0x2ea56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2ea5b  ldarg.0
0x2ea5c  ldstr    aWebwizardid// "webwizardid"
0x2ea61  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ea66  ldarg.3
0x2ea67  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_webwizardid()
0x2ea6c  ldc.i4.0
0x2ea6d  ldc.i4.0
0x2ea6e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ea73  ldarg.0
0x2ea74  ldstr    aWizardpageid// "wizardpageid"
0x2ea79  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ea7e  ldarg.3
0x2ea7f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardpage::get_wizardpageid()
0x2ea84  ldc.i4.0
0x2ea85  ldc.i4.0
0x2ea86  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2ea8b  ldarg.0
0x2ea8c  ldarg.3
0x2ea8d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2ea92  ret
```
