# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write185_calendar

- ea: `0x1aab0`
- end: `0x1ac50`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write185_calendar`
- size: `416`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35800`
- `0x571c0`

## callees

- `0x5cf0`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x199c0`
- `0x1aab0`

## string_xrefs

- `0x1aaf5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab7b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab93`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1abab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1abc3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1abd9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1abf1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ac13`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ac29`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1ab30`: `createdby`
- `0x1ab48`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x1aab0  ldarg.3
0x1aab1  brtrue.s loc_1AAC0
0x1aab3  ldarg.s  4
0x1aab5  brfalse.s loc_1AABF
0x1aab7  ldarg.0
0x1aab8  ldarg.1
0x1aab9  ldarg.2
0x1aaba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1aabf  ret
0x1aac0  ldarg.s  5
0x1aac2  brtrue.s loc_1AAE0
0x1aac4  ldarg.3
0x1aac5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1aaca  stloc.0
0x1aacb  ldloc.0
0x1aacc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar
0x1aad1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1aad6  beq.s    loc_1AAE0
0x1aad8  ldarg.0
0x1aad9  ldarg.3
0x1aada  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1aadf  throw
0x1aae0  ldarg.0
0x1aae1  ldarg.1
0x1aae2  ldarg.2
0x1aae3  ldarg.3
0x1aae4  ldc.i4.0
0x1aae5  ldnull
0x1aae6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1aaeb  ldarg.s  5
0x1aaed  brfalse.s loc_1AAFF
0x1aaef  ldarg.0
0x1aaf0  ldstr    aCalendar// "calendar"
0x1aaf5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1aafa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1aaff  ldarg.0
0x1ab00  ldstr    aBusinessunitid// "businessunitid"
0x1ab05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ab0a  ldarg.3
0x1ab0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_businessunitid()
0x1ab10  ldc.i4.0
0x1ab11  ldc.i4.0
0x1ab12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ab17  ldarg.0
0x1ab18  ldstr    aCalendarid_0// "calendarid"
0x1ab1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ab22  ldarg.3
0x1ab23  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_calendarid()
0x1ab28  ldc.i4.0
0x1ab29  ldc.i4.0
0x1ab2a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1ab2f  ldarg.0
0x1ab30  ldstr    aCreatedby// "createdby"
0x1ab35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ab3a  ldarg.3
0x1ab3b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_createdby()
0x1ab40  ldc.i4.0
0x1ab41  ldc.i4.0
0x1ab42  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1ab47  ldarg.0
0x1ab48  ldstr    aCreatedon// "createdon"
0x1ab4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ab52  ldarg.3
0x1ab53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_createdon()
0x1ab58  ldc.i4.0
0x1ab59  ldc.i4.0
0x1ab5a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1ab5f  ldarg.0
0x1ab60  ldstr    aDescription_0// "description"
0x1ab65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ab6a  ldarg.3
0x1ab6b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_description()
0x1ab70  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1ab75  ldarg.0
0x1ab76  ldstr    aIsshared// "isshared"
0x1ab7b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ab80  ldarg.3
0x1ab81  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_isshared()
0x1ab86  ldc.i4.0
0x1ab87  ldc.i4.0
0x1ab88  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1ab8d  ldarg.0
0x1ab8e  ldstr    aModifiedby// "modifiedby"
0x1ab93  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ab98  ldarg.3
0x1ab99  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_modifiedby()
0x1ab9e  ldc.i4.0
0x1ab9f  ldc.i4.0
0x1aba0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1aba5  ldarg.0
0x1aba6  ldstr    aModifiedon// "modifiedon"
0x1abab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1abb0  ldarg.3
0x1abb1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_modifiedon()
0x1abb6  ldc.i4.0
0x1abb7  ldc.i4.0
0x1abb8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1abbd  ldarg.0
0x1abbe  ldstr    aName// "name"
0x1abc3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1abc8  ldarg.3
0x1abc9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_name()
0x1abce  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1abd3  ldarg.0
0x1abd4  ldstr    aOrganizationid// "organizationid"
0x1abd9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1abde  ldarg.3
0x1abdf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_organizationid()
0x1abe4  ldc.i4.0
0x1abe5  ldc.i4.0
0x1abe6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1abeb  ldarg.0
0x1abec  ldstr    aPrimaryuserid// "primaryuserid"
0x1abf1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1abf6  ldarg.3
0x1abf7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_primaryuserid()
0x1abfc  ldc.i4.0
0x1abfd  ldc.i4.0
0x1abfe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1ac03  ldarg.3
0x1ac04  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendar::get_calendarrules()
0x1ac09  stloc.1
0x1ac0a  ldloc.1
0x1ac0b  brfalse.s loc_1AC48
0x1ac0d  ldarg.0
0x1ac0e  ldstr    aCalendarrules// "calendarrules"
0x1ac13  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ac18  ldnull
0x1ac19  ldc.i4.0
0x1ac1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x1ac1f  ldc.i4.0
0x1ac20  stloc.2
0x1ac21  br.s     loc_1AC3C
0x1ac23  ldarg.0
0x1ac24  ldstr    aCalendarrule// "calendarrule"
0x1ac29  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1ac2e  ldloc.1
0x1ac2f  ldloc.2
0x1ac30  ldelem.ref
0x1ac31  ldc.i4.0
0x1ac32  ldc.i4.0
0x1ac33  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write184_calendarrule(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule o, bool isNullable, bool needType)
0x1ac38  ldloc.2
0x1ac39  ldc.i4.1
0x1ac3a  add
0x1ac3b  stloc.2
0x1ac3c  ldloc.2
0x1ac3d  ldloc.1
0x1ac3e  ldlen
0x1ac3f  conv.i4
0x1ac40  blt.s    loc_1AC23
0x1ac42  ldarg.0
0x1ac43  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x1ac48  ldarg.0
0x1ac49  ldarg.3
0x1ac4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1ac4f  ret
```
