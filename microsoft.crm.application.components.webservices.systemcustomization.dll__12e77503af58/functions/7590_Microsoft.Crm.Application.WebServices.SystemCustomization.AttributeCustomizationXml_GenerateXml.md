# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::GenerateXml

- ea: `0x7590`
- end: `0x768b`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::GenerateXml`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7050`

## callees

- `0x7590`
- `0x7690`

## pseudocode

```c

```

## disassembly

```asm
0x7590  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7595  stloc.0
0x7596  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x759b  stloc.1
0x759c  ldloc.1
0x759d  ldc.i4.1
0x759e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x75a3  ldloc.1
0x75a4  ldc.i4.0
0x75a5  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x75aa  ldloc.0
0x75ab  ldloc.1
0x75ac  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x75b1  stloc.2
0x75b2  ldloc.2
0x75b3  ldstr    aAttribute// "attribute"
0x75b8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x75bd  ldsfld   string [mscorlib]System.String::Empty
0x75c2  stloc.3
0x75c3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x75c8  ldarg.0
0x75c9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::_entityId
0x75ce  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x75d3  brfalse.s loc_75E6
0x75d5  ldarg.0
0x75d6  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::_entityId
0x75db  ldstr    aB// "B"
0x75e0  call     instance string [mscorlib]System.Guid::ToString(string)
0x75e5  stloc.3
0x75e6  ldloc.2
0x75e7  ldstr    aEntityid// "entityid"
0x75ec  ldloc.3
0x75ed  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x75f2  ldloc.2
0x75f3  ldstr    aAttributeid// "attributeid"
0x75f8  ldsfld   string [mscorlib]System.String::Empty
0x75fd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7602  ldloc.2
0x7603  ldstr    aDisplayname// "displayname"
0x7608  ldarg.0
0x7609  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::_displayName
0x760e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7613  ldloc.2
0x7614  ldstr    aSchemaname// "schemaname"
0x7619  ldarg.0
0x761a  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::_schemaName
0x761f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7624  ldarg.0
0x7625  ldfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::_required
0x762a  brfalse.s loc_763E
0x762c  ldloc.2
0x762d  ldstr    aReqlevel// "reqlevel"
0x7632  ldstr    aRequired// "Required"
0x7637  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x763c  br.s     loc_764E
0x763e  ldloc.2
0x763f  ldstr    aReqlevel// "reqlevel"
0x7644  ldstr    aNone_0// "None"
0x7649  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x764e  ldloc.2
0x764f  ldstr    aImemode// "imemode"
0x7654  ldarg.0
0x7655  ldfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::_imeMode
0x765a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x765f  ldarg.0
0x7660  ldloc.2
0x7661  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::WriteTypeInfo(class [System.Xml]System.Xml.XmlWriter writer)
0x7666  ldloc.2
0x7667  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x766c  ldloc.2
0x766d  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x7672  ldloc.2
0x7673  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x7678  leave.s  loc_7684
0x767a  ldloc.2
0x767b  brfalse.s loc_7683
0x767d  ldloc.2
0x767e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7683  endfinally
0x7684  ldloc.0
0x7685  callvirt instance string [mscorlib]System.Object::ToString()
0x768a  ret
```
