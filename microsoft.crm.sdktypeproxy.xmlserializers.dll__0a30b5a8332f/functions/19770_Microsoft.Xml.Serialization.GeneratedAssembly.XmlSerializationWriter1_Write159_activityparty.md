# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty

- ea: `0x19770`
- end: `0x19913`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty`
- size: `419`
- prototype: ``
- caller_count: `11`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x19ce0`
- `0x1c670`
- `0x20ef0`
- `0x23a80`
- `0x26f90`
- `0x27660`
- `0x2acf0`
- `0x2b280`
- `0x2caf0`

## callees

- `0x5cf0`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x165c0`
- `0x19770`

## string_xrefs

- `0x197b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x197c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x197dd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x197f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1980b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19823`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1983b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19853`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1986b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19883`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x19899`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x198b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x198c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x198e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x198f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x198dc`: `scheduledend`
- `0x198f4`: `scheduledstart`

## pseudocode

```c

```

## disassembly

```asm
0x19770  ldarg.3
0x19771  brtrue.s loc_19780
0x19773  ldarg.s  4
0x19775  brfalse.s loc_1977F
0x19777  ldarg.0
0x19778  ldarg.1
0x19779  ldarg.2
0x1977a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1977f  ret
0x19780  ldarg.s  5
0x19782  brtrue.s loc_197A0
0x19784  ldarg.3
0x19785  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1978a  stloc.0
0x1978b  ldloc.0
0x1978c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty
0x19791  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19796  beq.s    loc_197A0
0x19798  ldarg.0
0x19799  ldarg.3
0x1979a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1979f  throw
0x197a0  ldarg.0
0x197a1  ldarg.1
0x197a2  ldarg.2
0x197a3  ldarg.3
0x197a4  ldc.i4.0
0x197a5  ldnull
0x197a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x197ab  ldarg.s  5
0x197ad  brfalse.s loc_197BF
0x197af  ldarg.0
0x197b0  ldstr    aActivityparty// "activityparty"
0x197b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x197ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x197bf  ldarg.0
0x197c0  ldstr    aActivityid_0// "activityid"
0x197c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x197ca  ldarg.3
0x197cb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_activityid()
0x197d0  ldc.i4.0
0x197d1  ldc.i4.0
0x197d2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x197d7  ldarg.0
0x197d8  ldstr    aActivitypartyi// "activitypartyid"
0x197dd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x197e2  ldarg.3
0x197e3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_activitypartyid()
0x197e8  ldc.i4.0
0x197e9  ldc.i4.0
0x197ea  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x197ef  ldarg.0
0x197f0  ldstr    aAddressused// "addressused"
0x197f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x197fa  ldarg.3
0x197fb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_addressused()
0x19800  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x19805  ldarg.0
0x19806  ldstr    aDonotemail// "donotemail"
0x1980b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19810  ldarg.3
0x19811  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_donotemail()
0x19816  ldc.i4.0
0x19817  ldc.i4.0
0x19818  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1981d  ldarg.0
0x1981e  ldstr    aDonotfax// "donotfax"
0x19823  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19828  ldarg.3
0x19829  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_donotfax()
0x1982e  ldc.i4.0
0x1982f  ldc.i4.0
0x19830  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x19835  ldarg.0
0x19836  ldstr    aDonotphone// "donotphone"
0x1983b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19840  ldarg.3
0x19841  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_donotphone()
0x19846  ldc.i4.0
0x19847  ldc.i4.0
0x19848  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1984d  ldarg.0
0x1984e  ldstr    aDonotpostalmai// "donotpostalmail"
0x19853  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19858  ldarg.3
0x19859  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_donotpostalmail()
0x1985e  ldc.i4.0
0x1985f  ldc.i4.0
0x19860  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x19865  ldarg.0
0x19866  ldstr    aEffort_0// "effort"
0x1986b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19870  ldarg.3
0x19871  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_effort()
0x19876  ldc.i4.0
0x19877  ldc.i4.0
0x19878  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x1987d  ldarg.0
0x1987e  ldstr    aExchangeentryi// "exchangeentryid"
0x19883  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x19888  ldarg.3
0x19889  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_exchangeentryid()
0x1988e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x19893  ldarg.0
0x19894  ldstr    aParticipationt// "participationtypemask"
0x19899  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1989e  ldarg.3
0x1989f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_participationtypemask()
0x198a4  ldc.i4.0
0x198a5  ldc.i4.0
0x198a6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x198ab  ldarg.0
0x198ac  ldstr    aPartyid// "partyid"
0x198b1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x198b6  ldarg.3
0x198b7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_partyid()
0x198bc  ldc.i4.0
0x198bd  ldc.i4.0
0x198be  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x198c3  ldarg.0
0x198c4  ldstr    aResourcespecid_0// "resourcespecid"
0x198c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x198ce  ldarg.3
0x198cf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_resourcespecid()
0x198d4  ldc.i4.0
0x198d5  ldc.i4.0
0x198d6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x198db  ldarg.0
0x198dc  ldstr    aScheduledend// "scheduledend"
0x198e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x198e6  ldarg.3
0x198e7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_scheduledend()
0x198ec  ldc.i4.0
0x198ed  ldc.i4.0
0x198ee  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x198f3  ldarg.0
0x198f4  ldstr    aScheduledstart// "scheduledstart"
0x198f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x198fe  ldarg.3
0x198ff  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty::get_scheduledstart()
0x19904  ldc.i4.0
0x19905  ldc.i4.0
0x19906  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1990b  ldarg.0
0x1990c  ldarg.3
0x1990d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x19912  ret
```
