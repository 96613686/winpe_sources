# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write361_import

- ea: `0x26950`
- end: `0x26b0b`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write361_import`
- size: `443`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37320`
- `0x567b0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x26950`
- `0x26b10`

## string_xrefs

- `0x26995`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x269a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x269bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x269d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x269eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26a03`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26a1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26a33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26a4b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26a63`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26a79`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26a91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26aa9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ac1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26ad9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x26af1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x269a0`: `createdby`
- `0x269b8`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x26950  ldarg.3
0x26951  brtrue.s loc_26960
0x26953  ldarg.s  4
0x26955  brfalse.s loc_2695F
0x26957  ldarg.0
0x26958  ldarg.1
0x26959  ldarg.2
0x2695a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2695f  ret
0x26960  ldarg.s  5
0x26962  brtrue.s loc_26980
0x26964  ldarg.3
0x26965  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2696a  stloc.0
0x2696b  ldloc.0
0x2696c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import
0x26971  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x26976  beq.s    loc_26980
0x26978  ldarg.0
0x26979  ldarg.3
0x2697a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2697f  throw
0x26980  ldarg.0
0x26981  ldarg.1
0x26982  ldarg.2
0x26983  ldarg.3
0x26984  ldc.i4.0
0x26985  ldnull
0x26986  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2698b  ldarg.s  5
0x2698d  brfalse.s loc_2699F
0x2698f  ldarg.0
0x26990  ldstr    aImport// "import"
0x26995  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2699a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2699f  ldarg.0
0x269a0  ldstr    aCreatedby// "createdby"
0x269a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x269aa  ldarg.3
0x269ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_createdby()
0x269b0  ldc.i4.0
0x269b1  ldc.i4.0
0x269b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x269b7  ldarg.0
0x269b8  ldstr    aCreatedon// "createdon"
0x269bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x269c2  ldarg.3
0x269c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_createdon()
0x269c8  ldc.i4.0
0x269c9  ldc.i4.0
0x269ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x269cf  ldarg.0
0x269d0  ldstr    aEmailaddress// "emailaddress"
0x269d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x269da  ldarg.3
0x269db  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_emailaddress()
0x269e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x269e5  ldarg.0
0x269e6  ldstr    aImportid// "importid"
0x269eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x269f0  ldarg.3
0x269f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_importid()
0x269f6  ldc.i4.0
0x269f7  ldc.i4.0
0x269f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x269fd  ldarg.0
0x269fe  ldstr    aIsimport// "isimport"
0x26a03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26a08  ldarg.3
0x26a09  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_isimport()
0x26a0e  ldc.i4.0
0x26a0f  ldc.i4.0
0x26a10  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x26a15  ldarg.0
0x26a16  ldstr    aModecode// "modecode"
0x26a1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26a20  ldarg.3
0x26a21  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_modecode()
0x26a26  ldc.i4.0
0x26a27  ldc.i4.0
0x26a28  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x26a2d  ldarg.0
0x26a2e  ldstr    aModifiedby// "modifiedby"
0x26a33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26a38  ldarg.3
0x26a39  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_modifiedby()
0x26a3e  ldc.i4.0
0x26a3f  ldc.i4.0
0x26a40  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26a45  ldarg.0
0x26a46  ldstr    aModifiedon// "modifiedon"
0x26a4b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26a50  ldarg.3
0x26a51  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_modifiedon()
0x26a56  ldc.i4.0
0x26a57  ldc.i4.0
0x26a58  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x26a5d  ldarg.0
0x26a5e  ldstr    aName// "name"
0x26a63  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26a68  ldarg.3
0x26a69  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_name()
0x26a6e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x26a73  ldarg.0
0x26a74  ldstr    aOwnerid// "ownerid"
0x26a79  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26a7e  ldarg.3
0x26a7f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_ownerid()
0x26a84  ldc.i4.0
0x26a85  ldc.i4.0
0x26a86  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x26a8b  ldarg.0
0x26a8c  ldstr    aOwningbusiness// "owningbusinessunit"
0x26a91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26a96  ldarg.3
0x26a97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_owningbusinessunit()
0x26a9c  ldc.i4.0
0x26a9d  ldc.i4.0
0x26a9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x26aa3  ldarg.0
0x26aa4  ldstr    aSendnotificati// "sendnotification"
0x26aa9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26aae  ldarg.3
0x26aaf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_sendnotification()
0x26ab4  ldc.i4.0
0x26ab5  ldc.i4.0
0x26ab6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x26abb  ldarg.0
0x26abc  ldstr    aSequence// "sequence"
0x26ac1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26ac6  ldarg.3
0x26ac7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_sequence()
0x26acc  ldc.i4.0
0x26acd  ldc.i4.0
0x26ace  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x26ad3  ldarg.0
0x26ad4  ldstr    aStatecode// "statecode"
0x26ad9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26ade  ldarg.3
0x26adf  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_statecode()
0x26ae4  ldc.i4.0
0x26ae5  ldc.i4.0
0x26ae6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write360_ImportStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ImportStateInfo o, bool isNullable, bool needType)
0x26aeb  ldarg.0
0x26aec  ldstr    aStatuscode// "statuscode"
0x26af1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x26af6  ldarg.3
0x26af7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.import::get_statuscode()
0x26afc  ldc.i4.0
0x26afd  ldc.i4.0
0x26afe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x26b03  ldarg.0
0x26b04  ldarg.3
0x26b05  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x26b0a  ret
```
