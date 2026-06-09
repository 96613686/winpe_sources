# Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UploadReportCategory

- ea: `0x15e10`
- end: `0x15fff`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UploadReportCategory`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15240`

## callees

- `0x15e10`

## pseudocode

```c

```

## disassembly

```asm
0x15e10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15e15  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x15e1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x15e1f  stloc.0
0x15e20  ldloc.0
0x15e21  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15e26  ldc.i4   0x238E
0x15e2b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x15e30  stloc.1
0x15e31  ldloc.1
0x15e32  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x15e37  ldstr    aCategorycode// "categorycode"
0x15e3c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x15e41  stloc.2
0x15e42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15e47  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x15e4c  stloc.s  4
0x15e4e  ldloc.s  4
0x15e50  ldc.i4.0
0x15e51  call     class [System.Xml]System.Xml.XmlWriter [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlWriter(class [mscorlib]System.IO.TextWriter, bool)
0x15e56  stloc.s  5
0x15e58  ldloc.s  5
0x15e5a  ldstr    aAttribute// "attribute"
0x15e5f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x15e64  ldloc.s  5
0x15e66  ldstr    aEntityid_1// "entityid"
0x15e6b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x15e70  ldloc.s  5
0x15e72  ldloc.1
0x15e73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x15e78  stloc.s  7
0x15e7a  ldloca.s 7
0x15e7c  ldstr    aB// "B"
0x15e81  call     instance string [mscorlib]System.Guid::ToString(string)
0x15e86  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x15e8b  ldloc.s  5
0x15e8d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x15e92  ldloc.s  5
0x15e94  ldstr    aAttributeid// "attributeid"
0x15e99  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x15e9e  ldloc.s  5
0x15ea0  ldloc.2
0x15ea1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x15ea6  stloc.s  7
0x15ea8  ldloca.s 7
0x15eaa  ldstr    aB// "B"
0x15eaf  call     instance string [mscorlib]System.Guid::ToString(string)
0x15eb4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x15eb9  ldloc.s  5
0x15ebb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x15ec0  ldloc.s  5
0x15ec2  ldstr    aDisplayname// "displayname"
0x15ec7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x15ecc  ldloc.2
0x15ecd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x15ed2  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x15ed7  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x15edc  ldloc.0
0x15edd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15ee2  stloc.s  6
0x15ee4  ldloc.s  5
0x15ee6  ldloc.s  6
0x15ee8  brfalse.s loc_15EF3
0x15eea  ldloc.s  6
0x15eec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x15ef1  br.s     loc_15EF8
0x15ef3  ldsfld   string [mscorlib]System.String::Empty
0x15ef8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x15efd  ldloc.s  5
0x15eff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x15f04  ldloc.s  5
0x15f06  ldstr    aImemode// "imemode"
0x15f0b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x15f10  ldloc.s  5
0x15f12  ldloc.2
0x15f13  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeImeModeId()
0x15f18  stloc.s  8
0x15f1a  ldloca.s 8
0x15f1c  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode
0x15f22  callvirt instance string [mscorlib]System.Object::ToString()
0x15f27  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x15f2c  ldloc.s  5
0x15f2e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x15f33  ldloc.s  5
0x15f35  ldstr    aReqlevel// "reqlevel"
0x15f3a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x15f3f  ldloc.s  5
0x15f41  ldloc.2
0x15f42  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_AttributeRequiredLevelId()
0x15f47  stloc.s  9
0x15f49  ldloca.s 9
0x15f4b  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel
0x15f51  callvirt instance string [mscorlib]System.Object::ToString()
0x15f56  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteValue(string)
0x15f5b  ldloc.s  5
0x15f5d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x15f62  ldloc.s  5
0x15f64  ldstr    aType_0// "type"
0x15f69  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x15f6e  ldloc.s  5
0x15f70  ldarg.1
0x15f71  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x15f76  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x15f7b  ldloc.s  5
0x15f7d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x15f82  ldloc.s  5
0x15f84  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x15f89  leave.s  loc_15F97
0x15f8b  ldloc.s  5
0x15f8d  brfalse.s loc_15F96
0x15f8f  ldloc.s  5
0x15f91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15f96  endfinally
0x15f97  ldloc.s  4
0x15f99  callvirt instance string [mscorlib]System.Object::ToString()
0x15f9e  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x15fa3  stloc.3
0x15fa4  leave.s  loc_15FB2
0x15fa6  ldloc.s  4
0x15fa8  brfalse.s loc_15FB1
0x15faa  ldloc.s  4
0x15fac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15fb1  endfinally
0x15fb2  newobj   instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::.ctor()
0x15fb7  stloc.s  0xA
0x15fb9  ldloc.s  0xA
0x15fbb  ldloc.3
0x15fbc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x15fc1  callvirt instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateAttribute(class [System.Xml]System.Xml.XmlNode)
0x15fc6  ldstr    aPublishEntitie// "<publish><entities><entity>"
0x15fcb  ldloc.1
0x15fcc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x15fd1  ldstr    aEntityEntities// "</entity></entities></publish>"
0x15fd6  call     string [mscorlib]System.String::Concat(string, string, string)
0x15fdb  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x15fe0  stloc.s  0xB
0x15fe2  ldloc.s  0xA
0x15fe4  ldloc.s  0xB
0x15fe6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x15feb  callvirt instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::PublishCustomizations(class [System.Xml]System.Xml.XmlNode)
0x15ff0  leave.s  loc_15FFE
0x15ff2  ldloc.s  0xA
0x15ff4  brfalse.s loc_15FFD
0x15ff6  ldloc.s  0xA
0x15ff8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15ffd  endfinally
0x15ffe  ret
```
