# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write400_contractdetail

- ea: `0x28da0`
- end: `0x291e1`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write400_contractdetail`
- size: `1089`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x379b0`
- `0x56dd0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x150d0`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x15430`
- `0x16cb0`
- `0x170c0`
- `0x28da0`
- `0x291f0`

## string_xrefs

- `0x28de5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28df5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e0d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e9d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28eb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28ecd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28ee5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28efd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28f15`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28f2b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28f43`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28f5b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28f73`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28f8b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28fa3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28fbb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28fd3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28feb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29003`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2901b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29033`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2904b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29063`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2907b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29093`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x290a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x290c1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x290d9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x290f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29109`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29121`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29139`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29151`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29167`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2917f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x29197`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x291af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x291c7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28e80`: `createdby`
- `0x28e98`: `createdon`
- `0x28ffe`: `overriddencreatedon`
- `0x290d4`: `serviceaddress`
- `0x290ec`: `servicecontractunitscode`

## pseudocode

```c

```

## disassembly

```asm
0x28da0  ldarg.3
0x28da1  brtrue.s loc_28DB0
0x28da3  ldarg.s  4
0x28da5  brfalse.s loc_28DAF
0x28da7  ldarg.0
0x28da8  ldarg.1
0x28da9  ldarg.2
0x28daa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x28daf  ret
0x28db0  ldarg.s  5
0x28db2  brtrue.s loc_28DD0
0x28db4  ldarg.3
0x28db5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x28dba  stloc.0
0x28dbb  ldloc.0
0x28dbc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail
0x28dc1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28dc6  beq.s    loc_28DD0
0x28dc8  ldarg.0
0x28dc9  ldarg.3
0x28dca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x28dcf  throw
0x28dd0  ldarg.0
0x28dd1  ldarg.1
0x28dd2  ldarg.2
0x28dd3  ldarg.3
0x28dd4  ldc.i4.0
0x28dd5  ldnull
0x28dd6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x28ddb  ldarg.s  5
0x28ddd  brfalse.s loc_28DEF
0x28ddf  ldarg.0
0x28de0  ldstr    aContractdetail_0// "contractdetail"
0x28de5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28dea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x28def  ldarg.0
0x28df0  ldstr    aActiveon// "activeon"
0x28df5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28dfa  ldarg.3
0x28dfb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_activeon()
0x28e00  ldc.i4.0
0x28e01  ldc.i4.0
0x28e02  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28e07  ldarg.0
0x28e08  ldstr    aAllotmentsrema// "allotmentsremaining"
0x28e0d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28e12  ldarg.3
0x28e13  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_allotmentsremaining()
0x28e18  ldc.i4.0
0x28e19  ldc.i4.0
0x28e1a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28e1f  ldarg.0
0x28e20  ldstr    aAllotmentsused// "allotmentsused"
0x28e25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28e2a  ldarg.3
0x28e2b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_allotmentsused()
0x28e30  ldc.i4.0
0x28e31  ldc.i4.0
0x28e32  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28e37  ldarg.0
0x28e38  ldstr    aContractdetail_1// "contractdetailid"
0x28e3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28e42  ldarg.3
0x28e43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_contractdetailid()
0x28e48  ldc.i4.0
0x28e49  ldc.i4.0
0x28e4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x28e4f  ldarg.0
0x28e50  ldstr    aContractid// "contractid"
0x28e55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28e5a  ldarg.3
0x28e5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_contractid()
0x28e60  ldc.i4.0
0x28e61  ldc.i4.0
0x28e62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28e67  ldarg.0
0x28e68  ldstr    aContractstatec// "contractstatecode"
0x28e6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28e72  ldarg.3
0x28e73  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_contractstatecode()
0x28e78  ldc.i4.0
0x28e79  ldc.i4.0
0x28e7a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x28e7f  ldarg.0
0x28e80  ldstr    aCreatedby// "createdby"
0x28e85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28e8a  ldarg.3
0x28e8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_createdby()
0x28e90  ldc.i4.0
0x28e91  ldc.i4.0
0x28e92  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28e97  ldarg.0
0x28e98  ldstr    aCreatedon// "createdon"
0x28e9d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28ea2  ldarg.3
0x28ea3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_createdon()
0x28ea8  ldc.i4.0
0x28ea9  ldc.i4.0
0x28eaa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28eaf  ldarg.0
0x28eb0  ldstr    aCustomerid// "customerid"
0x28eb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28eba  ldarg.3
0x28ebb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_customerid()
0x28ec0  ldc.i4.0
0x28ec1  ldc.i4.0
0x28ec2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write124_Customer(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Customer o, bool isNullable, bool needType)
0x28ec7  ldarg.0
0x28ec8  ldstr    aDiscount// "discount"
0x28ecd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28ed2  ldarg.3
0x28ed3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_discount()
0x28ed8  ldc.i4.0
0x28ed9  ldc.i4.0
0x28eda  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x28edf  ldarg.0
0x28ee0  ldstr    aDiscountBase// "discount_base"
0x28ee5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28eea  ldarg.3
0x28eeb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_discount_base()
0x28ef0  ldc.i4.0
0x28ef1  ldc.i4.0
0x28ef2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x28ef7  ldarg.0
0x28ef8  ldstr    aDiscountpercen// "discountpercentage"
0x28efd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28f02  ldarg.3
0x28f03  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_discountpercentage()
0x28f08  ldc.i4.0
0x28f09  ldc.i4.0
0x28f0a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x28f0f  ldarg.0
0x28f10  ldstr    aEffectivitycal// "effectivitycalendar"
0x28f15  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28f1a  ldarg.3
0x28f1b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_effectivitycalendar()
0x28f20  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28f25  ldarg.0
0x28f26  ldstr    aExchangerate// "exchangerate"
0x28f2b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28f30  ldarg.3
0x28f31  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_exchangerate()
0x28f36  ldc.i4.0
0x28f37  ldc.i4.0
0x28f38  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write137_CrmDecimal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal o, bool isNullable, bool needType)
0x28f3d  ldarg.0
0x28f3e  ldstr    aExpireson// "expireson"
0x28f43  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28f48  ldarg.3
0x28f49  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_expireson()
0x28f4e  ldc.i4.0
0x28f4f  ldc.i4.0
0x28f50  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28f55  ldarg.0
0x28f56  ldstr    aImportsequence// "importsequencenumber"
0x28f5b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28f60  ldarg.3
0x28f61  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_importsequencenumber()
0x28f66  ldc.i4.0
0x28f67  ldc.i4.0
0x28f68  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28f6d  ldarg.0
0x28f6e  ldstr    aInitialquantit// "initialquantity"
0x28f73  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28f78  ldarg.3
0x28f79  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_initialquantity()
0x28f7e  ldc.i4.0
0x28f7f  ldc.i4.0
0x28f80  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28f85  ldarg.0
0x28f86  ldstr    aLineitemorder// "lineitemorder"
0x28f8b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28f90  ldarg.3
0x28f91  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_lineitemorder()
0x28f96  ldc.i4.0
0x28f97  ldc.i4.0
0x28f98  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28f9d  ldarg.0
0x28f9e  ldstr    aModifiedby// "modifiedby"
0x28fa3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28fa8  ldarg.3
0x28fa9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_modifiedby()
0x28fae  ldc.i4.0
0x28faf  ldc.i4.0
0x28fb0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28fb5  ldarg.0
0x28fb6  ldstr    aModifiedon// "modifiedon"
0x28fbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28fc0  ldarg.3
0x28fc1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_modifiedon()
0x28fc6  ldc.i4.0
0x28fc7  ldc.i4.0
0x28fc8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28fcd  ldarg.0
0x28fce  ldstr    aNet// "net"
0x28fd3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28fd8  ldarg.3
0x28fd9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_net()
0x28fde  ldc.i4.0
0x28fdf  ldc.i4.0
0x28fe0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x28fe5  ldarg.0
0x28fe6  ldstr    aNetBase// "net_base"
0x28feb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28ff0  ldarg.3
0x28ff1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_net_base()
0x28ff6  ldc.i4.0
0x28ff7  ldc.i4.0
0x28ff8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x28ffd  ldarg.0
0x28ffe  ldstr    aOverriddencrea// "overriddencreatedon"
0x29003  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29008  ldarg.3
0x29009  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_overriddencreatedon()
0x2900e  ldc.i4.0
0x2900f  ldc.i4.0
0x29010  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x29015  ldarg.0
0x29016  ldstr    aOwningbusiness// "owningbusinessunit"
0x2901b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29020  ldarg.3
0x29021  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_owningbusinessunit()
0x29026  ldc.i4.0
0x29027  ldc.i4.0
0x29028  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x2902d  ldarg.0
0x2902e  ldstr    aOwninguser// "owninguser"
0x29033  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29038  ldarg.3
0x29039  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_owninguser()
0x2903e  ldc.i4.0
0x2903f  ldc.i4.0
0x29040  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x29045  ldarg.0
0x29046  ldstr    aPrice// "price"
0x2904b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29050  ldarg.3
0x29051  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_price()
0x29056  ldc.i4.0
0x29057  ldc.i4.0
0x29058  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x2905d  ldarg.0
0x2905e  ldstr    aPriceBase// "price_base"
0x29063  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29068  ldarg.3
0x29069  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_price_base()
0x2906e  ldc.i4.0
0x2906f  ldc.i4.0
0x29070  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x29075  ldarg.0
0x29076  ldstr    aProductid// "productid"
0x2907b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29080  ldarg.3
0x29081  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_productid()
0x29086  ldc.i4.0
0x29087  ldc.i4.0
0x29088  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x2908d  ldarg.0
0x2908e  ldstr    aProductserialn// "productserialnumber"
0x29093  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x29098  ldarg.3
0x29099  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_productserialnumber()
0x2909e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x290a3  ldarg.0
0x290a4  ldstr    aRate// "rate"
0x290a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x290ae  ldarg.3
0x290af  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_rate()
0x290b4  ldc.i4.0
0x290b5  ldc.i4.0
0x290b6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x290bb  ldarg.0
0x290bc  ldstr    aRateBase// "rate_base"
0x290c1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x290c6  ldarg.3
0x290c7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_rate_base()
0x290cc  ldc.i4.0
0x290cd  ldc.i4.0
0x290ce  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write156_CrmMoney(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney o, bool isNullable, bool needType)
0x290d3  ldarg.0
0x290d4  ldstr    aServiceaddress// "serviceaddress"
0x290d9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x290de  ldarg.3
0x290df  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_serviceaddress()
0x290e4  ldc.i4.0
0x290e5  ldc.i4.0
0x290e6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x290eb  ldarg.0
0x290ec  ldstr    aServicecontrac// "servicecontractunitscode"
0x290f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x290f6  ldarg.3
0x290f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_servicecontractunitscode()
0x290fc  ldc.i4.0
0x290fd  ldc.i4.0
0x290fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x29103  ldarg.0
0x29104  ldstr    aStatecode// "statecode"
0x29109  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2910e  ldarg.3
0x2910f  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ContractDetailStateInfo [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.contractdetail::get_statecode()
  ... truncated ...
```
