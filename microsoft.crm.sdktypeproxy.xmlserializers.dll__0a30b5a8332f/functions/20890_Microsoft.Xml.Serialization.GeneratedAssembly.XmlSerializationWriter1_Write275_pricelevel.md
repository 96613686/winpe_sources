# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write275_pricelevel

- ea: `0x20890`
- end: `0x20ac3`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write275_pricelevel`
- size: `563`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36750`
- `0x55b00`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x16cb0`
- `0x20890`
- `0x20ad0`

## string_xrefs

- `0x208d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x208e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x208fd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20915`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2092d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20943`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2095b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20973`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2098b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x209a3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x209bb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x209d1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x209e9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20a01`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20a19`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20a31`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20a49`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20a61`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20a79`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20a91`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20aa9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x208f8`: `createdby`
- `0x20910`: `createdon`
- `0x209e4`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x20890  ldarg.3
0x20891  brtrue.s loc_208A0
0x20893  ldarg.s  4
0x20895  brfalse.s loc_2089F
0x20897  ldarg.0
0x20898  ldarg.1
0x20899  ldarg.2
0x2089a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2089f  ret
0x208a0  ldarg.s  5
0x208a2  brtrue.s loc_208C0
0x208a4  ldarg.3
0x208a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x208aa  stloc.0
0x208ab  ldloc.0
0x208ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel
0x208b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x208b6  beq.s    loc_208C0
0x208b8  ldarg.0
0x208b9  ldarg.3
0x208ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x208bf  throw
0x208c0  ldarg.0
0x208c1  ldarg.1
0x208c2  ldarg.2
0x208c3  ldarg.3
0x208c4  ldc.i4.0
0x208c5  ldnull
0x208c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x208cb  ldarg.s  5
0x208cd  brfalse.s loc_208DF
0x208cf  ldarg.0
0x208d0  ldstr    aPricelevel// "pricelevel"
0x208d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x208da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x208df  ldarg.0
0x208e0  ldstr    aBegindate// "begindate"
0x208e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x208ea  ldarg.3
0x208eb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_begindate()
0x208f0  ldc.i4.0
0x208f1  ldc.i4.0
0x208f2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x208f7  ldarg.0
0x208f8  ldstr    aCreatedby// "createdby"
0x208fd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20902  ldarg.3
0x20903  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_createdby()
0x20908  ldc.i4.0
0x20909  ldc.i4.0
0x2090a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2090f  ldarg.0
0x20910  ldstr    aCreatedon// "createdon"
0x20915  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2091a  ldarg.3
0x2091b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_createdon()
0x20920  ldc.i4.0
0x20921  ldc.i4.0
0x20922  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20927  ldarg.0
0x20928  ldstr    aDescription_0// "description"
0x2092d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20932  ldarg.3
0x20933  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_description()
0x20938  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2093d  ldarg.0
0x2093e  ldstr    aEnddate// "enddate"
0x20943  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20948  ldarg.3
0x20949  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_enddate()
0x2094e  ldc.i4.0
0x2094f  ldc.i4.0
0x20950  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x20955  ldarg.0
0x20956  ldstr    aFreighttermsco// "freighttermscode"
0x2095b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20960  ldarg.3
0x20961  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_freighttermscode()
0x20966  ldc.i4.0
0x20967  ldc.i4.0
0x20968  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x2096d  ldarg.0
0x2096e  ldstr    aImportsequence// "importsequencenumber"
0x20973  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20978  ldarg.3
0x20979  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_importsequencenumber()
0x2097e  ldc.i4.0
0x2097f  ldc.i4.0
0x20980  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20985  ldarg.0
0x20986  ldstr    aModifiedby// "modifiedby"
0x2098b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20990  ldarg.3
0x20991  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_modifiedby()
0x20996  ldc.i4.0
0x20997  ldc.i4.0
0x20998  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2099d  ldarg.0
0x2099e  ldstr    aModifiedon// "modifiedon"
0x209a3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x209a8  ldarg.3
0x209a9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_modifiedon()
0x209ae  ldc.i4.0
0x209af  ldc.i4.0
0x209b0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x209b5  ldarg.0
0x209b6  ldstr    aName// "name"
0x209bb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x209c0  ldarg.3
0x209c1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_name()
0x209c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x209cb  ldarg.0
0x209cc  ldstr    aOrganizationid// "organizationid"
0x209d1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x209d6  ldarg.3
0x209d7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_organizationid()
0x209dc  ldc.i4.0
0x209dd  ldc.i4.0
0x209de  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x209e3  ldarg.0
0x209e4  ldstr    aOverriddencrea// "overriddencreatedon"
0x209e9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x209ee  ldarg.3
0x209ef  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_overriddencreatedon()
0x209f4  ldc.i4.0
0x209f5  ldc.i4.0
0x209f6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x209fb  ldarg.0
0x209fc  ldstr    aPaymentmethodc// "paymentmethodcode"
0x20a01  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20a06  ldarg.3
0x20a07  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_paymentmethodcode()
0x20a0c  ldc.i4.0
0x20a0d  ldc.i4.0
0x20a0e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x20a13  ldarg.0
0x20a14  ldstr    aPricelevelid// "pricelevelid"
0x20a19  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20a1e  ldarg.3
0x20a1f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_pricelevelid()
0x20a24  ldc.i4.0
0x20a25  ldc.i4.0
0x20a26  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x20a2b  ldarg.0
0x20a2c  ldstr    aShippingmethod// "shippingmethodcode"
0x20a31  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20a36  ldarg.3
0x20a37  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_shippingmethodcode()
0x20a3c  ldc.i4.0
0x20a3d  ldc.i4.0
0x20a3e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x20a43  ldarg.0
0x20a44  ldstr    aStatecode// "statecode"
0x20a49  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20a4e  ldarg.3
0x20a4f  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PriceLevelStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_statecode()
0x20a54  ldc.i4.0
0x20a55  ldc.i4.0
0x20a56  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write274_PriceLevelStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PriceLevelStateInfo o, bool isNullable, bool needType)
0x20a5b  ldarg.0
0x20a5c  ldstr    aStatuscode// "statuscode"
0x20a61  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20a66  ldarg.3
0x20a67  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_statuscode()
0x20a6c  ldc.i4.0
0x20a6d  ldc.i4.0
0x20a6e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x20a73  ldarg.0
0x20a74  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x20a79  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20a7e  ldarg.3
0x20a7f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_timezoneruleversionnumber()
0x20a84  ldc.i4.0
0x20a85  ldc.i4.0
0x20a86  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20a8b  ldarg.0
0x20a8c  ldstr    aTransactioncur_0// "transactioncurrencyid"
0x20a91  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20a96  ldarg.3
0x20a97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_transactioncurrencyid()
0x20a9c  ldc.i4.0
0x20a9d  ldc.i4.0
0x20a9e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20aa3  ldarg.0
0x20aa4  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x20aa9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20aae  ldarg.3
0x20aaf  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.pricelevel::get_utcconversiontimezonecode()
0x20ab4  ldc.i4.0
0x20ab5  ldc.i4.0
0x20ab6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20abb  ldarg.0
0x20abc  ldarg.3
0x20abd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x20ac2  ret
```
