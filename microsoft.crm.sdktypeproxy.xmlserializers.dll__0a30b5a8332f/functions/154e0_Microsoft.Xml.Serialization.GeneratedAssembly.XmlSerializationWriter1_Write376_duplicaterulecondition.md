# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write376_duplicaterulecondition

- ea: `0x154e0`
- end: `0x15653`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write376_duplicaterulecondition`
- size: `371`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x19ce0`
- `0x375c0`
- `0x56a50`
- `0x58850`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x154e0`

## string_xrefs

- `0x15525`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x15535`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1554b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x15563`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1557b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x15593`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x155a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x155c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x155d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x155f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x15609`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x15621`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x15639`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x15546`: `createdby`
- `0x1555e`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x154e0  ldarg.3
0x154e1  brtrue.s loc_154F0
0x154e3  ldarg.s  4
0x154e5  brfalse.s loc_154EF
0x154e7  ldarg.0
0x154e8  ldarg.1
0x154e9  ldarg.2
0x154ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x154ef  ret
0x154f0  ldarg.s  5
0x154f2  brtrue.s loc_15510
0x154f4  ldarg.3
0x154f5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x154fa  stloc.0
0x154fb  ldloc.0
0x154fc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition
0x15501  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15506  beq.s    loc_15510
0x15508  ldarg.0
0x15509  ldarg.3
0x1550a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1550f  throw
0x15510  ldarg.0
0x15511  ldarg.1
0x15512  ldarg.2
0x15513  ldarg.3
0x15514  ldc.i4.0
0x15515  ldnull
0x15516  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1551b  ldarg.s  5
0x1551d  brfalse.s loc_1552F
0x1551f  ldarg.0
0x15520  ldstr    aDuplicaterulec// "duplicaterulecondition"
0x15525  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1552a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1552f  ldarg.0
0x15530  ldstr    aBaseattributen// "baseattributename"
0x15535  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1553a  ldarg.3
0x1553b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_baseattributename()
0x15540  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x15545  ldarg.0
0x15546  ldstr    aCreatedby// "createdby"
0x1554b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x15550  ldarg.3
0x15551  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_createdby()
0x15556  ldc.i4.0
0x15557  ldc.i4.0
0x15558  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1555d  ldarg.0
0x1555e  ldstr    aCreatedon// "createdon"
0x15563  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x15568  ldarg.3
0x15569  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_createdon()
0x1556e  ldc.i4.0
0x1556f  ldc.i4.0
0x15570  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x15575  ldarg.0
0x15576  ldstr    aDuplicaterulec_0// "duplicateruleconditionid"
0x1557b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x15580  ldarg.3
0x15581  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_duplicateruleconditionid()
0x15586  ldc.i4.0
0x15587  ldc.i4.0
0x15588  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1558d  ldarg.0
0x1558e  ldstr    aMatchingattrib// "matchingattributename"
0x15593  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x15598  ldarg.3
0x15599  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_matchingattributename()
0x1559e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x155a3  ldarg.0
0x155a4  ldstr    aModifiedby// "modifiedby"
0x155a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x155ae  ldarg.3
0x155af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_modifiedby()
0x155b4  ldc.i4.0
0x155b5  ldc.i4.0
0x155b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x155bb  ldarg.0
0x155bc  ldstr    aModifiedon// "modifiedon"
0x155c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x155c6  ldarg.3
0x155c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_modifiedon()
0x155cc  ldc.i4.0
0x155cd  ldc.i4.0
0x155ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x155d3  ldarg.0
0x155d4  ldstr    aOperatorcode// "operatorcode"
0x155d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x155de  ldarg.3
0x155df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_operatorcode()
0x155e4  ldc.i4.0
0x155e5  ldc.i4.0
0x155e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x155eb  ldarg.0
0x155ec  ldstr    aOperatorparam// "operatorparam"
0x155f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x155f6  ldarg.3
0x155f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_operatorparam()
0x155fc  ldc.i4.0
0x155fd  ldc.i4.0
0x155fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x15603  ldarg.0
0x15604  ldstr    aOwningbusiness// "owningbusinessunit"
0x15609  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1560e  ldarg.3
0x1560f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_owningbusinessunit()
0x15614  ldc.i4.0
0x15615  ldc.i4.0
0x15616  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1561b  ldarg.0
0x1561c  ldstr    aOwninguser// "owninguser"
0x15621  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x15626  ldarg.3
0x15627  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_owninguser()
0x1562c  ldc.i4.0
0x1562d  ldc.i4.0
0x1562e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x15633  ldarg.0
0x15634  ldstr    aRegardingobjec// "regardingobjectid"
0x15639  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1563e  ldarg.3
0x1563f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.duplicaterulecondition::get_regardingobjectid()
0x15644  ldc.i4.0
0x15645  ldc.i4.0
0x15646  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1564b  ldarg.0
0x1564c  ldarg.3
0x1564d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x15652  ret
```
