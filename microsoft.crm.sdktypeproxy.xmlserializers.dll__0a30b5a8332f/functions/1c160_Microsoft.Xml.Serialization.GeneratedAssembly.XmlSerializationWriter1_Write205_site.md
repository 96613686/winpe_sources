# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write205_site

- ea: `0x1c160`
- end: `0x1c66f`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write205_site`
- size: `1295`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x35b80`
- `0x54f30`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x165c0`
- `0x1c160`

## string_xrefs

- `0x1c1a5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c1b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c1cd`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c1e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c1fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c211`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c227`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c23d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c255`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c26b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c281`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c297`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c2af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c2c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c2db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c2f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c309`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c31f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c335`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c34b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c361`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c377`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c38f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c3a7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c3bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c3d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c3eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c401`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c417`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c42f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c445`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c45b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c471`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c489`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c49f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c4b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c4cb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c4e3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c4f9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c50f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c525`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c53b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c551`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c569`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c581`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c599`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c5af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c5c7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c5df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c5f7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c60d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c625`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c63d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c655`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1c564`: `createdby`
- `0x1c57c`: `createdon`
- `0x1c620`: `overriddencreatedon`
- `0x1c1b0`: `address1_addressid`
- `0x1c38a`: `address2_addressid`

## pseudocode

```c

