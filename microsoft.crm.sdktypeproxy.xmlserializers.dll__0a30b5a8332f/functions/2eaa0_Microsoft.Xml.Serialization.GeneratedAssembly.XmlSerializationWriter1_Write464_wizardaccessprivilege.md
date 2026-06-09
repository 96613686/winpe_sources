# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write464_wizardaccessprivilege

- ea: `0x2eaa0`
- end: `0x2ebcb`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write464_wizardaccessprivilege`
- size: `299`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x38350`
- `0x57850`

## callees

- `0x5cf0`
- `0x15180`
- `0x153c0`
- `0x2eaa0`

## string_xrefs

- `0x2eae5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eaf5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eb0d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eb25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eb3b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eb53`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eb6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eb83`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eb99`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2ebb1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2eaf0`: `createdby`
- `0x2eb08`: `createdon`
- `0x2eae0`: `wizardaccessprivilege`
- `0x2eb7e`: `privilegename`
- `0x2ebac`: `wizardaccessprivilegeid`

## pseudocode

```c

```

## disassembly

```asm
0x2eaa0  ldarg.3
0x2eaa1  brtrue.s loc_2EAB0
0x2eaa3  ldarg.s  4
0x2eaa5  brfalse.s loc_2EAAF
0x2eaa7  ldarg.0
0x2eaa8  ldarg.1
0x2eaa9  ldarg.2
0x2eaaa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2eaaf  ret
0x2eab0  ldarg.s  5
0x2eab2  brtrue.s loc_2EAD0
0x2eab4  ldarg.3
0x2eab5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2eaba  stloc.0
0x2eabb  ldloc.0
0x2eabc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege
0x2eac1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2eac6  beq.s    loc_2EAD0
0x2eac8  ldarg.0
0x2eac9  ldarg.3
0x2eaca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2eacf  throw
0x2ead0  ldarg.0
0x2ead1  ldarg.1
0x2ead2  ldarg.2
0x2ead3  ldarg.3
0x2ead4  ldc.i4.0
0x2ead5  ldnull
0x2ead6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2eadb  ldarg.s  5
0x2eadd  brfalse.s loc_2EAEF
0x2eadf  ldarg.0
0x2eae0  ldstr    aWizardaccesspr// "wizardaccessprivilege"
0x2eae5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eaea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2eaef  ldarg.0
0x2eaf0  ldstr    aCreatedby// "createdby"
0x2eaf5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eafa  ldarg.3
0x2eafb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_createdby()
0x2eb00  ldc.i4.0
0x2eb01  ldc.i4.0
0x2eb02  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2eb07  ldarg.0
0x2eb08  ldstr    aCreatedon// "createdon"
0x2eb0d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eb12  ldarg.3
0x2eb13  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_createdon()
0x2eb18  ldc.i4.0
0x2eb19  ldc.i4.0
0x2eb1a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2eb1f  ldarg.0
0x2eb20  ldstr    aEntityname_1// "entityname"
0x2eb25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eb2a  ldarg.3
0x2eb2b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_entityname()
0x2eb30  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2eb35  ldarg.0
0x2eb36  ldstr    aModifiedby// "modifiedby"
0x2eb3b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eb40  ldarg.3
0x2eb41  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_modifiedby()
0x2eb46  ldc.i4.0
0x2eb47  ldc.i4.0
0x2eb48  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2eb4d  ldarg.0
0x2eb4e  ldstr    aModifiedon// "modifiedon"
0x2eb53  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eb58  ldarg.3
0x2eb59  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_modifiedon()
0x2eb5e  ldc.i4.0
0x2eb5f  ldc.i4.0
0x2eb60  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2eb65  ldarg.0
0x2eb66  ldstr    aOrganizationid// "organizationid"
0x2eb6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eb70  ldarg.3
0x2eb71  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_organizationid()
0x2eb76  ldc.i4.0
0x2eb77  ldc.i4.0
0x2eb78  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2eb7d  ldarg.0
0x2eb7e  ldstr    aPrivilegename// "privilegename"
0x2eb83  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eb88  ldarg.3
0x2eb89  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_privilegename()
0x2eb8e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2eb93  ldarg.0
0x2eb94  ldstr    aWebwizardid// "webwizardid"
0x2eb99  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2eb9e  ldarg.3
0x2eb9f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_webwizardid()
0x2eba4  ldc.i4.0
0x2eba5  ldc.i4.0
0x2eba6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2ebab  ldarg.0
0x2ebac  ldstr    aWizardaccesspr_0// "wizardaccessprivilegeid"
0x2ebb1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2ebb6  ldarg.3
0x2ebb7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.wizardaccessprivilege::get_wizardaccessprivilegeid()
0x2ebbc  ldc.i4.0
0x2ebbd  ldc.i4.0
0x2ebbe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2ebc3  ldarg.0
0x2ebc4  ldarg.3
0x2ebc5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x2ebca  ret
```
