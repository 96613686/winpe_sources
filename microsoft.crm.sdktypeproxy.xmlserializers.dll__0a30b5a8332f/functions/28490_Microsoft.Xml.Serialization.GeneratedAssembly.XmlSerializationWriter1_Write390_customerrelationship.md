# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write390_customerrelationship

- ea: `0x28490`
- end: `0x28663`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write390_customerrelationship`
- size: `467`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x377f0`
- `0x56c10`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x153c0`
- `0x16a10`
- `0x170c0`
- `0x28490`

## string_xrefs

- `0x284d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x284e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x284fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28515`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2852d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28545`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2855d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28573`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2858b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x285a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x285bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x285d3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x285eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28603`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2861b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28633`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28649`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x284f8`: `createdby`
- `0x28510`: `createdon`
- `0x285ce`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x28490  ldarg.3
0x28491  brtrue.s loc_284A0
0x28493  ldarg.s  4
0x28495  brfalse.s loc_2849F
0x28497  ldarg.0
0x28498  ldarg.1
0x28499  ldarg.2
0x2849a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2849f  ret
0x284a0  ldarg.s  5
0x284a2  brtrue.s loc_284C0
0x284a4  ldarg.3
0x284a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x284aa  stloc.0
0x284ab  ldloc.0
0x284ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship
0x284b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x284b6  beq.s    loc_284C0
0x284b8  ldarg.0
0x284b9  ldarg.3
0x284ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x284bf  throw
0x284c0  ldarg.0
0x284c1  ldarg.1
0x284c2  ldarg.2
0x284c3  ldarg.3
0x284c4  ldc.i4.0
0x284c5  ldnull
0x284c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x284cb  ldarg.s  5
0x284cd  brfalse.s loc_284DF
0x284cf  ldarg.0
0x284d0  ldstr    aCustomerrelati// "customerrelationship"
0x284d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x284da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x284df  ldarg.0
0x284e0  ldstr    aConverserelati// "converserelationshipid"
0x284e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x284ea  ldarg.3
0x284eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_converserelationshipid()
0x284f0  ldc.i4.0
0x284f1  ldc.i4.0
0x284f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x284f7  ldarg.0
0x284f8  ldstr    aCreatedby// "createdby"
0x284fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28502  ldarg.3
0x28503  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_createdby()
0x28508  ldc.i4.0
0x28509  ldc.i4.0
0x2850a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2850f  ldarg.0
0x28510  ldstr    aCreatedon// "createdon"
0x28515  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2851a  ldarg.3
0x2851b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_createdon()
0x28520  ldc.i4.0
0x28521  ldc.i4.0
0x28522  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28527  ldarg.0
0x28528  ldstr    aCustomerid// "customerid"
0x2852d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28532  ldarg.3
0x28533  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_customerid()
0x28538  ldc.i4.0
0x28539  ldc.i4.0
0x2853a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x2853f  ldarg.0
0x28540  ldstr    aCustomerrelati_0// "customerrelationshipid"
0x28545  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2854a  ldarg.3
0x2854b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_customerrelationshipid()
0x28550  ldc.i4.0
0x28551  ldc.i4.0
0x28552  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x28557  ldarg.0
0x28558  ldstr    aCustomerrolede// "customerroledescription"
0x2855d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28562  ldarg.3
0x28563  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_customerroledescription()
0x28568  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2856d  ldarg.0
0x2856e  ldstr    aCustomerroleid// "customerroleid"
0x28573  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28578  ldarg.3
0x28579  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_customerroleid()
0x2857e  ldc.i4.0
0x2857f  ldc.i4.0
0x28580  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28585  ldarg.0
0x28586  ldstr    aImportsequence// "importsequencenumber"
0x2858b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28590  ldarg.3
0x28591  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_importsequencenumber()
0x28596  ldc.i4.0
0x28597  ldc.i4.0
0x28598  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2859d  ldarg.0
0x2859e  ldstr    aModifiedby// "modifiedby"
0x285a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x285a8  ldarg.3
0x285a9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_modifiedby()
0x285ae  ldc.i4.0
0x285af  ldc.i4.0
0x285b0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x285b5  ldarg.0
0x285b6  ldstr    aModifiedon// "modifiedon"
0x285bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x285c0  ldarg.3
0x285c1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_modifiedon()
0x285c6  ldc.i4.0
0x285c7  ldc.i4.0
0x285c8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x285cd  ldarg.0
0x285ce  ldstr    aOverriddencrea// "overriddencreatedon"
0x285d3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x285d8  ldarg.3
0x285d9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_overriddencreatedon()
0x285de  ldc.i4.0
0x285df  ldc.i4.0
0x285e0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x285e5  ldarg.0
0x285e6  ldstr    aOwnerid// "ownerid"
0x285eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x285f0  ldarg.3
0x285f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_ownerid()
0x285f6  ldc.i4.0
0x285f7  ldc.i4.0
0x285f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x285fd  ldarg.0
0x285fe  ldstr    aOwningbusiness// "owningbusinessunit"
0x28603  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28608  ldarg.3
0x28609  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_owningbusinessunit()
0x2860e  ldc.i4.0
0x2860f  ldc.i4.0
0x28610  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28615  ldarg.0
0x28616  ldstr    aPartnerid// "partnerid"
0x2861b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28620  ldarg.3
0x28621  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_partnerid()
0x28626  ldc.i4.0
0x28627  ldc.i4.0
0x28628  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x2862d  ldarg.0
0x2862e  ldstr    aPartnerroledes// "partnerroledescription"
0x28633  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28638  ldarg.3
0x28639  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_partnerroledescription()
0x2863e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28643  ldarg.0
0x28644  ldstr    aPartnerroleid// "partnerroleid"
0x28649  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2864e  ldarg.3
0x2864f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customerrelationship::get_partnerroleid()
0x28654  ldc.i4.0
0x28655  ldc.i4.0
0x28656  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2865b  ldarg.0
0x2865c  ldarg.3
0x2865d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x28662  ret
```