```

## disassembly

```asm
0x1c160  ldarg.3
0x1c161  brtrue.s loc_1C170
0x1c163  ldarg.s  4
0x1c165  brfalse.s loc_1C16F
0x1c167  ldarg.0
0x1c168  ldarg.1
0x1c169  ldarg.2
0x1c16a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1c16f  ret
0x1c170  ldarg.s  5
0x1c172  brtrue.s loc_1C190
0x1c174  ldarg.3
0x1c175  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1c17a  stloc.0
0x1c17b  ldloc.0
0x1c17c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site
0x1c181  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c186  beq.s    loc_1C190
0x1c188  ldarg.0
0x1c189  ldarg.3
0x1c18a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x1c18f  throw
0x1c190  ldarg.0
0x1c191  ldarg.1
0x1c192  ldarg.2
0x1c193  ldarg.3
0x1c194  ldc.i4.0
0x1c195  ldnull
0x1c196  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1c19b  ldarg.s  5
0x1c19d  brfalse.s loc_1C1AF
0x1c19f  ldarg.0
0x1c1a0  ldstr    aSite// "site"
0x1c1a5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c1aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1c1af  ldarg.0
0x1c1b0  ldstr    aAddress1Addres// "address1_addressid"
0x1c1b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c1ba  ldarg.3
0x1c1bb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_addressid()
0x1c1c0  ldc.i4.0
0x1c1c1  ldc.i4.0
0x1c1c2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1c1c7  ldarg.0
0x1c1c8  ldstr    aAddress1Addres_0// "address1_addresstypecode"
0x1c1cd  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c1d2  ldarg.3
0x1c1d3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_addresstypecode()
0x1c1d8  ldc.i4.0
0x1c1d9  ldc.i4.0
0x1c1da  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1c1df  ldarg.0
0x1c1e0  ldstr    aAddress1City// "address1_city"
0x1c1e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c1ea  ldarg.3
0x1c1eb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_city()
0x1c1f0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c1f5  ldarg.0
0x1c1f6  ldstr    aAddress1Countr// "address1_country"
0x1c1fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c200  ldarg.3
0x1c201  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_country()
0x1c206  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c20b  ldarg.0
0x1c20c  ldstr    aAddress1County// "address1_county"
0x1c211  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c216  ldarg.3
0x1c217  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_county()
0x1c21c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c221  ldarg.0
0x1c222  ldstr    aAddress1Fax// "address1_fax"
0x1c227  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c22c  ldarg.3
0x1c22d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_fax()
0x1c232  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c237  ldarg.0
0x1c238  ldstr    aAddress1Latitu// "address1_latitude"
0x1c23d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c242  ldarg.3
0x1c243  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_latitude()
0x1c248  ldc.i4.0
0x1c249  ldc.i4.0
0x1c24a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x1c24f  ldarg.0
0x1c250  ldstr    aAddress1Line1// "address1_line1"
0x1c255  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c25a  ldarg.3
0x1c25b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_line1()
0x1c260  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c265  ldarg.0
0x1c266  ldstr    aAddress1Line2// "address1_line2"
0x1c26b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c270  ldarg.3
0x1c271  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_line2()
0x1c276  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c27b  ldarg.0
0x1c27c  ldstr    aAddress1Line3// "address1_line3"
0x1c281  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c286  ldarg.3
0x1c287  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_line3()
0x1c28c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c291  ldarg.0
0x1c292  ldstr    aAddress1Longit// "address1_longitude"
0x1c297  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c29c  ldarg.3
0x1c29d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_longitude()
0x1c2a2  ldc.i4.0
0x1c2a3  ldc.i4.0
0x1c2a4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x1c2a9  ldarg.0
0x1c2aa  ldstr    aAddress1Name// "address1_name"
0x1c2af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c2b4  ldarg.3
0x1c2b5  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_name()
0x1c2ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c2bf  ldarg.0
0x1c2c0  ldstr    aAddress1Postal// "address1_postalcode"
0x1c2c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c2ca  ldarg.3
0x1c2cb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_postalcode()
0x1c2d0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c2d5  ldarg.0
0x1c2d6  ldstr    aAddress1Postof// "address1_postofficebox"
0x1c2db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c2e0  ldarg.3
0x1c2e1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_postofficebox()
0x1c2e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c2eb  ldarg.0
0x1c2ec  ldstr    aAddress1Shippi// "address1_shippingmethodcode"
0x1c2f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c2f6  ldarg.3
0x1c2f7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_shippingmethodcode()
0x1c2fc  ldc.i4.0
0x1c2fd  ldc.i4.0
0x1c2fe  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1c303  ldarg.0
0x1c304  ldstr    aAddress1Stateo// "address1_stateorprovince"
0x1c309  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c30e  ldarg.3
0x1c30f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_stateorprovince()
0x1c314  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c319  ldarg.0
0x1c31a  ldstr    aAddress1Teleph// "address1_telephone1"
0x1c31f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c324  ldarg.3
0x1c325  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_telephone1()
0x1c32a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c32f  ldarg.0
0x1c330  ldstr    aAddress1Teleph_0// "address1_telephone2"
0x1c335  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c33a  ldarg.3
0x1c33b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_telephone2()
0x1c340  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c345  ldarg.0
0x1c346  ldstr    aAddress1Teleph_1// "address1_telephone3"
0x1c34b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c350  ldarg.3
0x1c351  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_telephone3()
0x1c356  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c35b  ldarg.0
0x1c35c  ldstr    aAddress1Upszon// "address1_upszone"
0x1c361  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c366  ldarg.3
0x1c367  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_upszone()
0x1c36c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c371  ldarg.0
0x1c372  ldstr    aAddress1Utcoff// "address1_utcoffset"
0x1c377  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c37c  ldarg.3
0x1c37d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address1_utcoffset()
0x1c382  ldc.i4.0
0x1c383  ldc.i4.0
0x1c384  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x1c389  ldarg.0
0x1c38a  ldstr    aAddress2Addres// "address2_addressid"
0x1c38f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c394  ldarg.3
0x1c395  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_addressid()
0x1c39a  ldc.i4.0
0x1c39b  ldc.i4.0
0x1c39c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x1c3a1  ldarg.0
0x1c3a2  ldstr    aAddress2Addres_0// "address2_addresstypecode"
0x1c3a7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c3ac  ldarg.3
0x1c3ad  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_addresstypecode()
0x1c3b2  ldc.i4.0
0x1c3b3  ldc.i4.0
0x1c3b4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1c3b9  ldarg.0
0x1c3ba  ldstr    aAddress2City// "address2_city"
0x1c3bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c3c4  ldarg.3
0x1c3c5  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_city()
0x1c3ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c3cf  ldarg.0
0x1c3d0  ldstr    aAddress2Countr// "address2_country"
0x1c3d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c3da  ldarg.3
0x1c3db  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_country()
0x1c3e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c3e5  ldarg.0
0x1c3e6  ldstr    aAddress2County// "address2_county"
0x1c3eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c3f0  ldarg.3
0x1c3f1  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_county()
0x1c3f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c3fb  ldarg.0
0x1c3fc  ldstr    aAddress2Fax// "address2_fax"
0x1c401  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c406  ldarg.3
0x1c407  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_fax()
0x1c40c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c411  ldarg.0
0x1c412  ldstr    aAddress2Latitu// "address2_latitude"
0x1c417  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c41c  ldarg.3
0x1c41d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_latitude()
0x1c422  ldc.i4.0
0x1c423  ldc.i4.0
0x1c424  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x1c429  ldarg.0
0x1c42a  ldstr    aAddress2Line1// "address2_line1"
0x1c42f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c434  ldarg.3
0x1c435  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_line1()
0x1c43a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c43f  ldarg.0
0x1c440  ldstr    aAddress2Line2// "address2_line2"
0x1c445  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c44a  ldarg.3
0x1c44b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_line2()
0x1c450  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c455  ldarg.0
0x1c456  ldstr    aAddress2Line3// "address2_line3"
0x1c45b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c460  ldarg.3
0x1c461  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_line3()
0x1c466  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c46b  ldarg.0
0x1c46c  ldstr    aAddress2Longit// "address2_longitude"
0x1c471  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c476  ldarg.3
0x1c477  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_longitude()
0x1c47c  ldc.i4.0
0x1c47d  ldc.i4.0
0x1c47e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write130_CrmFloat(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat o, bool isNullable, bool needType)
0x1c483  ldarg.0
0x1c484  ldstr    aAddress2Name// "address2_name"
0x1c489  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c48e  ldarg.3
0x1c48f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_name()
0x1c494  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c499  ldarg.0
0x1c49a  ldstr    aAddress2Postal// "address2_postalcode"
0x1c49f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c4a4  ldarg.3
0x1c4a5  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_postalcode()
0x1c4aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c4af  ldarg.0
0x1c4b0  ldstr    aAddress2Postof// "address2_postofficebox"
0x1c4b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c4ba  ldarg.3
0x1c4bb  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_postofficebox()
0x1c4c0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c4c5  ldarg.0
0x1c4c6  ldstr    aAddress2Shippi// "address2_shippingmethodcode"
0x1c4cb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c4d0  ldarg.3
0x1c4d1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_shippingmethodcode()
0x1c4d6  ldc.i4.0
0x1c4d7  ldc.i4.0
0x1c4d8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x1c4dd  ldarg.0
0x1c4de  ldstr    aAddress2Stateo// "address2_stateorprovince"
0x1c4e3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c4e8  ldarg.3
0x1c4e9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_stateorprovince()
0x1c4ee  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c4f3  ldarg.0
0x1c4f4  ldstr    aAddress2Teleph// "address2_telephone1"
0x1c4f9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c4fe  ldarg.3
0x1c4ff  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_telephone1()
0x1c504  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c509  ldarg.0
0x1c50a  ldstr    aAddress2Teleph_0// "address2_telephone2"
0x1c50f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c514  ldarg.3
0x1c515  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_telephone2()
0x1c51a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c51f  ldarg.0
0x1c520  ldstr    aAddress2Teleph_1// "address2_telephone3"
0x1c525  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1c52a  ldarg.3
0x1c52b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.site::get_address2_telephone3()
0x1c530  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1c535  ldarg.0
0x1c536  ldstr    aAddress2Upszon// "address2_upszone"
0x1c53b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
  ... truncated ...
```
