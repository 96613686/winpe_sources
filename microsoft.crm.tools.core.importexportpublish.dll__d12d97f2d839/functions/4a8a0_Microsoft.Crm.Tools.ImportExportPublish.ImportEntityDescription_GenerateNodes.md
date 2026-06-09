# Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription::GenerateNodes

- ea: `0x4a8a0`
- end: `0x4baee`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription::GenerateNodes`
- size: `4686`
- prototype: ``
- caller_count: `1`
- callee_count: `49`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x66e00`

## callees

- `0x4a780`
- `0x4a8a0`
- `0x4baf0`
- `0x4bc80`
- `0x4bd90`
- `0x4bdb0`
- `0x4be00`
- `0x4be20`
- `0x4be70`
- `0x4be90`
- `0x4bee0`
- `0x4bf00`
- `0x4bf30`
- `0x4bf90`
- `0x4bfb0`
- `0x4c000`
- `0x4c020`
- `0x4c040`
- `0x4c090`
- `0x4c0b0`
- `0x4c100`
- `0x4c120`
- `0x4c170`
- `0x4c190`
- `0x4c1e0`
- `0x4c200`
- `0x4c250`
- `0x4c270`
- `0x4c290`
- `0x4c2e0`
- `0x4c300`
- `0x4c370`
- `0x4c390`
- `0x4c3e0`
- `0x4c400`
- `0x4c470`
- `0x4c490`
- `0x4c500`
- `0x4c520`
- `0x4c590`
- `0x4c5e0`
- `0x4c600`
- `0x4c650`
- `0x4c670`
- `0x4c6e0`
- `0x4c700`
- `0x4c720`
- `0x4c800`
- `0x4c820`

## string_xrefs

- `0x4b477`: `FieldSecurityProfile`
- `0x4af93`: `PluginAssembly`
- `0x4b1a3`: `ServiceEndpoint`
- `0x4b450`: `FieldSecurityProfiles`
- `0x4a8bc`: `importexportxml`
- `0x4ad80`: `template`
- `0x4acb5`: `securityrole`
- `0x4aa36`: `isvconfig`
- `0x4ad5e`: `templates`
- `0x4ac8e`: `securityroles`
- `0x4af6c`: `SolutionPluginAssemblies`
- `0x4b179`: `ServiceEndpoints`
- `0x4b8c4`: `channelaccessprofiles`
- `0x4b8eb`: `channelaccessprofile`

## pseudocode

```c

```

## disassembly

