# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetImportMapXmlWithAutoMapping

- ea: `0x613b0`
- end: `0x61695`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetImportMapXmlWithAutoMapping`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x60e70`

## callees

- `0x11760`
- `0x30260`
- `0x30870`
- `0x5be20`
- `0x5fb00`
- `0x5fb80`
- `0x5fc50`
- `0x5fc60`
- `0x5fc90`
- `0x60f70`
- `0x613b0`
- `0x616a0`
- `0x61e90`
- `0x63be0`
- `0x63c40`
- `0x66ae0`
- `0x66e20`
- `0x6a810`

## string_xrefs

- `0x61457`: `Only one file allowed for update mode`
- `0x6149d`: `ImportWizard.TemporaryMap.Name`
- `0x614f4`: `ImportWizard.TemporaryMap.Description`

## pseudocode

```c

```

## disassembly

```asm
0x613b0  ldarg.1
0x613b1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.ImportWizardState::get_OriginalImportFileId()
0x613b6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x613bb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x613c0  brfalse.s loc_613D4
0x613c2  ldarg.0
0x613c3  ldarg.1
0x613c4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.ImportWizardState::get_OriginalImportFileId()
0x613c9  ldarg.1
0x613ca  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x613cf  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::CleanupReplicatedImportFiles(valuetype [mscorlib]System.Guid originalImportFileId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x613d4  ldarg.1
0x613d5  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportType()
0x613da  ldc.i4.2
0x613db  beq.s    loc_613F1
0x613dd  ldarg.1
0x613de  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportType()
0x613e3  ldc.i4.4
0x613e4  beq.s    loc_613F1
0x613e6  ldarg.1
0x613e7  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportType()
0x613ec  ldc.i4.5
0x613ed  ceq
0x613ef  br.s     loc_613F2
0x613f1  ldc.i4.1
0x613f2  stloc.0
0x613f3  ldstr    aImportfile// "importfile"
0x613f8  ldarg.1
0x613f9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x613fe  call     class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityType::Create(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x61403  newobj   instance void Microsoft.Crm.Application.Platform.ImportFile::.ctor(class Microsoft.Crm.Application.Platform.EntityType type)
0x61408  ldarg.1
0x61409  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportId()
0x6140e  ldc.i4.5
0x6140f  newarr   [mscorlib]System.String
0x61414  dup
0x61415  ldc.i4.0
0x61416  ldstr    aName// "name"
0x6141b  stelem.ref
0x6141c  dup
0x6141d  ldc.i4.1
0x6141e  ldstr    aSource// "source"
0x61423  stelem.ref
0x61424  dup
0x61425  ldc.i4.2
0x61426  ldstr    aSourceentityna// "sourceentityname"
0x6142b  stelem.ref
0x6142c  dup
0x6142d  ldc.i4.3
0x6142e  ldstr    aImportfileid// "importfileid"
0x61433  stelem.ref
0x61434  dup
0x61435  ldc.i4.4
0x61436  ldstr    aTargetentityna// "targetentityname"
0x6143b  stelem.ref
0x6143c  call     instance class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.ImportFile::RetrieveImportFiles(valuetype [mscorlib]System.Guid importId, string[] columns)
0x61441  stloc.1
0x61442  ldarg.0
0x61443  ldarg.1
0x61444  call     instance bool Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::IsOrContainsXlsx(class Microsoft.Crm.Application.Platform.ImportWizardState wizardState)
0x61449  brtrue.s loc_61462
0x6144b  ldloc.0
0x6144c  brfalse.s loc_61462
0x6144e  ldloc.1
0x6144f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x61454  ldc.i4.1
0x61455  beq.s    loc_61462
0x61457  ldstr    aOnlyOneFileAll// "Only one file allowed for update mode"
0x6145c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x61461  throw
0x61462  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x61467  stloc.2
0x61468  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x6146d  stloc.3
0x6146e  ldloc.3
0x6146f  ldc.i4.1
0x61470  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x61475  ldloc.3
0x61476  ldc.i4.0
0x61477  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x6147c  ldloc.2
0x6147d  ldloc.3
0x6147e  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x61483  stloc.s  4
0x61485  ldloc.s  4
0x61487  ldstr    aMap// "Map"
0x6148c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x61491  ldloc.s  4
0x61493  ldstr    aName_0// "Name"
0x61498  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6149d  ldstr    aImportwizardTe// "ImportWizard.TemporaryMap.Name"
0x614a2  ldarg.1
0x614a3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x614a8  ldc.i4.1
0x614a9  newarr   [mscorlib]System.Object
0x614ae  dup
0x614af  ldc.i4.0
0x614b0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x614b5  stloc.s  6
0x614b7  ldloca.s 6
0x614b9  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x614be  stloc.s  7
0x614c0  ldloca.s 7
0x614c2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x614c7  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x614cc  stelem.ref
0x614cd  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, object[] arguments)
0x614d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x614d7  ldloc.s  4
0x614d9  ldstr    aSource_0// "Source"
0x614de  ldstr    aImport_0// "Import"
0x614e3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x614e8  ldloc.s  4
0x614ea  ldstr    aDescription_1// "Description"
0x614ef  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x614f4  ldstr    aImportwizardTe_0// "ImportWizard.TemporaryMap.Description"
0x614f9  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x614fe  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x61503  ldloc.s  4
0x61505  ldstr    aEntitymaps// "EntityMaps"
0x6150a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x6150f  ldc.i4.1
0x61510  stloc.s  5
0x61512  ldloc.1
0x61513  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x61518  stloc.s  8
0x6151a  br       loc_6164A
0x6151f  ldloc.s  8
0x61521  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x61526  stloc.s  9
0x61528  ldloc.s  4
0x6152a  ldstr    aEntitymap_0// "EntityMap"
0x6152f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x61534  ldloc.s  9
0x61536  ldstr    aSourceentityna// "sourceentityname"
0x6153b  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x61540  castclass [mscorlib]System.String
0x61545  stloc.s  0xA
0x61547  ldloc.s  4
0x61549  ldstr    aInputfilename// "InputFileName"
0x6154e  ldloc.s  9
0x61550  ldstr    aSource// "source"
0x61555  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6155a  castclass [mscorlib]System.String
0x6155f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x61564  ldloc.s  4
0x61566  ldstr    aInputfileid// "InputFileId"
0x6156b  ldstr    aFile// "file_"
0x61570  ldloc.s  5
0x61572  box      [mscorlib]System.Int32
0x61577  call     string [mscorlib]System.String::Concat(object, object)
0x6157c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x61581  ldloc.s  4
0x61583  ldstr    aSourceentityna_0// "SourceEntityName"
0x61588  ldloc.s  0xA
0x6158a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x6158f  ldarg.0
0x61590  ldarg.1
0x61591  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportType()
0x61596  ldloc.s  9
0x61598  ldloc.0
0x61599  ldloc.s  0xA
0x6159b  ldarg.1
0x6159c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x615a1  call     instance string Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetLogicalNameForImportEntity(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType importType, class Microsoft.Crm.Application.Platform.Entity importFile, bool isUpdate, string sourceEntityName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x615a6  stloc.s  0xB
0x615a8  ldloc.s  5
0x615aa  ldc.i4.1
0x615ab  add
0x615ac  stloc.s  5
0x615ae  ldloc.s  0xB
0x615b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x615b5  brtrue.s loc_61627
0x615b7  ldloc.s  0xB
0x615b9  ldarg.1
0x615ba  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportType Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportType()
0x615bf  ldc.i4.2
0x615c0  ceq
0x615c2  ldarg.1
0x615c3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x615c8  call     bool Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::IsValidForImport(string entityName, bool isUpdateViaImport, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x615cd  brfalse.s loc_61627
0x615cf  ldloc.s  0xB
0x615d1  stloc.s  0xC
0x615d3  ldloc.s  4
0x615d5  ldstr    aProcesscode// "ProcessCode"
0x615da  ldc.i4.2
0x615db  stloc.s  0xD
0x615dd  ldloca.s 0xD
0x615df  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x615e5  callvirt instance string [mscorlib]System.Object::ToString()
0x615ea  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x615ef  ldloc.s  4
0x615f1  ldstr    aTargetentityna_0// "TargetEntityName"
0x615f6  ldloc.s  0xC
0x615f8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x615fd  ldarg.0
0x615fe  ldloc.s  9
0x61600  ldstr    aImportfileid// "importfileid"
0x61605  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x6160a  unbox.any [mscorlib]System.Guid
0x6160f  ldloc.s  0xC
0x61611  ldarg.1
0x61612  callvirt instance int32[] Microsoft.Crm.Application.Platform.ImportWizardState::get_HeaderColumnIndexesToBeIgnored()
0x61617  ldloc.0
0x61618  ldloc.s  4
0x6161a  ldarg.1
0x6161b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x61620  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetAttributeMapsXmlFromImportFile(valuetype [mscorlib]System.Guid importFileId, string entityLogicalName, class [mscorlib]System.Collections.Generic.IList`1<int32> headerColumnIndexesToBeIgnored, bool isUpdateViaImportMap, class [System.Xml]System.Xml.XmlWriter writer, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x61625  br.s     loc_61643
0x61627  ldloc.s  4
0x61629  ldstr    aProcesscode// "ProcessCode"
0x6162e  ldc.i4.1
0x6162f  stloc.s  0xD
0x61631  ldloca.s 0xD
0x61633  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x61639  callvirt instance string [mscorlib]System.Object::ToString()
0x6163e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x61643  ldloc.s  4
0x61645  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x6164a  ldloc.s  8
0x6164c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x61651  brtrue   loc_6151F
0x61656  leave.s  loc_61664
0x61658  ldloc.s  8
0x6165a  brfalse.s loc_61663
0x6165c  ldloc.s  8
0x6165e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61663  endfinally
0x61664  ldloc.s  4
0x61666  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x6166b  ldloc.s  4
0x6166d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x61672  ldloc.s  4
0x61674  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x61679  ldloc.s  4
0x6167b  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x61680  leave.s  loc_6168E
0x61682  ldloc.s  4
0x61684  brfalse.s loc_6168D
0x61686  ldloc.s  4
0x61688  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6168d  endfinally
0x6168e  ldloc.2
0x6168f  callvirt instance string [mscorlib]System.Object::ToString()
0x61694  ret
```
