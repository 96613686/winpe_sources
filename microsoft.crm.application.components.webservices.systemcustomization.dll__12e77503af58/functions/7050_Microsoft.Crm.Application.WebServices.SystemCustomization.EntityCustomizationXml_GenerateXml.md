# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::GenerateXml

- ea: `0x7050`
- end: `0x7283`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::GenerateXml`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5ed0`

## callees

- `0x7050`
- `0x7290`
- `0x73f0`
- `0x7420`
- `0x7480`
- `0x7590`

## string_xrefs

- `0x70fe`: `autocreateaccessteams`
- `0x712a`: `readonlyinmobileclient`
- `0x71da`: `readingpaneenabled`
- `0x7114`: `isquickcreateenabled`

## pseudocode

```c

```

## disassembly

```asm
0x7050  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7055  stloc.0
0x7056  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x705b  stloc.1
0x705c  ldloc.1
0x705d  ldc.i4.1
0x705e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x7063  ldloc.1
0x7064  ldc.i4.0
0x7065  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x706a  ldloc.0
0x706b  ldloc.1
0x706c  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x7071  stloc.2
0x7072  ldloc.2
0x7073  ldstr    aEntity// "entity"
0x7078  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x707d  ldloc.2
0x707e  ldstr    aEntityid// "entityid"
0x7083  ldsfld   string [mscorlib]System.String::Empty
0x7088  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x708d  ldloc.2
0x708e  ldstr    aSingularname// "singularname"
0x7093  ldarg.0
0x7094  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_singularName
0x7099  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x709e  ldloc.2
0x709f  ldstr    aPluralname// "pluralname"
0x70a4  ldarg.0
0x70a5  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_pluralName
0x70aa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x70af  ldloc.2
0x70b0  ldstr    aSchemaname// "schemaname"
0x70b5  ldarg.0
0x70b6  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_schemaName
0x70bb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x70c0  ldloc.2
0x70c1  ldstr    aOwnershiptype// "ownershiptype"
0x70c6  ldarg.0
0x70c7  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_ownershipType
0x70cc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x70d1  ldloc.2
0x70d2  ldstr    aDuplicatecheck// "duplicatecheck"
0x70d7  ldarg.0
0x70d8  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_duplicateCheck
0x70dd  call     instance string [mscorlib]System.Boolean::ToString()
0x70e2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x70e7  ldloc.2
0x70e8  ldstr    aBusinessproces// "businessprocessenabled"
0x70ed  ldarg.0
0x70ee  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_businessProcessEnabled
0x70f3  call     instance string [mscorlib]System.Boolean::ToString()
0x70f8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x70fd  ldloc.2
0x70fe  ldstr    aAutocreateacce// "autocreateaccessteams"
0x7103  ldarg.0
0x7104  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_autoCreateAccessTeams
0x7109  call     instance string [mscorlib]System.Boolean::ToString()
0x710e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7113  ldloc.2
0x7114  ldstr    aIsquickcreatee// "isquickcreateenabled"
0x7119  ldarg.0
0x711a  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_isQuickCreateEnabled
0x711f  call     instance string [mscorlib]System.Boolean::ToString()
0x7124  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7129  ldloc.2
0x712a  ldstr    aReadonlyinmobi// "readonlyinmobileclient"
0x712f  ldarg.0
0x7130  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_readOnlyInMobileClient
0x7135  call     instance string [mscorlib]System.Boolean::ToString()
0x713a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x713f  ldloc.2
0x7140  ldstr    aVisibleinmobil_0// "visibleinmobileclient"
0x7145  ldarg.0
0x7146  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_visibleInMobileClient
0x714b  call     instance string [mscorlib]System.Boolean::ToString()
0x7150  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7155  ldloc.2
0x7156  ldstr    aOfflineinmobil// "offlineinmobileclient"
0x715b  ldarg.0
0x715c  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_offlineInMobileClient
0x7161  call     instance string [mscorlib]System.Boolean::ToString()
0x7166  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x716b  ldloc.2
0x716c  ldstr    aEntityisactivi// "entityisactivity"
0x7171  ldarg.0
0x7172  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_entityIsActivity
0x7177  call     instance string [mscorlib]System.Boolean::ToString()
0x717c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7181  ldloc.2
0x7182  ldstr    aMailmergecheck// "mailmergecheck"
0x7187  ldarg.0
0x7188  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_mailmergecheck
0x718d  call     instance string [mscorlib]System.Boolean::ToString()
0x7192  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7197  ldloc.2
0x7198  ldstr    aAuditenabled// "auditenabled"
0x719d  ldarg.0
0x719e  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_auditenabled
0x71a3  call     instance string [mscorlib]System.Boolean::ToString()
0x71a8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x71ad  ldloc.2
0x71ae  ldstr    aCollaboration// "collaboration"
0x71b3  ldarg.0
0x71b4  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_collaboration
0x71b9  call     instance string [mscorlib]System.Boolean::ToString()
0x71be  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x71c3  ldloc.2
0x71c4  ldstr    aAutoroutetoown// "autoroutetoownerqueue"
0x71c9  ldarg.0
0x71ca  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_autoroutetoownerqueue
0x71cf  call     instance string [mscorlib]System.Boolean::ToString()
0x71d4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x71d9  ldloc.2
0x71da  ldstr    aReadingpaneena// "readingpaneenabled"
0x71df  ldarg.0
0x71e0  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_readingPaneEnabled
0x71e5  call     instance string [mscorlib]System.Boolean::ToString()
0x71ea  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x71ef  ldloc.2
0x71f0  ldstr    aDocmgmtenabled// "docmgmtenabled"
0x71f5  ldarg.0
0x71f6  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_docMgmtEnabled
0x71fb  call     instance string [mscorlib]System.Boolean::ToString()
0x7200  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7205  ldloc.2
0x7206  ldstr    aVisibleinmobil// "visibleinmobile"
0x720b  ldarg.0
0x720c  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_visibleInMobile
0x7211  call     instance string [mscorlib]System.Boolean::ToString()
0x7216  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x721b  ldloc.2
0x721c  ldstr    aChangetracking// "changetrackingenabled"
0x7221  ldarg.0
0x7222  ldflda   bool Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_changetrackingenabled
0x7227  call     instance string [mscorlib]System.Boolean::ToString()
0x722c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7231  ldarg.0
0x7232  ldloc.2
0x7233  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::WriteDisplayProperties(class [System.Xml]System.Xml.XmlWriter writer)
0x7238  ldarg.0
0x7239  ldloc.2
0x723a  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::WriteRichClientProperties(class [System.Xml]System.Xml.XmlWriter writer)
0x723f  ldarg.0
0x7240  ldloc.2
0x7241  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::WriteAssociateProperties(class [System.Xml]System.Xml.XmlWriter writer)
0x7246  ldarg.0
0x7247  ldloc.2
0x7248  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::WriteConnectionProperties(class [System.Xml]System.Xml.XmlWriter writer)
0x724d  ldloc.2
0x724e  ldarg.0
0x724f  ldfld    class Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::_primaryField
0x7254  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::GenerateXml()
0x7259  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x725e  ldloc.2
0x725f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7264  ldloc.2
0x7265  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x726a  ldloc.2
0x726b  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x7270  leave.s  loc_727C
0x7272  ldloc.2
0x7273  brfalse.s loc_727B
0x7275  ldloc.2
0x7276  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x727b  endfinally
0x727c  ldloc.0
0x727d  callvirt instance string [mscorlib]System.Object::ToString()
0x7282  ret
```
