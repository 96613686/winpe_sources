# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::.ctor_0

- ea: `0x6f60`
- end: `0x7047`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::.ctor_0`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5ed0`

## callees

- `0x6f60`
- `0x7510`

## string_xrefs

- `0x6fb7`: `CustomizationXml/DisplayName`
- `0x6fcd`: `CustomizationXml/CollectionName`
- `0x6ffd`: `CustomizationXml/PrimaryKeyDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0x6f60  ldarg.0
0x6f61  ldsfld   string [mscorlib]System.String::Empty
0x6f66  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_singularName
0x6f6b  ldarg.0
0x6f6c  ldsfld   string [mscorlib]System.String::Empty
0x6f71  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_pluralName
0x6f76  ldarg.0
0x6f77  ldsfld   string [mscorlib]System.String::Empty
0x6f7c  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_schemaName
0x6f81  ldarg.0
0x6f82  ldstr    aUserowned// "UserOwned"
0x6f87  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_ownershipType
0x6f8c  ldarg.0
0x6f8d  ldc.i4.1
0x6f8e  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_duplicateCheck
0x6f93  ldarg.0
0x6f94  ldc.i4.1
0x6f95  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_docMgmtEnabled
0x6f9a  ldarg.0
0x6f9b  ldc.i4.1
0x6f9c  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_hasNotes
0x6fa1  ldarg.0
0x6fa2  ldc.i4.1
0x6fa3  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_hasActivities
0x6fa8  ldarg.0
0x6fa9  call     instance void [mscorlib]System.Object::.ctor()
0x6fae  ldarg.1
0x6faf  castclass [System.Xml]System.Xml.XmlNode
0x6fb4  stloc.0
0x6fb5  ldarg.0
0x6fb6  ldloc.0
0x6fb7  ldstr    aCustomizationx_1// "CustomizationXml/DisplayName"
0x6fbc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6fc1  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6fc6  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_singularName
0x6fcb  ldarg.0
0x6fcc  ldloc.0
0x6fcd  ldstr    aCustomizationx_2// "CustomizationXml/CollectionName"
0x6fd2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6fd7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6fdc  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_pluralName
0x6fe1  ldarg.0
0x6fe2  ldarg.0
0x6fe3  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_singularName
0x6fe8  ldstr    aAZaZ09// "[^a-zA-Z_0-9]"
0x6fed  ldsfld   string [mscorlib]System.String::Empty
0x6ff2  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x6ff7  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_schemaName
0x6ffc  ldloc.0
0x6ffd  ldstr    aCustomizationx_3// "CustomizationXml/PrimaryKeyDisplayName"
0x7002  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7007  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x700c  stloc.1
0x700d  ldloc.1
0x700e  ldstr    aAZaZ09// "[^a-zA-Z_0-9]"
0x7013  ldsfld   string [mscorlib]System.String::Empty
0x7018  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x701d  stloc.2
0x701e  ldloc.2
0x701f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7024  brfalse.s loc_702C
0x7026  ldstr    aPrimaryfield// "PrimaryField"
0x702b  stloc.2
0x702c  ldarg.0
0x702d  ldloc.1
0x702e  ldloc.2
0x702f  ldc.i4.1
0x7030  ldstr    aNvarchar// "nvarchar"
0x7035  ldstr    aText// "text"
0x703a  ldc.i4.s 0x64
0x703c  newobj   instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::.ctor(string displayName, string schemaName, bool required, string type, string format, int32 length)
0x7041  stfld    class Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_primaryField
0x7046  ret
```
