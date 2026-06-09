# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write394_customeraddress

- ea: `0x28830`
- end: `0x28bc7`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write394_customeraddress`
- size: `919`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x378d0`
- `0x56cf0`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x153c0`
- `0x165c0`
- `0x167c0`
- `0x28830`

## string_xrefs

- `0x28875`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28885`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2889d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x288b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x288cb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x288e1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x288f7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2890f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28927`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2893f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28955`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2896d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28985`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2899d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x289b3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x289c9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x289df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x289f7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28a0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28a27`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28a3d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28a55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28a6d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28a85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28a9d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28ab5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28acb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28ae1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28af7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28b0f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28b25`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28b3b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28b51`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28b67`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28b7f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28b95`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x28bad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x288f2`: `createdby`
- `0x2890a`: `createdon`
- `0x28a50`: `overriddencreatedon`
- `0x28922`: `customeraddressid`

## pseudocode

```c

```

## disassembly

```asm
0x28830  ldarg.3
0x28831  brtrue.s loc_28840
0x28833  ldarg.s  4
0x28835  brfalse.s loc_2883F
0x28837  ldarg.0
0x28838  ldarg.1
0x28839  ldarg.2
0x2883a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2883f  ret
0x28840  ldarg.s  5
0x28842  brtrue.s loc_28860
0x28844  ldarg.3
0x28845  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2884a  stloc.0
0x2884b  ldloc.0
0x2884c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress
0x28851  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x28856  beq.s    loc_28860
0x28858  ldarg.0
0x28859  ldarg.3
0x2885a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2885f  throw
0x28860  ldarg.0
0x28861  ldarg.1
0x28862  ldarg.2
0x28863  ldarg.3
0x28864  ldc.i4.0
0x28865  ldnull
0x28866  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2886b  ldarg.s  5
0x2886d  brfalse.s loc_2887F
0x2886f  ldarg.0
0x28870  ldstr    aCustomeraddres// "customeraddress"
0x28875  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2887a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2887f  ldarg.0
0x28880  ldstr    aAddressnumber// "addressnumber"
0x28885  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2888a  ldarg.3
0x2888b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_addressnumber()
0x28890  ldc.i4.0
0x28891  ldc.i4.0
0x28892  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28897  ldarg.0
0x28898  ldstr    aAddresstypecod// "addresstypecode"
0x2889d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x288a2  ldarg.3
0x288a3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_addresstypecode()
0x288a8  ldc.i4.0
0x288a9  ldc.i4.0
0x288aa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x288af  ldarg.0
0x288b0  ldstr    aCity// "city"
0x288b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x288ba  ldarg.3
0x288bb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_city()
0x288c0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x288c5  ldarg.0
0x288c6  ldstr    aCountry// "country"
0x288cb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x288d0  ldarg.3
0x288d1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_country()
0x288d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x288db  ldarg.0
0x288dc  ldstr    aCounty// "county"
0x288e1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x288e6  ldarg.3
0x288e7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_county()
0x288ec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x288f1  ldarg.0
0x288f2  ldstr    aCreatedby// "createdby"
0x288f7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x288fc  ldarg.3
0x288fd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_createdby()
0x28902  ldc.i4.0
0x28903  ldc.i4.0
0x28904  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28909  ldarg.0
0x2890a  ldstr    aCreatedon// "createdon"
0x2890f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28914  ldarg.3
0x28915  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_createdon()
0x2891a  ldc.i4.0
0x2891b  ldc.i4.0
0x2891c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28921  ldarg.0
0x28922  ldstr    aCustomeraddres_0// "customeraddressid"
0x28927  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2892c  ldarg.3
0x2892d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_customeraddressid()
0x28932  ldc.i4.0
0x28933  ldc.i4.0
0x28934  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x28939  ldarg.0
0x2893a  ldstr    aFax// "fax"
0x2893f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28944  ldarg.3
0x28945  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_fax()
0x2894a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2894f  ldarg.0
0x28950  ldstr    aFreighttermsco// "freighttermscode"
0x28955  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2895a  ldarg.3
0x2895b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_freighttermscode()
0x28960  ldc.i4.0
0x28961  ldc.i4.0
0x28962  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x28967  ldarg.0
0x28968  ldstr    aImportsequence// "importsequencenumber"
0x2896d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28972  ldarg.3
0x28973  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_importsequencenumber()
0x28978  ldc.i4.0
0x28979  ldc.i4.0
0x2897a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x2897f  ldarg.0
0x28980  ldstr    aLatitude// "latitude"
0x28985  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2898a  ldarg.3
0x2898b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_latitude()
0x28990  ldc.i4.0
0x28991  ldc.i4.0
0x28992  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x28997  ldarg.0
0x28998  ldstr    aLine1// "line1"
0x2899d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x289a2  ldarg.3
0x289a3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_line1()
0x289a8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x289ad  ldarg.0
0x289ae  ldstr    aLine2// "line2"
0x289b3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x289b8  ldarg.3
0x289b9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_line2()
0x289be  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x289c3  ldarg.0
0x289c4  ldstr    aLine3// "line3"
0x289c9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x289ce  ldarg.3
0x289cf  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_line3()
0x289d4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x289d9  ldarg.0
0x289da  ldstr    aLongitude// "longitude"
0x289df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x289e4  ldarg.3
0x289e5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_longitude()
0x289ea  ldc.i4.0
0x289eb  ldc.i4.0
0x289ec  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x289f1  ldarg.0
0x289f2  ldstr    aModifiedby// "modifiedby"
0x289f7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x289fc  ldarg.3
0x289fd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_modifiedby()
0x28a02  ldc.i4.0
0x28a03  ldc.i4.0
0x28a04  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28a09  ldarg.0
0x28a0a  ldstr    aModifiedon// "modifiedon"
0x28a0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28a14  ldarg.3
0x28a15  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_modifiedon()
0x28a1a  ldc.i4.0
0x28a1b  ldc.i4.0
0x28a1c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28a21  ldarg.0
0x28a22  ldstr    aName// "name"
0x28a27  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28a2c  ldarg.3
0x28a2d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_name()
0x28a32  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28a37  ldarg.0
0x28a38  ldstr    aObjecttypecode_0// "objecttypecode"
0x28a3d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28a42  ldarg.3
0x28a43  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_objecttypecode()
0x28a48  ldc.i4.0
0x28a49  ldc.i4.0
0x28a4a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x28a4f  ldarg.0
0x28a50  ldstr    aOverriddencrea// "overriddencreatedon"
0x28a55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28a5a  ldarg.3
0x28a5b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_overriddencreatedon()
0x28a60  ldc.i4.0
0x28a61  ldc.i4.0
0x28a62  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x28a67  ldarg.0
0x28a68  ldstr    aOwningbusiness// "owningbusinessunit"
0x28a6d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28a72  ldarg.3
0x28a73  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_owningbusinessunit()
0x28a78  ldc.i4.0
0x28a79  ldc.i4.0
0x28a7a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28a7f  ldarg.0
0x28a80  ldstr    aOwninguser// "owninguser"
0x28a85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28a8a  ldarg.3
0x28a8b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_owninguser()
0x28a90  ldc.i4.0
0x28a91  ldc.i4.0
0x28a92  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28a97  ldarg.0
0x28a98  ldstr    aParentid// "parentid"
0x28a9d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28aa2  ldarg.3
0x28aa3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_parentid()
0x28aa8  ldc.i4.0
0x28aa9  ldc.i4.0
0x28aaa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x28aaf  ldarg.0
0x28ab0  ldstr    aPostalcode// "postalcode"
0x28ab5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28aba  ldarg.3
0x28abb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_postalcode()
0x28ac0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28ac5  ldarg.0
0x28ac6  ldstr    aPostofficebox// "postofficebox"
0x28acb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28ad0  ldarg.3
0x28ad1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_postofficebox()
0x28ad6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28adb  ldarg.0
0x28adc  ldstr    aPrimarycontact// "primarycontactname"
0x28ae1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28ae6  ldarg.3
0x28ae7  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_primarycontactname()
0x28aec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28af1  ldarg.0
0x28af2  ldstr    aShippingmethod// "shippingmethodcode"
0x28af7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28afc  ldarg.3
0x28afd  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_shippingmethodcode()
0x28b02  ldc.i4.0
0x28b03  ldc.i4.0
0x28b04  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x28b09  ldarg.0
0x28b0a  ldstr    aStateorprovinc// "stateorprovince"
0x28b0f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28b14  ldarg.3
0x28b15  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_stateorprovince()
0x28b1a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28b1f  ldarg.0
0x28b20  ldstr    aTelephone1// "telephone1"
0x28b25  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28b2a  ldarg.3
0x28b2b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_telephone1()
0x28b30  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28b35  ldarg.0
0x28b36  ldstr    aTelephone2// "telephone2"
0x28b3b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28b40  ldarg.3
0x28b41  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_telephone2()
0x28b46  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28b4b  ldarg.0
0x28b4c  ldstr    aTelephone3// "telephone3"
0x28b51  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28b56  ldarg.3
0x28b57  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_telephone3()
0x28b5c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28b61  ldarg.0
0x28b62  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x28b67  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28b6c  ldarg.3
0x28b6d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_timezoneruleversionnumber()
0x28b72  ldc.i4.0
0x28b73  ldc.i4.0
0x28b74  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28b79  ldarg.0
0x28b7a  ldstr    aUpszone// "upszone"
0x28b7f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28b84  ldarg.3
0x28b85  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_upszone()
0x28b8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x28b8f  ldarg.0
0x28b90  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x28b95  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28b9a  ldarg.3
0x28b9b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_utcconversiontimezonecode()
0x28ba0  ldc.i4.0
0x28ba1  ldc.i4.0
0x28ba2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28ba7  ldarg.0
0x28ba8  ldstr    aUtcoffset// "utcoffset"
0x28bad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x28bb2  ldarg.3
0x28bb3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.customeraddress::get_utcoffset()
0x28bb8  ldc.i4.0
0x28bb9  ldc.i4.0
0x28bba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x28bbf  ldarg.0
0x28bc0  ldarg.3
0x28bc1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x28bc6  ret
```
