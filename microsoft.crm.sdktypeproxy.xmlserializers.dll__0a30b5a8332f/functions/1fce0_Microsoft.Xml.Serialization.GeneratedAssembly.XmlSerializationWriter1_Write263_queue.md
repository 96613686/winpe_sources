# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write263_queue

- ea: `0x1fce0`
- end: `0x1ff25`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write263_queue`
- size: `581`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36590`
- `0x55940`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x1fce0`

## string_xrefs

- `0x1fd25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fd35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fd4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fd65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fd7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fd95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fdab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fdc1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fdd7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fded`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fe05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fe1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fe35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fe4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fe65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fe7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fe93`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1feab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fec3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fedb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fef3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ff0b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1fd60`: `createdby`
- `0x1fd78`: `createdon`
- `0x1fe00`: `incomingemaildeliverymethod`
- `0x1fe18`: `incomingemailfilteringmethod`

## pseudocode

```c

```

## disassembly

```asm
0x1fce0  ldarg.3
0x1fce1  brtrue.s loc_1FCF0
0x1fce3  ldarg.s  4
0x1fce5  brfalse.s loc_1FCEF
0x1fce7  ldarg.0
0x1fce8  ldarg.1
0x1fce9  ldarg.2
0x1fcea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1fcef  ret
0x1fcf0  ldarg.s  5
0x1fcf2  brtrue.s loc_1FD10
0x1fcf4  ldarg.3
0x1fcf5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1fcfa  stloc.0
0x1fcfb  ldloc.0
0x1fcfc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue
0x1fd01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fd06  beq.s    loc_1FD10
0x1fd08  ldarg.0
0x1fd09  ldarg.3
0x1fd0a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1fd0f  throw
0x1fd10  ldarg.0
0x1fd11  ldarg.1
0x1fd12  ldarg.2
0x1fd13  ldarg.3
0x1fd14  ldc.i4.0
0x1fd15  ldnull
0x1fd16  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1fd1b  ldarg.s  5
0x1fd1d  brfalse.s loc_1FD2F
0x1fd1f  ldarg.0
0x1fd20  ldstr    aQueue// "queue"
0x1fd25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fd2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1fd2f  ldarg.0
0x1fd30  ldstr    aAllowemailcred// "allowemailcredentials"
0x1fd35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fd3a  ldarg.3
0x1fd3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_allowemailcredentials()
0x1fd40  ldc.i4.0
0x1fd41  ldc.i4.0
0x1fd42  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1fd47  ldarg.0
0x1fd48  ldstr    aBusinessunitid// "businessunitid"
0x1fd4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fd52  ldarg.3
0x1fd53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_businessunitid()
0x1fd58  ldc.i4.0
0x1fd59  ldc.i4.0
0x1fd5a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1fd5f  ldarg.0
0x1fd60  ldstr    aCreatedby// "createdby"
0x1fd65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fd6a  ldarg.3
0x1fd6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_createdby()
0x1fd70  ldc.i4.0
0x1fd71  ldc.i4.0
0x1fd72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1fd77  ldarg.0
0x1fd78  ldstr    aCreatedon// "createdon"
0x1fd7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fd82  ldarg.3
0x1fd83  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_createdon()
0x1fd88  ldc.i4.0
0x1fd89  ldc.i4.0
0x1fd8a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1fd8f  ldarg.0
0x1fd90  ldstr    aDescription_0// "description"
0x1fd95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fd9a  ldarg.3
0x1fd9b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_description()
0x1fda0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1fda5  ldarg.0
0x1fda6  ldstr    aEmailaddress// "emailaddress"
0x1fdab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fdb0  ldarg.3
0x1fdb1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_emailaddress()
0x1fdb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1fdbb  ldarg.0
0x1fdbc  ldstr    aEmailpassword// "emailpassword"
0x1fdc1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fdc6  ldarg.3
0x1fdc7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_emailpassword()
0x1fdcc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1fdd1  ldarg.0
0x1fdd2  ldstr    aEmailusername// "emailusername"
0x1fdd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fddc  ldarg.3
0x1fddd  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_emailusername()
0x1fde2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1fde7  ldarg.0
0x1fde8  ldstr    aIgnoreunsolici// "ignoreunsolicitedemail"
0x1fded  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fdf2  ldarg.3
0x1fdf3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_ignoreunsolicitedemail()
0x1fdf8  ldc.i4.0
0x1fdf9  ldc.i4.0
0x1fdfa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1fdff  ldarg.0
0x1fe00  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x1fe05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fe0a  ldarg.3
0x1fe0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_incomingemaildeliverymethod()
0x1fe10  ldc.i4.0
0x1fe11  ldc.i4.0
0x1fe12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1fe17  ldarg.0
0x1fe18  ldstr    aIncomingemailf// "incomingemailfilteringmethod"
0x1fe1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fe22  ldarg.3
0x1fe23  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_incomingemailfilteringmethod()
0x1fe28  ldc.i4.0
0x1fe29  ldc.i4.0
0x1fe2a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1fe2f  ldarg.0
0x1fe30  ldstr    aIsfaxqueue// "isfaxqueue"
0x1fe35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fe3a  ldarg.3
0x1fe3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_isfaxqueue()
0x1fe40  ldc.i4.0
0x1fe41  ldc.i4.0
0x1fe42  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1fe47  ldarg.0
0x1fe48  ldstr    aModifiedby// "modifiedby"
0x1fe4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fe52  ldarg.3
0x1fe53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_modifiedby()
0x1fe58  ldc.i4.0
0x1fe59  ldc.i4.0
0x1fe5a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1fe5f  ldarg.0
0x1fe60  ldstr    aModifiedon// "modifiedon"
0x1fe65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fe6a  ldarg.3
0x1fe6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_modifiedon()
0x1fe70  ldc.i4.0
0x1fe71  ldc.i4.0
0x1fe72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1fe77  ldarg.0
0x1fe78  ldstr    aName// "name"
0x1fe7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fe82  ldarg.3
0x1fe83  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_name()
0x1fe88  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1fe8d  ldarg.0
0x1fe8e  ldstr    aOrganizationid// "organizationid"
0x1fe93  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fe98  ldarg.3
0x1fe99  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_organizationid()
0x1fe9e  ldc.i4.0
0x1fe9f  ldc.i4.0
0x1fea0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1fea5  ldarg.0
0x1fea6  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x1feab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1feb0  ldarg.3
0x1feb1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_outgoingemaildeliverymethod()
0x1feb6  ldc.i4.0
0x1feb7  ldc.i4.0
0x1feb8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1febd  ldarg.0
0x1febe  ldstr    aPrimaryuserid// "primaryuserid"
0x1fec3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fec8  ldarg.3
0x1fec9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_primaryuserid()
0x1fece  ldc.i4.0
0x1fecf  ldc.i4.0
0x1fed0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1fed5  ldarg.0
0x1fed6  ldstr    aQueueid// "queueid"
0x1fedb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fee0  ldarg.3
0x1fee1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_queueid()
0x1fee6  ldc.i4.0
0x1fee7  ldc.i4.0
0x1fee8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1feed  ldarg.0
0x1feee  ldstr    aQueuesemantics// "queuesemantics"
0x1fef3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1fef8  ldarg.3
0x1fef9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_queuesemantics()
0x1fefe  ldc.i4.0
0x1feff  ldc.i4.0
0x1ff00  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1ff05  ldarg.0
0x1ff06  ldstr    aQueuetypecode// "queuetypecode"
0x1ff0b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ff10  ldarg.3
0x1ff11  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.queue::get_queuetypecode()
0x1ff16  ldc.i4.0
0x1ff17  ldc.i4.0
0x1ff18  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1ff1d  ldarg.0
0x1ff1e  ldarg.3
0x1ff1f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1ff24  ret
```