```asm
0x4a8a0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4a8a5  stloc.0
0x4a8a6  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x4a8ab  stloc.1
0x4a8ac  ldloc.1
0x4a8ad  ldc.i4.1
0x4a8ae  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x4a8b3  ldloc.0
0x4a8b4  ldloc.1
0x4a8b5  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x4a8ba  stloc.2
0x4a8bb  ldloc.2
0x4a8bc  ldstr    aImportexportxm_95// "importexportxml"
0x4a8c1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4a8c6  ldloc.2
0x4a8c7  ldarg.s  0x1A
0x4a8c9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x4a8ce  ldloc.2
0x4a8cf  ldarg.s  0x1B
0x4a8d1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x4a8d6  ldarg.s  0x1C
0x4a8d8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a8dd  brtrue.s loc_4A8E7
0x4a8df  ldloc.2
0x4a8e0  ldarg.s  0x1C
0x4a8e2  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x4a8e7  ldarg.s  0x1D
0x4a8e9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a8ee  brtrue.s loc_4A8F8
0x4a8f0  ldloc.2
0x4a8f1  ldarg.s  0x1D
0x4a8f3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x4a8f8  ldloc.2
0x4a8f9  ldstr    aEntities_1// "entities"
0x4a8fe  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4a903  ldarg.1
0x4a904  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x4a909  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4a90e  stloc.3
0x4a90f  br.s     loc_4A930
0x4a911  ldloc.3
0x4a912  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a917  castclass Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription
0x4a91c  stloc.s  4
0x4a91e  ldloc.2
0x4a91f  ldloc.s  4
0x4a921  ldstr    aEntity// "entity"
0x4a926  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription::GenerateNode(string entityName)
0x4a92b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x4a930  ldloc.3
0x4a931  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a936  brtrue.s loc_4A911
0x4a938  leave.s  loc_4A94E
0x4a93a  ldloc.3
0x4a93b  isinst   [mscorlib]System.IDisposable
0x4a940  stloc.s  5
0x4a942  ldloc.s  5
0x4a944  brfalse.s loc_4A94D
0x4a946  ldloc.s  5
0x4a948  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a94d  endfinally
0x4a94e  ldloc.2
0x4a94f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4a954  ldarg.s  0x2F
0x4a956  brfalse.s loc_4A9B5
0x4a958  ldloc.2
0x4a959  ldstr    aAppmodules// "AppModules"
0x4a95e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4a963  ldarg.s  0x2F
0x4a965  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x4a96a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4a96f  stloc.3
0x4a970  br.s     loc_4A991
0x4a972  ldloc.3
0x4a973  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a978  castclass Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription
0x4a97d  stloc.s  6
0x4a97f  ldloc.2
0x4a980  ldloc.s  6
0x4a982  ldstr    aAppmodule// "AppModule"
0x4a987  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription::GenerateNode(string entityName)
0x4a98c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x4a991  ldloc.3
0x4a992  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a997  brtrue.s loc_4A972
0x4a999  leave.s  loc_4A9AF
0x4a99b  ldloc.3
0x4a99c  isinst   [mscorlib]System.IDisposable
0x4a9a1  stloc.s  5
0x4a9a3  ldloc.s  5
0x4a9a5  brfalse.s loc_4A9AE
0x4a9a7  ldloc.s  5
0x4a9a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a9ae  endfinally
0x4a9af  ldloc.2
0x4a9b0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4a9b5  ldarg.s  0x30
0x4a9b7  brfalse.s loc_4AA16
0x4a9b9  ldloc.2
0x4a9ba  ldstr    aAppmodulesitem_4// "AppModuleSiteMaps"
0x4a9bf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4a9c4  ldarg.s  0x30
0x4a9c6  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x4a9cb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4a9d0  stloc.3
0x4a9d1  br.s     loc_4A9F2
0x4a9d3  ldloc.3
0x4a9d4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4a9d9  castclass Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription
0x4a9de  stloc.s  7
0x4a9e0  ldloc.2
0x4a9e1  ldloc.s  7
0x4a9e3  ldstr    aAppmodulesitem_8// "AppModuleSiteMap"
0x4a9e8  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription::GenerateNode(string entityName)
0x4a9ed  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteRaw(string)
0x4a9f2  ldloc.3
0x4a9f3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a9f8  brtrue.s loc_4A9D3
0x4a9fa  leave.s  loc_4AA10
0x4a9fc  ldloc.3
0x4a9fd  isinst   [mscorlib]System.IDisposable
0x4aa02  stloc.s  5
0x4aa04  ldloc.s  5
0x4aa06  brfalse.s loc_4AA0F
0x4aa08  ldloc.s  5
0x4aa0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4aa0f  endfinally
0x4aa10  ldloc.2
0x4aa11  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4aa16  ldloc.2
0x4aa17  ldstr    aNodes// "nodes"
0x4aa1c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4aa21  ldarg.s  0x1E
0x4aa23  brfalse.s loc_4AA46
0x4aa25  ldloc.2
0x4aa26  ldstr    aNode// "node"
0x4aa2b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4aa30  ldloc.2
0x4aa31  ldstr    aId// "id"
0x4aa36  ldstr    aIsvconfig_0// "isvconfig"
0x4aa3b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4aa40  ldloc.2
0x4aa41  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4aa46  ldarg.s  0x1F
0x4aa48  brfalse.s loc_4AA6B
0x4aa4a  ldloc.2
0x4aa4b  ldstr    aNode// "node"
0x4aa50  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4aa55  ldloc.2
0x4aa56  ldstr    aId// "id"
0x4aa5b  ldstr    aRelationshipro_0// "relationshiproles"
0x4aa60  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4aa65  ldloc.2
0x4aa66  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4aa6b  ldarg.s  0x20
0x4aa6d  brfalse.s loc_4AA90
0x4aa6f  ldloc.2
0x4aa70  ldstr    aNode// "node"
0x4aa75  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4aa7a  ldloc.2
0x4aa7b  ldstr    aId// "id"
0x4aa80  ldstr    aSitemap_0// "sitemap"
0x4aa85  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4aa8a  ldloc.2
0x4aa8b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4aa90  ldloc.2
0x4aa91  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4aa96  ldloc.2
0x4aa97  ldarg.s  0x21
0x4aa99  ldarg.s  0x22
0x4aa9b  ldarg.s  0x23
0x4aa9d  ldarg.s  0x24
0x4aa9f  ldarg.s  0x25
0x4aaa1  ldarg.s  0x26
0x4aaa3  ldarg.s  0x27
0x4aaa5  ldarg.s  0x28
0x4aaa7  ldarg.s  0x29
0x4aaa9  ldarg.s  0x2A
0x4aaab  call     void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityDescription::GenerateSettings(class [System.Xml]System.Xml.XmlWriter xw, bool orgSettingsGeneralIsPresent, bool orgSettingsCalendarIsPresent, bool orgSettingsEmailIsPresent, bool orgSettingsMarketingIsPresent, bool orgSettingsCustomizationIsPresent, bool orgSettingsOutlookSynchronizationIsPresent, bool orgSettingsAutoNumberingIsPresent, bool orgSettingsSalesIsPresent, bool orgSettingsExternalApplicationsIsPresent, bool orgSettingsModulesContextIsPresent)
0x4aab0  ldloc.2
0x4aab1  ldstr    aInteractioncen_0// "InteractionCentricDashboards"
0x4aab6  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x4aabb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4aac0  ldarg.3
0x4aac1  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x4aac6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4aacb  stloc.3
0x4aacc  br.s     loc_4AB31
0x4aace  ldloc.3
0x4aacf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4aad4  castclass [mscorlib]System.String
0x4aad9  stloc.s  8
0x4aadb  ldloc.2
0x4aadc  ldstr    aInteractioncen// "InteractionCentricDashboard"
0x4aae1  call     instance string [mscorlib]System.String::ToLowerInvariant()
0x4aae6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4aaeb  ldarg.3
0x4aaec  ldloc.s  8
0x4aaee  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x4aaf3  castclass Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardDescription
0x4aaf8  stloc.s  9
0x4aafa  ldloc.2
0x4aafb  ldstr    aId// "id"
0x4ab00  ldloc.s  8
0x4ab02  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4ab07  ldloc.2
0x4ab08  ldstr    aName// "name"
0x4ab0d  ldloc.s  9
0x4ab0f  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardDescription::get_DisplayName()
0x4ab14  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4ab19  ldloc.2
0x4ab1a  ldstr    aDescription// "description"
0x4ab1f  ldloc.s  9
0x4ab21  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportInteractionCentricDashboardDescription::get_Description()
0x4ab26  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4ab2b  ldloc.2
0x4ab2c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4ab31  ldloc.3
0x4ab32  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ab37  brtrue.s loc_4AACE
0x4ab39  leave.s  loc_4AB4F
0x4ab3b  ldloc.3
0x4ab3c  isinst   [mscorlib]System.IDisposable
0x4ab41  stloc.s  5
0x4ab43  ldloc.s  5
0x4ab45  brfalse.s loc_4AB4E
0x4ab47  ldloc.s  5
0x4ab49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ab4e  endfinally
0x4ab4f  ldloc.2
0x4ab50  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4ab55  ldloc.2
0x4ab56  ldstr    aDashboards_0// "dashboards"
0x4ab5b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4ab60  ldarg.2
0x4ab61  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x4ab66  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4ab6b  stloc.3
0x4ab6c  br.s     loc_4ABCC
0x4ab6e  ldloc.3
0x4ab6f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4ab74  castclass [mscorlib]System.String
0x4ab79  stloc.s  0xA
0x4ab7b  ldloc.2
0x4ab7c  ldstr    aDashboard_0// "dashboard"
0x4ab81  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4ab86  ldarg.2
0x4ab87  ldloc.s  0xA
0x4ab89  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x4ab8e  castclass Microsoft.Crm.Tools.ImportExportPublish.ImportDashboardDescription
0x4ab93  stloc.s  0xB
0x4ab95  ldloc.2
0x4ab96  ldstr    aId// "id"
0x4ab9b  ldloc.s  0xA
0x4ab9d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4aba2  ldloc.2
0x4aba3  ldstr    aName// "name"
0x4aba8  ldloc.s  0xB
0x4abaa  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportDashboardDescription::get_DisplayName()
0x4abaf  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4abb4  ldloc.2
0x4abb5  ldstr    aDescription// "description"
0x4abba  ldloc.s  0xB
0x4abbc  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportDashboardDescription::get_Description()
0x4abc1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x4abc6  ldloc.2
0x4abc7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4abcc  ldloc.3
0x4abcd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4abd2  brtrue.s loc_4AB6E
0x4abd4  leave.s  loc_4ABEA
0x4abd6  ldloc.3
0x4abd7  isinst   [mscorlib]System.IDisposable
0x4abdc  stloc.s  5
0x4abde  ldloc.s  5
0x4abe0  brfalse.s loc_4ABE9
0x4abe2  ldloc.s  5
0x4abe4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4abe9  endfinally
0x4abea  ldloc.2
0x4abeb  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x4abf0  ldloc.2
0x4abf1  ldstr    aDialogs_0// "dialogs"
0x4abf6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4abfb  ldarg.s  4
0x4abfd  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x4ac02  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x4ac07  stloc.3
0x4ac08  br.s     loc_4AC69
0x4ac0a  ldloc.3
0x4ac0b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4ac10  castclass [mscorlib]System.String
0x4ac15  stloc.s  0xC
0x4ac17  ldloc.2
0x4ac18  ldstr    aDialog_0// "dialog"
0x4ac1d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x4ac22  ldarg.s  4
0x4ac24  ldloc.s  0xC
0x4ac26  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x4ac2b  castclass Microsoft.Crm.Tools.ImportExportPublish.ImportDialogDescription
  ... truncated ...
```
