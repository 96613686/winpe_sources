# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write203_uom

- ea: `0x1bfd0`
- end: `0x1c15d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write203_uom`
- size: `397`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35b10`
- `0x57a10`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x15430`
- `0x1bfd0`

## string_xrefs

- `0x1c015`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c025`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c03d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c055`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c06d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c085`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c09d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c0b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c0cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c0e3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c0fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c113`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c12b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c143`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c038`: `createdby`
- `0x1c050`: `createdon`
- `0x1c0f6`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x1bfd0  ldarg.3
0x1bfd1  brtrue.s loc_1BFE0
0x1bfd3  ldarg.s  4
0x1bfd5  brfalse.s loc_1BFDF
0x1bfd7  ldarg.0
0x1bfd8  ldarg.1
0x1bfd9  ldarg.2
0x1bfda  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1bfdf  ret
0x1bfe0  ldarg.s  5
0x1bfe2  brtrue.s loc_1C000
0x1bfe4  ldarg.3
0x1bfe5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1bfea  stloc.0
0x1bfeb  ldloc.0
0x1bfec  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom
0x1bff1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bff6  beq.s    loc_1C000
0x1bff8  ldarg.0
0x1bff9  ldarg.3
0x1bffa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1bfff  throw
0x1c000  ldarg.0
0x1c001  ldarg.1
0x1c002  ldarg.2
0x1c003  ldarg.3
0x1c004  ldc.i4.0
0x1c005  ldnull
0x1c006  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1c00b  ldarg.s  5
0x1c00d  brfalse.s loc_1C01F
0x1c00f  ldarg.0
0x1c010  ldstr    aUom// "uom"
0x1c015  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c01a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1c01f  ldarg.0
0x1c020  ldstr    aBaseuom// "baseuom"
0x1c025  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c02a  ldarg.3
0x1c02b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_baseuom()
0x1c030  ldc.i4.0
0x1c031  ldc.i4.0
0x1c032  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c037  ldarg.0
0x1c038  ldstr    aCreatedby// "createdby"
0x1c03d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c042  ldarg.3
0x1c043  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_createdby()
0x1c048  ldc.i4.0
0x1c049  ldc.i4.0
0x1c04a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c04f  ldarg.0
0x1c050  ldstr    aCreatedon// "createdon"
0x1c055  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c05a  ldarg.3
0x1c05b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_createdon()
0x1c060  ldc.i4.0
0x1c061  ldc.i4.0
0x1c062  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c067  ldarg.0
0x1c068  ldstr    aImportsequence// "importsequencenumber"
0x1c06d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c072  ldarg.3
0x1c073  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_importsequencenumber()
0x1c078  ldc.i4.0
0x1c079  ldc.i4.0
0x1c07a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1c07f  ldarg.0
0x1c080  ldstr    aIsschedulebase// "isschedulebaseuom"
0x1c085  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c08a  ldarg.3
0x1c08b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_isschedulebaseuom()
0x1c090  ldc.i4.0
0x1c091  ldc.i4.0
0x1c092  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x1c097  ldarg.0
0x1c098  ldstr    aModifiedby// "modifiedby"
0x1c09d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c0a2  ldarg.3
0x1c0a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_modifiedby()
0x1c0a8  ldc.i4.0
0x1c0a9  ldc.i4.0
0x1c0aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c0af  ldarg.0
0x1c0b0  ldstr    aModifiedon// "modifiedon"
0x1c0b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c0ba  ldarg.3
0x1c0bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_modifiedon()
0x1c0c0  ldc.i4.0
0x1c0c1  ldc.i4.0
0x1c0c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c0c7  ldarg.0
0x1c0c8  ldstr    aName// "name"
0x1c0cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c0d2  ldarg.3
0x1c0d3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_name()
0x1c0d8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c0dd  ldarg.0
0x1c0de  ldstr    aOrganizationid// "organizationid"
0x1c0e3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c0e8  ldarg.3
0x1c0e9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_organizationid()
0x1c0ee  ldc.i4.0
0x1c0ef  ldc.i4.0
0x1c0f0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x1c0f5  ldarg.0
0x1c0f6  ldstr    aOverriddencrea// "overriddencreatedon"
0x1c0fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c100  ldarg.3
0x1c101  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_overriddencreatedon()
0x1c106  ldc.i4.0
0x1c107  ldc.i4.0
0x1c108  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x1c10d  ldarg.0
0x1c10e  ldstr    aQuantity// "quantity"
0x1c113  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c118  ldarg.3
0x1c119  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_quantity()
0x1c11e  ldc.i4.0
0x1c11f  ldc.i4.0
0x1c120  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x1c125  ldarg.0
0x1c126  ldstr    aUomid// "uomid"
0x1c12b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c130  ldarg.3
0x1c131  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_uomid()
0x1c136  ldc.i4.0
0x1c137  ldc.i4.0
0x1c138  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1c13d  ldarg.0
0x1c13e  ldstr    aUomscheduleid// "uomscheduleid"
0x1c143  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c148  ldarg.3
0x1c149  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.uom::get_uomscheduleid()
0x1c14e  ldc.i4.0
0x1c14f  ldc.i4.0
0x1c150  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x1c155  ldarg.0
0x1c156  ldarg.3
0x1c157  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x1c15c  ret
```
