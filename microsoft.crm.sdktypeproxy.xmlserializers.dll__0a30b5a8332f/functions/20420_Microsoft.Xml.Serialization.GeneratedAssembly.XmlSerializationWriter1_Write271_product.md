# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write271_product

- ea: `0x20420`
- end: `0x2080f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write271_product`
- size: `1007`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x366e0`
- `0x55a90`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x150d0`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x15430`
- `0x16cb0`
- `0x20420`
- `0x20810`

## string_xrefs

- `0x20465`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20475`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2048d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x204a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x204bd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x204d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x204ed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20505`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2051b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20533`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2054b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20563`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2057b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20593`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x205ab`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x205c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x205d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x205f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20609`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20621`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20639`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20651`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20667`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2067f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20695`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x206ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x206c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x206db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x206f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2070b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20723`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2073b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20753`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2076b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20783`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20799`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x207b1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x207c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x207e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x207f7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x20470`: `createdby`
- `0x20488`: `createdon`
- `0x205d4`: `overriddencreatedon`

## pseudocode

```c

```

## disassembly

```asm
0x20420  ldarg.3
0x20421  brtrue.s loc_20430
0x20423  ldarg.s  4
0x20425  brfalse.s loc_2042F
0x20427  ldarg.0
0x20428  ldarg.1
0x20429  ldarg.2
0x2042a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2042f  ret
0x20430  ldarg.s  5
0x20432  brtrue.s loc_20450
0x20434  ldarg.3
0x20435  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2043a  stloc.0
0x2043b  ldloc.0
0x2043c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product
0x20441  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20446  beq.s    loc_20450
0x20448  ldarg.0
0x20449  ldarg.3
0x2044a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2044f  throw
0x20450  ldarg.0
0x20451  ldarg.1
0x20452  ldarg.2
0x20453  ldarg.3
0x20454  ldc.i4.0
0x20455  ldnull
0x20456  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2045b  ldarg.s  5
0x2045d  brfalse.s loc_2046F
0x2045f  ldarg.0
0x20460  ldstr    aProduct// "product"
0x20465  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2046a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2046f  ldarg.0
0x20470  ldstr    aCreatedby// "createdby"
0x20475  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2047a  ldarg.3
0x2047b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_createdby()
0x20480  ldc.i4.0
0x20481  ldc.i4.0
0x20482  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20487  ldarg.0
0x20488  ldstr    aCreatedon// "createdon"
0x2048d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20492  ldarg.3
0x20493  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_createdon()
0x20498  ldc.i4.0
0x20499  ldc.i4.0
0x2049a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x2049f  ldarg.0
0x204a0  ldstr    aCurrentcost// "currentcost"
0x204a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x204aa  ldarg.3
0x204ab  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_currentcost()
0x204b0  ldc.i4.0
0x204b1  ldc.i4.0
0x204b2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x204b7  ldarg.0
0x204b8  ldstr    aCurrentcostBas// "currentcost_base"
0x204bd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x204c2  ldarg.3
0x204c3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_currentcost_base()
0x204c8  ldc.i4.0
0x204c9  ldc.i4.0
0x204ca  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x204cf  ldarg.0
0x204d0  ldstr    aDefaultuomid// "defaultuomid"
0x204d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x204da  ldarg.3
0x204db  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_defaultuomid()
0x204e0  ldc.i4.0
0x204e1  ldc.i4.0
0x204e2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x204e7  ldarg.0
0x204e8  ldstr    aDefaultuomsche// "defaultuomscheduleid"
0x204ed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x204f2  ldarg.3
0x204f3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_defaultuomscheduleid()
0x204f8  ldc.i4.0
0x204f9  ldc.i4.0
0x204fa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x204ff  ldarg.0
0x20500  ldstr    aDescription_0// "description"
0x20505  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2050a  ldarg.3
0x2050b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_description()
0x20510  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20515  ldarg.0
0x20516  ldstr    aExchangerate// "exchangerate"
0x2051b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20520  ldarg.3
0x20521  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_exchangerate()
0x20526  ldc.i4.0
0x20527  ldc.i4.0
0x20528  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2052d  ldarg.0
0x2052e  ldstr    aImportsequence// "importsequencenumber"
0x20533  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20538  ldarg.3
0x20539  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_importsequencenumber()
0x2053e  ldc.i4.0
0x2053f  ldc.i4.0
0x20540  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x20545  ldarg.0
0x20546  ldstr    aIskit// "iskit"
0x2054b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20550  ldarg.3
0x20551  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_iskit()
0x20556  ldc.i4.0
0x20557  ldc.i4.0
0x20558  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x2055d  ldarg.0
0x2055e  ldstr    aIsstockitem// "isstockitem"
0x20563  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20568  ldarg.3
0x20569  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_isstockitem()
0x2056e  ldc.i4.0
0x2056f  ldc.i4.0
0x20570  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x20575  ldarg.0
0x20576  ldstr    aModifiedby// "modifiedby"
0x2057b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20580  ldarg.3
0x20581  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_modifiedby()
0x20586  ldc.i4.0
0x20587  ldc.i4.0
0x20588  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2058d  ldarg.0
0x2058e  ldstr    aModifiedon// "modifiedon"
0x20593  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20598  ldarg.3
0x20599  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_modifiedon()
0x2059e  ldc.i4.0
0x2059f  ldc.i4.0
0x205a0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x205a5  ldarg.0
0x205a6  ldstr    aName// "name"
0x205ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x205b0  ldarg.3
0x205b1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_name()
0x205b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x205bb  ldarg.0
0x205bc  ldstr    aOrganizationid// "organizationid"
0x205c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x205c6  ldarg.3
0x205c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_organizationid()
0x205cc  ldc.i4.0
0x205cd  ldc.i4.0
0x205ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x205d3  ldarg.0
0x205d4  ldstr    aOverriddencrea// "overriddencreatedon"
0x205d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x205de  ldarg.3
0x205df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_overriddencreatedon()
0x205e4  ldc.i4.0
0x205e5  ldc.i4.0
0x205e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x205eb  ldarg.0
0x205ec  ldstr    aPrice// "price"
0x205f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x205f6  ldarg.3
0x205f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_price()
0x205fc  ldc.i4.0
0x205fd  ldc.i4.0
0x205fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x20603  ldarg.0
0x20604  ldstr    aPriceBase// "price_base"
0x20609  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2060e  ldarg.3
0x2060f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_price_base()
0x20614  ldc.i4.0
0x20615  ldc.i4.0
0x20616  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2061b  ldarg.0
0x2061c  ldstr    aPricelevelid// "pricelevelid"
0x20621  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20626  ldarg.3
0x20627  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_pricelevelid()
0x2062c  ldc.i4.0
0x2062d  ldc.i4.0
0x2062e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x20633  ldarg.0
0x20634  ldstr    aProductid// "productid"
0x20639  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2063e  ldarg.3
0x2063f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_productid()
0x20644  ldc.i4.0
0x20645  ldc.i4.0
0x20646  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x2064b  ldarg.0
0x2064c  ldstr    aProductnumber// "productnumber"
0x20651  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20656  ldarg.3
0x20657  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_productnumber()
0x2065c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20661  ldarg.0
0x20662  ldstr    aProducttypecod// "producttypecode"
0x20667  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2066c  ldarg.3
0x2066d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_producttypecode()
0x20672  ldc.i4.0
0x20673  ldc.i4.0
0x20674  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x20679  ldarg.0
0x2067a  ldstr    aProducturl// "producturl"
0x2067f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20684  ldarg.3
0x20685  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_producturl()
0x2068a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2068f  ldarg.0
0x20690  ldstr    aQuantitydecima// "quantitydecimal"
0x20695  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2069a  ldarg.3
0x2069b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_quantitydecimal()
0x206a0  ldc.i4.0
0x206a1  ldc.i4.0
0x206a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x206a7  ldarg.0
0x206a8  ldstr    aQuantityonhand// "quantityonhand"
0x206ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x206b2  ldarg.3
0x206b3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_quantityonhand()
0x206b8  ldc.i4.0
0x206b9  ldc.i4.0
0x206ba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x206bf  ldarg.0
0x206c0  ldstr    aSize// "size"
0x206c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x206ca  ldarg.3
0x206cb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_size()
0x206d0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x206d5  ldarg.0
0x206d6  ldstr    aStandardcost// "standardcost"
0x206db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x206e0  ldarg.3
0x206e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_standardcost()
0x206e6  ldc.i4.0
0x206e7  ldc.i4.0
0x206e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x206ed  ldarg.0
0x206ee  ldstr    aStandardcostBa// "standardcost_base"
0x206f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x206f8  ldarg.3
0x206f9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_standardcost_base()
0x206fe  ldc.i4.0
0x206ff  ldc.i4.0
0x20700  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x20705  ldarg.0
0x20706  ldstr    aStatecode// "statecode"
0x2070b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20710  ldarg.3
0x20711  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ProductStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_statecode()
0x20716  ldc.i4.0
0x20717  ldc.i4.0
0x20718  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write270_ProductStateInfo(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ProductStateInfo o, bool isNullable, bool needType)
0x2071d  ldarg.0
0x2071e  ldstr    aStatuscode// "statuscode"
0x20723  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20728  ldarg.3
0x20729  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_statuscode()
0x2072e  ldc.i4.0
0x2072f  ldc.i4.0
0x20730  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write144_Status(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Status o, bool isNullable, bool needType)
0x20735  ldarg.0
0x20736  ldstr    aStockvolume// "stockvolume"
0x2073b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20740  ldarg.3
0x20741  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_stockvolume()
0x20746  ldc.i4.0
0x20747  ldc.i4.0
0x20748  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x2074d  ldarg.0
0x2074e  ldstr    aStockweight// "stockweight"
0x20753  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20758  ldarg.3
0x20759  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_stockweight()
0x2075e  ldc.i4.0
0x2075f  ldc.i4.0
0x20760  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x20765  ldarg.0
0x20766  ldstr    aSubjectid// "subjectid"
0x2076b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20770  ldarg.3
0x20771  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_subjectid()
0x20776  ldc.i4.0
0x20777  ldc.i4.0
0x20778  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2077d  ldarg.0
0x2077e  ldstr    aSuppliername// "suppliername"
0x20783  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x20788  ldarg.3
0x20789  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_suppliername()
0x2078e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x20793  ldarg.0
0x20794  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x20799  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2079e  ldarg.3
0x2079f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.product::get_timezoneruleversionnumber()
  ... truncated ...
```
