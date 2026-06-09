# Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::GenerateXml

- ea: `0x6cd0`
- end: `0x6df1`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::GenerateXml`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6380`

## callees

- `0x6cd0`
- `0x6e00`
- `0x6e70`

## pseudocode

```c

```

## disassembly

```asm
0x6cd0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x6cd5  stloc.0
0x6cd6  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x6cdb  stloc.1
0x6cdc  ldloc.1
0x6cdd  ldc.i4.1
0x6cde  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x6ce3  ldloc.1
0x6ce4  ldc.i4.0
0x6ce5  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x6cea  ldloc.0
0x6ceb  ldloc.1
0x6cec  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x6cf1  stloc.2
0x6cf2  ldloc.2
0x6cf3  ldstr    aRelationship// "relationship"
0x6cf8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x6cfd  ldloc.2
0x6cfe  ldstr    aRelationshipid// "relationshipid"
0x6d03  ldsfld   string [mscorlib]System.String::Empty
0x6d08  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d0d  ldloc.2
0x6d0e  ldstr    aEntityrelation// "entityrelationshipid"
0x6d13  ldsfld   string [mscorlib]System.String::Empty
0x6d18  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d1d  ldloc.2
0x6d1e  ldstr    aSchemaname// "schemaname"
0x6d23  ldarg.0
0x6d24  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_schemaName
0x6d29  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d2e  ldloc.2
0x6d2f  ldstr    aManytomany// "manytomany"
0x6d34  ldarg.0
0x6d35  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_manyToMany
0x6d3a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d3f  ldloc.2
0x6d40  ldstr    aReferencedenti// "referencedentityname"
0x6d45  ldarg.0
0x6d46  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedEntityName
0x6d4b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d50  ldloc.2
0x6d51  ldstr    aReferencedinst// "referencedinstancename"
0x6d56  ldarg.0
0x6d57  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencedInstanceName
0x6d5c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d61  ldloc.2
0x6d62  ldstr    aReferencingent// "referencingentityname"
0x6d67  ldarg.0
0x6d68  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_referencingEntityName
0x6d6d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d72  ldloc.2
0x6d73  ldstr    aAttributeschem// "attributeschemaname"
0x6d78  ldarg.0
0x6d79  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_attributeSchemaName
0x6d7e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d83  ldarg.0
0x6d84  ldfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_required
0x6d89  brfalse.s loc_6D9D
0x6d8b  ldloc.2
0x6d8c  ldstr    aReqlevel// "reqlevel"
0x6d91  ldstr    aRequired// "Required"
0x6d96  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6d9b  br.s     loc_6DAD
0x6d9d  ldloc.2
0x6d9e  ldstr    aReqlevel// "reqlevel"
0x6da3  ldstr    aNone_0// "None"
0x6da8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6dad  ldloc.2
0x6dae  ldstr    aDescription// "description"
0x6db3  ldarg.0
0x6db4  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::_description
0x6db9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x6dbe  ldarg.0
0x6dbf  ldloc.2
0x6dc0  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::WriteCascadingProperties(class [System.Xml]System.Xml.XmlWriter writer)
0x6dc5  ldarg.0
0x6dc6  ldloc.2
0x6dc7  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::WriteAssociatedMenuProperties(class [System.Xml]System.Xml.XmlWriter writer)
0x6dcc  ldloc.2
0x6dcd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x6dd2  ldloc.2
0x6dd3  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x6dd8  ldloc.2
0x6dd9  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x6dde  leave.s  loc_6DEA
0x6de0  ldloc.2
0x6de1  brfalse.s loc_6DE9
0x6de3  ldloc.2
0x6de4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6de9  endfinally
0x6dea  ldloc.0
0x6deb  callvirt instance string [mscorlib]System.Object::ToString()
0x6df0  ret
```
