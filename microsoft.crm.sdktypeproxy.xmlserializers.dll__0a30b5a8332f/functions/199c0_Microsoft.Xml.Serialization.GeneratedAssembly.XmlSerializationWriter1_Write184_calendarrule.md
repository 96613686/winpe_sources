# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write184_calendarrule

- ea: `0x199c0`
- end: `0x19cdf`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write184_calendarrule`
- size: `799`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x19ce0`
- `0x1aab0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x165c0`
- `0x199c0`

## string_xrefs

- `0x19a05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19a15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19a2d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19a45`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19a5d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19a75`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19a8d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19aa3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19abb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19ad3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19aeb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19b03`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19b1b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19b33`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19b49`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19b61`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19b79`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19b91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19ba9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19bc1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19bd9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19bf1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19c07`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19c1f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19c37`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19c4d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19c65`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19c7d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19c95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19cad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19cc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19a58`: `createdby`
- `0x19a70`: `createdon`
- `0x19c60`: `serviceid`

## pseudocode

```c

```

## disassembly

```asm
0x199c0  ldarg.3
0x199c1  brtrue.s loc_199D0
0x199c3  ldarg.s  4
0x199c5  brfalse.s loc_199CF
0x199c7  ldarg.0
0x199c8  ldarg.1
0x199c9  ldarg.2
0x199ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x199cf  ret
0x199d0  ldarg.s  5
0x199d2  brtrue.s loc_199F0
0x199d4  ldarg.3
0x199d5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x199da  stloc.0
0x199db  ldloc.0
0x199dc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule
0x199e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x199e6  beq.s    loc_199F0
0x199e8  ldarg.0
0x199e9  ldarg.3
0x199ea  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x199ef  throw
0x199f0  ldarg.0
0x199f1  ldarg.1
0x199f2  ldarg.2
0x199f3  ldarg.3
0x199f4  ldc.i4.0
0x199f5  ldnull
0x199f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x199fb  ldarg.s  5
0x199fd  brfalse.s loc_19A0F
0x199ff  ldarg.0
0x19a00  ldstr    aCalendarrule// "calendarrule"
0x19a05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19a0a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x19a0f  ldarg.0
0x19a10  ldstr    aBusinessunitid// "businessunitid"
0x19a15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19a1a  ldarg.3
0x19a1b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_businessunitid()
0x19a20  ldc.i4.0
0x19a21  ldc.i4.0
0x19a22  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x19a27  ldarg.0
0x19a28  ldstr    aCalendarid_0// "calendarid"
0x19a2d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19a32  ldarg.3
0x19a33  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_calendarid()
0x19a38  ldc.i4.0
0x19a39  ldc.i4.0
0x19a3a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x19a3f  ldarg.0
0x19a40  ldstr    aCalendarruleid// "calendarruleid"
0x19a45  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19a4a  ldarg.3
0x19a4b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_calendarruleid()
0x19a50  ldc.i4.0
0x19a51  ldc.i4.0
0x19a52  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x19a57  ldarg.0
0x19a58  ldstr    aCreatedby// "createdby"
0x19a5d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19a62  ldarg.3
0x19a63  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_createdby()
0x19a68  ldc.i4.0
0x19a69  ldc.i4.0
0x19a6a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x19a6f  ldarg.0
0x19a70  ldstr    aCreatedon// "createdon"
0x19a75  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19a7a  ldarg.3
0x19a7b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_createdon()
0x19a80  ldc.i4.0
0x19a81  ldc.i4.0
0x19a82  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x19a87  ldarg.0
0x19a88  ldstr    aDescription_0// "description"
0x19a8d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19a92  ldarg.3
0x19a93  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_description()
0x19a98  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x19a9d  ldarg.0
0x19a9e  ldstr    aDuration// "duration"
0x19aa3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19aa8  ldarg.3
0x19aa9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_duration()
0x19aae  ldc.i4.0
0x19aaf  ldc.i4.0
0x19ab0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x19ab5  ldarg.0
0x19ab6  ldstr    aEffectiveinter// "effectiveintervalend"
0x19abb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19ac0  ldarg.3
0x19ac1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_effectiveintervalend()
0x19ac6  ldc.i4.0
0x19ac7  ldc.i4.0
0x19ac8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x19acd  ldarg.0
0x19ace  ldstr    aEffectiveinter_0// "effectiveintervalstart"
0x19ad3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19ad8  ldarg.3
0x19ad9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_effectiveintervalstart()
0x19ade  ldc.i4.0
0x19adf  ldc.i4.0
0x19ae0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x19ae5  ldarg.0
0x19ae6  ldstr    aEffort_0// "effort"
0x19aeb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19af0  ldarg.3
0x19af1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_effort()
0x19af6  ldc.i4.0
0x19af7  ldc.i4.0
0x19af8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x19afd  ldarg.0
0x19afe  ldstr    aEndtime// "endtime"
0x19b03  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19b08  ldarg.3
0x19b09  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_endtime()
0x19b0e  ldc.i4.0
0x19b0f  ldc.i4.0
0x19b10  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x19b15  ldarg.0
0x19b16  ldstr    aExtentcode// "extentcode"
0x19b1b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19b20  ldarg.3
0x19b21  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_extentcode()
0x19b26  ldc.i4.0
0x19b27  ldc.i4.0
0x19b28  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x19b2d  ldarg.0
0x19b2e  ldstr    aGroupdesignato// "groupdesignator"
0x19b33  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19b38  ldarg.3
0x19b39  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_groupdesignator()
0x19b3e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x19b43  ldarg.0
0x19b44  ldstr    aInnercalendari// "innercalendarid"
0x19b49  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19b4e  ldarg.3
0x19b4f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_innercalendarid()
0x19b54  ldc.i4.0
0x19b55  ldc.i4.0
0x19b56  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x19b5b  ldarg.0
0x19b5c  ldstr    aIsmodified// "ismodified"
0x19b61  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19b66  ldarg.3
0x19b67  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_ismodified()
0x19b6c  ldc.i4.0
0x19b6d  ldc.i4.0
0x19b6e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x19b73  ldarg.0
0x19b74  ldstr    aIsselected// "isselected"
0x19b79  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19b7e  ldarg.3
0x19b7f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_isselected()
0x19b84  ldc.i4.0
0x19b85  ldc.i4.0
0x19b86  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x19b8b  ldarg.0
0x19b8c  ldstr    aIssimple// "issimple"
0x19b91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19b96  ldarg.3
0x19b97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_issimple()
0x19b9c  ldc.i4.0
0x19b9d  ldc.i4.0
0x19b9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x19ba3  ldarg.0
0x19ba4  ldstr    aIsvaried// "isvaried"
0x19ba9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19bae  ldarg.3
0x19baf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_isvaried()
0x19bb4  ldc.i4.0
0x19bb5  ldc.i4.0
0x19bb6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x19bbb  ldarg.0
0x19bbc  ldstr    aModifiedby// "modifiedby"
0x19bc1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19bc6  ldarg.3
0x19bc7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_modifiedby()
0x19bcc  ldc.i4.0
0x19bcd  ldc.i4.0
0x19bce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x19bd3  ldarg.0
0x19bd4  ldstr    aModifiedon// "modifiedon"
0x19bd9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19bde  ldarg.3
0x19bdf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_modifiedon()
0x19be4  ldc.i4.0
0x19be5  ldc.i4.0
0x19be6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x19beb  ldarg.0
0x19bec  ldstr    aName// "name"
0x19bf1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19bf6  ldarg.3
0x19bf7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_name()
0x19bfc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x19c01  ldarg.0
0x19c02  ldstr    aOffset// "offset"
0x19c07  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19c0c  ldarg.3
0x19c0d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_offset()
0x19c12  ldc.i4.0
0x19c13  ldc.i4.0
0x19c14  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x19c19  ldarg.0
0x19c1a  ldstr    aOrganizationid// "organizationid"
0x19c1f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19c24  ldarg.3
0x19c25  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_organizationid()
0x19c2a  ldc.i4.0
0x19c2b  ldc.i4.0
0x19c2c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x19c31  ldarg.0
0x19c32  ldstr    aPattern// "pattern"
0x19c37  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19c3c  ldarg.3
0x19c3d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_pattern()
0x19c42  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x19c47  ldarg.0
0x19c48  ldstr    aRank// "rank"
0x19c4d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19c52  ldarg.3
0x19c53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_rank()
0x19c58  ldc.i4.0
0x19c59  ldc.i4.0
0x19c5a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x19c5f  ldarg.0
0x19c60  ldstr    aServiceid// "serviceid"
0x19c65  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19c6a  ldarg.3
0x19c6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_serviceid()
0x19c70  ldc.i4.0
0x19c71  ldc.i4.0
0x19c72  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x19c77  ldarg.0
0x19c78  ldstr    aStarttime// "starttime"
0x19c7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19c82  ldarg.3
0x19c83  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_starttime()
0x19c88  ldc.i4.0
0x19c89  ldc.i4.0
0x19c8a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x19c8f  ldarg.0
0x19c90  ldstr    aSubcode_0// "subcode"
0x19c95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19c9a  ldarg.3
0x19c9b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_subcode()
0x19ca0  ldc.i4.0
0x19ca1  ldc.i4.0
0x19ca2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x19ca7  ldarg.0
0x19ca8  ldstr    aTimecode_0// "timecode"
0x19cad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19cb2  ldarg.3
0x19cb3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_timecode()
0x19cb8  ldc.i4.0
0x19cb9  ldc.i4.0
0x19cba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x19cbf  ldarg.0
0x19cc0  ldstr    aTimezonecode// "timezonecode"
0x19cc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19cca  ldarg.3
0x19ccb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.calendarrule::get_timezonecode()
0x19cd0  ldc.i4.0
0x19cd1  ldc.i4.0
0x19cd2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x19cd7  ldarg.0
0x19cd8  ldarg.3
0x19cd9  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x19cde  ret
```
