# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write315_letter

- ea: `0x23a80`
- end: `0x23ee0`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write315_letter`
- size: `1120`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36d00`
- `0x56190`

## callees

- `0x5cf0`
- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15270`
- `0x15320`
- `0x153c0`
- `0x16a10`
- `0x16cb0`
- `0x19770`
- `0x23a80`
- `0x23ee0`

## string_xrefs

- `0x23ac5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23ad5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23aed`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23b05`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23b1d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23b35`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23b55`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23b6b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23b90`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23bb0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23bc7`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23bf0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23c08`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23c20`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23c36`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23c5a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23c71`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23c9c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23cb4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23ccc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23ce4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23cfc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23d14`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23d2c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23d44`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23d5c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23d74`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23d8c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23da4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23dbc`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23dd4`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23dec`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23e04`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23e1c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23e32`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23e48`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23e60`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23e84`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23e9b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23ec6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x23beb`: `createdby`
- `0x23c03`: `createdon`
- `0x23d0f`: `overriddencreatedon`
- `0x23d9f`: `scheduledend`
- `0x23db7`: `scheduledstart`
- `0x23dcf`: `serviceid`
- `0x23cc7`: `isworkflowcreated`
- `0x23d87`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x23a80  ldarg.3
0x23a81  brtrue.s loc_23A90
0x23a83  ldarg.s  4
0x23a85  brfalse.s loc_23A8F
0x23a87  ldarg.0
0x23a88  ldarg.1
0x23a89  ldarg.2
0x23a8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x23a8f  ret
0x23a90  ldarg.s  5
0x23a92  brtrue.s loc_23AB0
0x23a94  ldarg.3
0x23a95  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x23a9a  stloc.0
0x23a9b  ldloc.0
0x23a9c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter
0x23aa1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23aa6  beq.s    loc_23AB0
0x23aa8  ldarg.0
0x23aa9  ldarg.3
0x23aaa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x23aaf  throw
0x23ab0  ldarg.0
0x23ab1  ldarg.1
0x23ab2  ldarg.2
0x23ab3  ldarg.3
0x23ab4  ldc.i4.0
0x23ab5  ldnull
0x23ab6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x23abb  ldarg.s  5
0x23abd  brfalse.s loc_23ACF
0x23abf  ldarg.0
0x23ac0  ldstr    aLetter// "letter"
0x23ac5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23aca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x23acf  ldarg.0
0x23ad0  ldstr    aActivityid_0// "activityid"
0x23ad5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23ada  ldarg.3
0x23adb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_activityid()
0x23ae0  ldc.i4.0
0x23ae1  ldc.i4.0
0x23ae2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x23ae7  ldarg.0
0x23ae8  ldstr    aActualduration// "actualdurationminutes"
0x23aed  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23af2  ldarg.3
0x23af3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_actualdurationminutes()
0x23af8  ldc.i4.0
0x23af9  ldc.i4.0
0x23afa  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x23aff  ldarg.0
0x23b00  ldstr    aActualend// "actualend"
0x23b05  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23b0a  ldarg.3
0x23b0b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_actualend()
0x23b10  ldc.i4.0
0x23b11  ldc.i4.0
0x23b12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23b17  ldarg.0
0x23b18  ldstr    aActualstart// "actualstart"
0x23b1d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23b22  ldarg.3
0x23b23  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_actualstart()
0x23b28  ldc.i4.0
0x23b29  ldc.i4.0
0x23b2a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23b2f  ldarg.0
0x23b30  ldstr    aAddress// "address"
0x23b35  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23b3a  ldarg.3
0x23b3b  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_address()
0x23b40  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x23b45  ldarg.3
0x23b46  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_bcc()
0x23b4b  stloc.1
0x23b4c  ldloc.1
0x23b4d  brfalse.s loc_23B8A
0x23b4f  ldarg.0
0x23b50  ldstr    aBcc// "bcc"
0x23b55  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23b5a  ldnull
0x23b5b  ldc.i4.0
0x23b5c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x23b61  ldc.i4.0
0x23b62  stloc.2
0x23b63  br.s     loc_23B7E
0x23b65  ldarg.0
0x23b66  ldstr    aActivityparty// "activityparty"
0x23b6b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23b70  ldloc.1
0x23b71  ldloc.2
0x23b72  ldelem.ref
0x23b73  ldc.i4.0
0x23b74  ldc.i4.0
0x23b75  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x23b7a  ldloc.2
0x23b7b  ldc.i4.1
0x23b7c  add
0x23b7d  stloc.2
0x23b7e  ldloc.2
0x23b7f  ldloc.1
0x23b80  ldlen
0x23b81  conv.i4
0x23b82  blt.s    loc_23B65
0x23b84  ldarg.0
0x23b85  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x23b8a  ldarg.0
0x23b8b  ldstr    aCategory// "category"
0x23b90  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23b95  ldarg.3
0x23b96  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_category()
0x23b9b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x23ba0  ldarg.3
0x23ba1  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_cc()
0x23ba6  stloc.3
0x23ba7  ldloc.3
0x23ba8  brfalse.s loc_23BEA
0x23baa  ldarg.0
0x23bab  ldstr    aCc// "cc"
0x23bb0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23bb5  ldnull
0x23bb6  ldc.i4.0
0x23bb7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x23bbc  ldc.i4.0
0x23bbd  stloc.s  4
0x23bbf  br.s     loc_23BDD
0x23bc1  ldarg.0
0x23bc2  ldstr    aActivityparty// "activityparty"
0x23bc7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23bcc  ldloc.3
0x23bcd  ldloc.s  4
0x23bcf  ldelem.ref
0x23bd0  ldc.i4.0
0x23bd1  ldc.i4.0
0x23bd2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x23bd7  ldloc.s  4
0x23bd9  ldc.i4.1
0x23bda  add
0x23bdb  stloc.s  4
0x23bdd  ldloc.s  4
0x23bdf  ldloc.3
0x23be0  ldlen
0x23be1  conv.i4
0x23be2  blt.s    loc_23BC1
0x23be4  ldarg.0
0x23be5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x23bea  ldarg.0
0x23beb  ldstr    aCreatedby// "createdby"
0x23bf0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23bf5  ldarg.3
0x23bf6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_createdby()
0x23bfb  ldc.i4.0
0x23bfc  ldc.i4.0
0x23bfd  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23c02  ldarg.0
0x23c03  ldstr    aCreatedon// "createdon"
0x23c08  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23c0d  ldarg.3
0x23c0e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_createdon()
0x23c13  ldc.i4.0
0x23c14  ldc.i4.0
0x23c15  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23c1a  ldarg.0
0x23c1b  ldstr    aDescription_0// "description"
0x23c20  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23c25  ldarg.3
0x23c26  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_description()
0x23c2b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x23c30  ldarg.0
0x23c31  ldstr    aDirectioncode// "directioncode"
0x23c36  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23c3b  ldarg.3
0x23c3c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_directioncode()
0x23c41  ldc.i4.0
0x23c42  ldc.i4.0
0x23c43  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x23c48  ldarg.3
0x23c49  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_from()
0x23c4e  stloc.s  5
0x23c50  ldloc.s  5
0x23c52  brfalse.s loc_23C96
0x23c54  ldarg.0
0x23c55  ldstr    aFrom_0// "from"
0x23c5a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23c5f  ldnull
0x23c60  ldc.i4.0
0x23c61  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x23c66  ldc.i4.0
0x23c67  stloc.s  6
0x23c69  br.s     loc_23C88
0x23c6b  ldarg.0
0x23c6c  ldstr    aActivityparty// "activityparty"
0x23c71  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23c76  ldloc.s  5
0x23c78  ldloc.s  6
0x23c7a  ldelem.ref
0x23c7b  ldc.i4.0
0x23c7c  ldc.i4.0
0x23c7d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write159_activityparty(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.activityparty o, bool isNullable, bool needType)
0x23c82  ldloc.s  6
0x23c84  ldc.i4.1
0x23c85  add
0x23c86  stloc.s  6
0x23c88  ldloc.s  6
0x23c8a  ldloc.s  5
0x23c8c  ldlen
0x23c8d  conv.i4
0x23c8e  blt.s    loc_23C6B
0x23c90  ldarg.0
0x23c91  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x23c96  ldarg.0
0x23c97  ldstr    aImportsequence// "importsequencenumber"
0x23c9c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23ca1  ldarg.3
0x23ca2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_importsequencenumber()
0x23ca7  ldc.i4.0
0x23ca8  ldc.i4.0
0x23ca9  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x23cae  ldarg.0
0x23caf  ldstr    aIsbilled// "isbilled"
0x23cb4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23cb9  ldarg.3
0x23cba  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_isbilled()
0x23cbf  ldc.i4.0
0x23cc0  ldc.i4.0
0x23cc1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x23cc6  ldarg.0
0x23cc7  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x23ccc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23cd1  ldarg.3
0x23cd2  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_isworkflowcreated()
0x23cd7  ldc.i4.0
0x23cd8  ldc.i4.0
0x23cd9  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x23cde  ldarg.0
0x23cdf  ldstr    aModifiedby// "modifiedby"
0x23ce4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23ce9  ldarg.3
0x23cea  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_modifiedby()
0x23cef  ldc.i4.0
0x23cf0  ldc.i4.0
0x23cf1  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23cf6  ldarg.0
0x23cf7  ldstr    aModifiedon// "modifiedon"
0x23cfc  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23d01  ldarg.3
0x23d02  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_modifiedon()
0x23d07  ldc.i4.0
0x23d08  ldc.i4.0
0x23d09  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23d0e  ldarg.0
0x23d0f  ldstr    aOverriddencrea// "overriddencreatedon"
0x23d14  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23d19  ldarg.3
0x23d1a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_overriddencreatedon()
0x23d1f  ldc.i4.0
0x23d20  ldc.i4.0
0x23d21  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write128_CrmDateTime(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDateTime o, bool isNullable, bool needType)
0x23d26  ldarg.0
0x23d27  ldstr    aOwnerid// "ownerid"
0x23d2c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23d31  ldarg.3
0x23d32  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_ownerid()
0x23d37  ldc.i4.0
0x23d38  ldc.i4.0
0x23d39  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write125_Owner(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Owner o, bool isNullable, bool needType)
0x23d3e  ldarg.0
0x23d3f  ldstr    aOwningbusiness// "owningbusinessunit"
0x23d44  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23d49  ldarg.3
0x23d4a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_owningbusinessunit()
0x23d4f  ldc.i4.0
0x23d50  ldc.i4.0
0x23d51  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23d56  ldarg.0
0x23d57  ldstr    aPrioritycode// "prioritycode"
0x23d5c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23d61  ldarg.3
0x23d62  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_prioritycode()
0x23d67  ldc.i4.0
0x23d68  ldc.i4.0
0x23d69  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write141_Picklist(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Picklist o, bool isNullable, bool needType)
0x23d6e  ldarg.0
0x23d6f  ldstr    aRegardingobjec// "regardingobjectid"
0x23d74  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23d79  ldarg.3
0x23d7a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_regardingobjectid()
0x23d7f  ldc.i4.0
0x23d80  ldc.i4.0
0x23d81  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x23d86  ldarg.0
0x23d87  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x23d8c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x23d91  ldarg.3
0x23d92  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.letter::get_scheduleddurationminutes()
0x23d97  ldc.i4.0
0x23d98  ldc.i4.0
0x23d99  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x23d9e  ldarg.0
  ... truncated ...
```
