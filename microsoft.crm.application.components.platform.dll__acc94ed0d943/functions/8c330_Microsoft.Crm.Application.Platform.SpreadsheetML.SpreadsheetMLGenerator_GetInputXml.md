# Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::GetInputXml

- ea: `0x8c330`
- end: `0x8c52d`
- name: `Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::GetInputXml`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8c1f0`

## callees

- `0x2fb90`
- `0x2fbc0`
- `0x3aa00`
- `0x8c330`
- `0x8c530`
- `0x8c700`
- `0x8c780`
- `0x8c7d0`
- `0x8d3e0`
- `0x8d3f0`
- `0x8d400`
- `0x8d410`
- `0x8d420`
- `0x8d520`

## string_xrefs

- `0x8c353`: `ImportTemplate`
- `0x8c35e`: `SpreadsheetExportMode`

## pseudocode

```c

```

## disassembly

```asm
0x8c330  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x8c335  stloc.0
0x8c336  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x8c33b  stloc.1
0x8c33c  ldloc.1
0x8c33d  ldc.i4.1
0x8c33e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x8c343  ldloc.1
0x8c344  ldc.i4.0
0x8c345  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x8c34a  ldloc.0
0x8c34b  ldloc.1
0x8c34c  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x8c351  stloc.2
0x8c352  ldloc.2
0x8c353  ldstr    aImporttemplate// "ImportTemplate"
0x8c358  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x8c35d  ldloc.2
0x8c35e  ldstr    aSpreadsheetexp// "SpreadsheetExportMode"
0x8c363  ldarg.0
0x8c364  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c369  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetExportMode Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_SpreadsheetMode()
0x8c36e  stloc.s  4
0x8c370  ldloca.s 4
0x8c372  constrained. [Microsoft.Crm]Microsoft.Crm.SpreadsheetExportMode
0x8c378  callvirt instance string [mscorlib]System.Object::ToString()
0x8c37d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x8c382  ldloc.2
0x8c383  ldstr    aProtected// "Protected"
0x8c388  ldarg.0
0x8c389  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c38e  callvirt instance bool Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_IsProtected()
0x8c393  stloc.s  5
0x8c395  ldloca.s 5
0x8c397  call     instance string [mscorlib]System.Boolean::ToString()
0x8c39c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x8c3a1  ldloc.2
0x8c3a2  ldstr    aRighttoleft// "RightToLeft"
0x8c3a7  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8c3ac  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x8c3b1  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x8c3b6  stloc.s  5
0x8c3b8  ldloca.s 5
0x8c3ba  call     instance string [mscorlib]System.Boolean::ToString()
0x8c3bf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x8c3c4  ldarg.0
0x8c3c5  ldloc.2
0x8c3c6  call     instance void Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillMiscDetails(class [System.Xml]System.Xml.XmlWriter writer)
0x8c3cb  ldloc.2
0x8c3cc  ldstr    aEntity_0// "Entity"
0x8c3d1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x8c3d6  ldloc.2
0x8c3d7  ldstr    aLogicalname_0// "LogicalName"
0x8c3dc  ldarg.0
0x8c3dd  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c3e2  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_EntityLogicalName()
0x8c3e7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x8c3ec  ldloc.2
0x8c3ed  ldstr    aSheetname// "SheetName"
0x8c3f2  ldarg.0
0x8c3f3  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c3f8  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_SheetName()
0x8c3fd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x8c402  ldarg.0
0x8c403  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c408  callvirt instance bool Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_IsHeaderChecksumRequired()
0x8c40d  brfalse.s loc_8C481
0x8c40f  ldarg.0
0x8c410  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties> Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_attributePropertiesList
0x8c415  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::get_Count()
0x8c41a  newarr   [mscorlib]System.String
0x8c41f  stloc.s  6
0x8c421  ldc.i4.0
0x8c422  stloc.s  7
0x8c424  ldarg.0
0x8c425  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties> Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_attributePropertiesList
0x8c42a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::GetEnumerator()
0x8c42f  stloc.s  9
0x8c431  br.s     loc_8C44D
0x8c433  ldloca.s 9
0x8c435  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::get_Current()
0x8c43a  stloc.s  0xA
0x8c43c  ldloc.s  6
0x8c43e  ldloc.s  7
0x8c440  dup
0x8c441  ldc.i4.1
0x8c442  add
0x8c443  stloc.s  7
0x8c445  ldloc.s  0xA
0x8c447  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties::get_DisplayName()
0x8c44c  stelem.ref
0x8c44d  ldloca.s 9
0x8c44f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::MoveNext()
0x8c454  brtrue.s loc_8C433
0x8c456  leave.s  loc_8C466
0x8c458  ldloca.s 9
0x8c45a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>
0x8c460  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c465  endfinally
0x8c466  call     class [Microsoft.Crm]Microsoft.Crm.IChecksumGenerator [Microsoft.Crm]Microsoft.Crm.ChecksumGenerator::get_Instance()
0x8c46b  ldloc.s  6
0x8c46d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.IChecksumGenerator::GenerateChecksum(class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x8c472  stloc.s  8
0x8c474  ldloc.2
0x8c475  ldstr    aHeaderchecksum// "HeaderChecksum"
0x8c47a  ldloc.s  8
0x8c47c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8c481  ldarg.0
0x8c482  ldloc.2
0x8c483  call     instance void Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillDuplicateColumnDetails(class [System.Xml]System.Xml.XmlWriter writer)
0x8c488  ldarg.0
0x8c489  ldloc.2
0x8c48a  call     instance void Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillNonImportableColumnDetails(class [System.Xml]System.Xml.XmlWriter writer)
0x8c48f  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c494  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8c499  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8c49e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8c4a3  ldarg.0
0x8c4a4  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c4a9  callvirt instance string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_EntityLogicalName()
0x8c4ae  ldc.i4.1
0x8c4af  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x8c4b4  stloc.3
0x8c4b5  ldc.i4.0
0x8c4b6  stloc.s  0xB
0x8c4b8  br.s     loc_8C4F3
0x8c4ba  ldarg.0
0x8c4bb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties> Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_attributePropertiesList
0x8c4c0  ldloc.s  0xB
0x8c4c2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::get_Item(!!T0)
0x8c4c7  stloc.s  0xC
0x8c4c9  ldloc.s  0xB
0x8c4cb  ldc.i4.3
0x8c4cc  bne.un.s loc_8C4DE
0x8c4ce  ldarg.0
0x8c4cf  ldfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c4d4  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.SpreadsheetExportMode Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties::get_SpreadsheetMode()
0x8c4d9  ldc.i4.1
0x8c4da  ceq
0x8c4dc  br.s     loc_8C4DF
0x8c4de  ldc.i4.0
0x8c4df  stloc.s  0xD
0x8c4e1  ldarg.0
0x8c4e2  ldloc.2
0x8c4e3  ldloc.s  0xC
0x8c4e5  ldloc.3
0x8c4e6  ldloc.s  0xD
0x8c4e8  call     instance void Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::FillAttributeDetails(class [System.Xml]System.Xml.XmlWriter writer, class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties attributeProperties, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, bool fillBackground)
0x8c4ed  ldloc.s  0xB
0x8c4ef  ldc.i4.1
0x8c4f0  add
0x8c4f1  stloc.s  0xB
0x8c4f3  ldloc.s  0xB
0x8c4f5  ldarg.0
0x8c4f6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties> Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_attributePropertiesList
0x8c4fb  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties>::get_Count()
0x8c500  blt.s    loc_8C4BA
0x8c502  ldloc.2
0x8c503  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x8c508  ldloc.2
0x8c509  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x8c50e  ldloc.2
0x8c50f  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x8c514  ldloc.2
0x8c515  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x8c51a  leave.s  loc_8C526
0x8c51c  ldloc.2
0x8c51d  brfalse.s loc_8C525
0x8c51f  ldloc.2
0x8c520  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8c525  endfinally
0x8c526  ldloc.0
0x8c527  callvirt instance string [mscorlib]System.Object::ToString()
0x8c52c  ret
```
