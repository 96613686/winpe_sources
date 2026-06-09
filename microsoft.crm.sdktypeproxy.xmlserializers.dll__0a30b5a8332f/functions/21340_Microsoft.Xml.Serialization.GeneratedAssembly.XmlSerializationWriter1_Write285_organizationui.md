# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write285_organizationui

- ea: `0x21340`
- end: `0x214d9`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write285_organizationui`
- size: `409`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x19ce0`
- `0x36910`
- `0x55da0`

## callees

- `0x5e50`
- `0x15020`
- `0x15180`
- `0x15320`
- `0x153c0`
- `0x167c0`
- `0x21340`

## string_xrefs

- `0x21385`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21395`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x213ad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x213c3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x213db`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x213f3`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21409`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2141f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21437`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2144d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21465`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x2147d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x21493`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x214a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x214bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x213a8`: `fieldxml`
- `0x213ee`: `formxml`
- `0x2148e`: `previewcolumnsetxml`
- `0x214a4`: `previewxml`

## pseudocode

```c

```

## disassembly

```asm
0x21340  ldarg.3
0x21341  brtrue.s loc_21350
0x21343  ldarg.s  4
0x21345  brfalse.s loc_2134F
0x21347  ldarg.0
0x21348  ldarg.1
0x21349  ldarg.2
0x2134a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x2134f  ret
0x21350  ldarg.s  5
0x21352  brtrue.s loc_21370
0x21354  ldarg.3
0x21355  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2135a  stloc.0
0x2135b  ldloc.0
0x2135c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui
0x21361  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21366  beq.s    loc_21370
0x21368  ldarg.0
0x21369  ldarg.3
0x2136a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x2136f  throw
0x21370  ldarg.0
0x21371  ldarg.1
0x21372  ldarg.2
0x21373  ldarg.3
0x21374  ldc.i4.0
0x21375  ldnull
0x21376  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x2137b  ldarg.s  5
0x2137d  brfalse.s loc_2138F
0x2137f  ldarg.0
0x21380  ldstr    aOrganizationui// "organizationui"
0x21385  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2138a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x2138f  ldarg.0
0x21390  ldstr    aCustomizationl// "customizationlevel"
0x21395  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2139a  ldarg.3
0x2139b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_customizationlevel()
0x213a0  ldc.i4.0
0x213a1  ldc.i4.0
0x213a2  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x213a7  ldarg.0
0x213a8  ldstr    aFieldxml// "fieldxml"
0x213ad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x213b2  ldarg.3
0x213b3  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_fieldxml()
0x213b8  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x213bd  ldarg.0
0x213be  ldstr    aFormid// "formid"
0x213c3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x213c8  ldarg.3
0x213c9  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_formid()
0x213ce  ldc.i4.0
0x213cf  ldc.i4.0
0x213d0  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write149_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x213d5  ldarg.0
0x213d6  ldstr    aFormidunique// "formidunique"
0x213db  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x213e0  ldarg.3
0x213e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_formidunique()
0x213e6  ldc.i4.0
0x213e7  ldc.i4.0
0x213e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write147_UniqueIdentifier(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.UniqueIdentifier o, bool isNullable, bool needType)
0x213ed  ldarg.0
0x213ee  ldstr    aFormxml// "formxml"
0x213f3  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x213f8  ldarg.3
0x213f9  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_formxml()
0x213fe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x21403  ldarg.0
0x21404  ldstr    aGridicon// "gridicon"
0x21409  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2140e  ldarg.3
0x2140f  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_gridicon()
0x21414  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x21419  ldarg.0
0x2141a  ldstr    aInproduction// "inproduction"
0x2141f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21424  ldarg.3
0x21425  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_inproduction()
0x2142a  ldc.i4.0
0x2142b  ldc.i4.0
0x2142c  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write151_CrmBoolean(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmBoolean o, bool isNullable, bool needType)
0x21431  ldarg.0
0x21432  ldstr    aLargeentityico// "largeentityicon"
0x21437  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2143c  ldarg.3
0x2143d  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_largeentityicon()
0x21442  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x21447  ldarg.0
0x21448  ldstr    aObjecttypecode_0// "objecttypecode"
0x2144d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21452  ldarg.3
0x21453  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_objecttypecode()
0x21458  ldc.i4.0
0x21459  ldc.i4.0
0x2145a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write135_EntityNameReference(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference o, bool isNullable, bool needType)
0x2145f  ldarg.0
0x21460  ldstr    aOrganizationid// "organizationid"
0x21465  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x2146a  ldarg.3
0x2146b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_organizationid()
0x21470  ldc.i4.0
0x21471  ldc.i4.0
0x21472  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write126_Lookup(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup o, bool isNullable, bool needType)
0x21477  ldarg.0
0x21478  ldstr    aOutlookshortcu// "outlookshortcuticon"
0x2147d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21482  ldarg.3
0x21483  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_outlookshortcuticon()
0x21488  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x2148d  ldarg.0
0x2148e  ldstr    aPreviewcolumns// "previewcolumnsetxml"
0x21493  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x21498  ldarg.3
0x21499  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_previewcolumnsetxml()
0x2149e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x214a3  ldarg.0
0x214a4  ldstr    aPreviewxml// "previewxml"
0x214a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x214ae  ldarg.3
0x214af  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_previewxml()
0x214b4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x214b9  ldarg.0
0x214ba  ldstr    aVersion// "version"
0x214bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x214c4  ldarg.3
0x214c5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.organizationui::get_version()
0x214ca  ldc.i4.0
0x214cb  ldc.i4.0
0x214cc  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write153_CrmNumber(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber o, bool isNullable, bool needType)
0x214d1  ldarg.0
0x214d2  ldarg.3
0x214d3  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x214d8  ret
```
