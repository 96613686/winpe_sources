# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write386_discounttype

- ea: `0x28050`
- end: `0x281f3`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write386_discounttype`
- size: `419`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x37710`
- `0x57690`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x153c0`
- `0x16cb0`
- `0x28050`
- `0x28200`

## string_xrefs

- `0x28095`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x280a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x280bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x280d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x280eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28103`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2811b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28133`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2814b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28163`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28179`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28191`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x281a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x281c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x281d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x280a0`: `createdby`
- `0x280b8`: `createdon`
- `0x2818c`: `overriddencreatedon`
- `0x28116`: `isamounttype`

## pseudocode

```c

```

## disassembly

```asm
0x28050  ldarg.3
0x28051  brtrue.s loc_28060
0x28053  ldarg.s  4
0x28055  brfalse.s loc_2805F
0x28057  ldarg.0
0x28058  ldarg.1
0x28059  ldarg.2
0x2805a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2805f  ret
0x28060  ldarg.s  5
0x28062  brtrue.s loc_28080
0x28064  ldarg.3
0x28065  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2806a  stloc.0
0x2806b  ldloc.0
0x2806c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype
0x28071  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28076  beq.s    loc_28080
0x28078  ldarg.0
0x28079  ldarg.3
0x2807a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2807f  throw
0x28080  ldarg.0
0x28081  ldarg.1
0x28082  ldarg.2
0x28083  ldarg.3
0x28084  ldc.i4.0
0x28085  ldnull
0x28086  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2808b  ldarg.s  5
0x2808d  brfalse.s loc_2809F
0x2808f  ldarg.0
0x28090  ldstr    aDiscounttype// "discounttype"
0x28095  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2809a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2809f  ldarg.0
0x280a0  ldstr    aCreatedby// "createdby"
0x280a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x280aa  ldarg.3
0x280ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_createdby()
0x280b0  ldc.i4.0
0x280b1  ldc.i4.0
0x280b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x280b7  ldarg.0
0x280b8  ldstr    aCreatedon// "createdon"
0x280bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x280c2  ldarg.3
0x280c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_createdon()
0x280c8  ldc.i4.0
0x280c9  ldc.i4.0
0x280ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x280cf  ldarg.0
0x280d0  ldstr    aDescription_0// "description"
0x280d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x280da  ldarg.3
0x280db  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_description()
0x280e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x280e5  ldarg.0
0x280e6  ldstr    aDiscounttypeid// "discounttypeid"
0x280eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x280f0  ldarg.3
0x280f1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_discounttypeid()
0x280f6  ldc.i4.0
0x280f7  ldc.i4.0
0x280f8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x280fd  ldarg.0
0x280fe  ldstr    aImportsequence// "importsequencenumber"
0x28103  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28108  ldarg.3
0x28109  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_importsequencenumber()
0x2810e  ldc.i4.0
0x2810f  ldc.i4.0
0x28110  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28115  ldarg.0
0x28116  ldstr    aIsamounttype// "isamounttype"
0x2811b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28120  ldarg.3
0x28121  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_isamounttype()
0x28126  ldc.i4.0
0x28127  ldc.i4.0
0x28128  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2812d  ldarg.0
0x2812e  ldstr    aModifiedby// "modifiedby"
0x28133  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28138  ldarg.3
0x28139  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_modifiedby()
0x2813e  ldc.i4.0
0x2813f  ldc.i4.0
0x28140  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28145  ldarg.0
0x28146  ldstr    aModifiedon// "modifiedon"
0x2814b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28150  ldarg.3
0x28151  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_modifiedon()
0x28156  ldc.i4.0
0x28157  ldc.i4.0
0x28158  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2815d  ldarg.0
0x2815e  ldstr    aName// "name"
0x28163  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28168  ldarg.3
0x28169  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_name()
0x2816e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28173  ldarg.0
0x28174  ldstr    aOrganizationid// "organizationid"
0x28179  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2817e  ldarg.3
0x2817f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_organizationid()
0x28184  ldc.i4.0
0x28185  ldc.i4.0
0x28186  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2818b  ldarg.0
0x2818c  ldstr    aOverriddencrea// "overriddencreatedon"
0x28191  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28196  ldarg.3
0x28197  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_overriddencreatedon()
0x2819c  ldc.i4.0
0x2819d  ldc.i4.0
0x2819e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x281a3  ldarg.0
0x281a4  ldstr    aStatecode// "statecode"
0x281a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x281ae  ldarg.3
0x281af  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DiscountTypeStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_statecode()
0x281b4  ldc.i4.0
0x281b5  ldc.i4.0
0x281b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write385_DiscountTypeStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.DiscountTypeStateInfo o, bool isNullable, bool needType)
0x281bb  ldarg.0
0x281bc  ldstr    aStatuscode// "statuscode"
0x281c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x281c6  ldarg.3
0x281c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_statuscode()
0x281cc  ldc.i4.0
0x281cd  ldc.i4.0
0x281ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x281d3  ldarg.0
0x281d4  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x281d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x281de  ldarg.3
0x281df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.discounttype::get_transactioncurrencyid()
0x281e4  ldc.i4.0
0x281e5  ldc.i4.0
0x281e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x281eb  ldarg.0
0x281ec  ldarg.3
0x281ed  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x281f2  ret
```
