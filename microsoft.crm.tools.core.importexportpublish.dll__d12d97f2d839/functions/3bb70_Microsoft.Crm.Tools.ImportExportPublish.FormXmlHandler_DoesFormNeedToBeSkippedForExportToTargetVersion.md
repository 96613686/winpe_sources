# Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::DoesFormNeedToBeSkippedForExportToTargetVersion

- ea: `0x3bb70`
- end: `0x3bd91`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::DoesFormNeedToBeSkippedForExportToTargetVersion`
- size: `545`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x3b8a0`
- `0x3b9c0`

## callees

- `0x37450`
- `0x3a780`
- `0x3a7b0`
- `0x3a7c0`
- `0x3aa70`
- `0x3af90`
- `0x3b550`
- `0x3bb70`
- `0x3bda0`
- `0x3be40`
- `0x3be90`
- `0x3bee0`
- `0x3bf20`
- `0x3bf70`
- `0x3c970`
- `0x3c990`
- `0x3c9a0`
- `0x3c9b0`
- `0x3c9e0`
- `0x3ca30`
- `0x3ca40`

## string_xrefs

- `0x3bc33`: `formxml`
- `0x3bd4d`: `formxml`
- `0x3bca7`: `Customization.Type_FormXml`

## pseudocode

```c

```

## disassembly

```asm
0x3bb70  ldarg.1
0x3bb71  ldstr    aFormid// "formid"
0x3bb76  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3bb7b  unbox.any [mscorlib]System.Guid
0x3bb80  ldc.i4.s 0x3C
0x3bb82  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x3bb87  stloc.0
0x3bb88  ldarg.0
0x3bb89  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3bb8e  ldloc.0
0x3bb8f  callvirt instance valuetype Microsoft.Crm.Tools.ImportExportPublish.ComponentAction Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::ActionToBeTakenOnComponent(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent)
0x3bb94  stloc.1
0x3bb95  ldnull
0x3bb96  stloc.2
0x3bb97  ldnull
0x3bb98  stloc.3
0x3bb99  ldloc.1
0x3bb9a  ldc.i4.1
0x3bb9b  beq.s    loc_3BBA1
0x3bb9d  ldloc.1
0x3bb9e  ldc.i4.2
0x3bb9f  bne.un.s loc_3BBFD
0x3bba1  ldarg.0
0x3bba2  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3bba7  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_FilteredComponents()
0x3bbac  ldloc.0
0x3bbad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent>::get_Item(void)
0x3bbb2  stloc.3
0x3bbb3  ldloc.3
0x3bbb4  brfalse.s loc_3BBFD
0x3bbb6  ldloc.3
0x3bbb7  ldloc.3
0x3bbb8  callvirt instance int32 Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_ComponentType()
0x3bbbd  call     string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::RetrievePlatformName(int32)
0x3bbc2  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::set_TypeName(string value)
0x3bbc7  ldloc.3
0x3bbc8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Id()
0x3bbcd  ldloc.3
0x3bbce  callvirt instance int32 Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_ComponentType()
0x3bbd3  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x3bbd8  ldarg.0
0x3bbd9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3bbde  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::RetrieveComponentInfo(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> component, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3bbe3  stloc.s  4
0x3bbe5  ldloc.s  4
0x3bbe7  brfalse.s loc_3BBFD
0x3bbe9  ldloc.3
0x3bbea  ldloc.s  4
0x3bbec  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_DisplayName()
0x3bbf1  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::set_Name(string value)
0x3bbf6  ldloc.3
0x3bbf7  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Name()
0x3bbfc  stloc.2
0x3bbfd  ldloc.1
0x3bbfe  ldc.i4.1
0x3bbff  bne.un.s loc_3BC03
0x3bc01  ldc.i4.1
0x3bc02  ret
0x3bc03  ldloc.1
0x3bc04  ldc.i4.2
0x3bc05  bne.un   loc_3BD8F
0x3bc0a  ldarg.0
0x3bc0b  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3bc10  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_DependencyInfo()
0x3bc15  ldloc.0
0x3bc16  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>>::ContainsKey(var<u1>)
0x3bc1b  brtrue.s loc_3BC1F
0x3bc1d  ldc.i4.0
0x3bc1e  ret
0x3bc1f  ldarg.0
0x3bc20  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3bc25  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>> Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_DependencyInfo()
0x3bc2a  ldloc.0
0x3bc2b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity>>::get_Item(void)
0x3bc30  stloc.s  5
0x3bc32  ldarg.1
0x3bc33  ldstr    aFormxml_0// "formxml"
0x3bc38  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3bc3d  isinst   [mscorlib]System.String
0x3bc42  stloc.s  6
0x3bc44  ldarg.1
0x3bc45  ldstr    aObjecttypecode_0// "objecttypecode"
0x3bc4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3bc4f  unbox.any [mscorlib]System.Int32
0x3bc54  stloc.s  7
0x3bc56  ldarg.0
0x3bc57  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::_metadataCache
0x3bc5c  ldloc.s  7
0x3bc5e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x3bc63  stloc.s  8
0x3bc65  ldnull
0x3bc66  stloc.s  9
0x3bc68  ldloc.s  8
0x3bc6a  brfalse.s loc_3BC7A
0x3bc6c  ldloc.s  8
0x3bc6e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x3bc73  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0x3bc78  stloc.s  9
0x3bc7a  ldloc.s  9
0x3bc7c  ldnull
0x3bc7d  cgt.un
0x3bc7f  ldstr    aEntityNameIsNu// "Entity name is null."
0x3bc84  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3bc89  ldloc.s  6
0x3bc8b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x3bc90  brtrue   loc_3BD5E
0x3bc95  ldarg.0
0x3bc96  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3bc9b  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x3bca0  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x3bca5  stloc.s  0xA
0x3bca7  ldstr    aCustomizationT_5// "Customization.Type_FormXml"
0x3bcac  ldloc.s  0xA
0x3bcae  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3bcb3  stloc.s  0xB
0x3bcb5  ldc.i4.0
0x3bcb6  ldloc.s  6
0x3bcb8  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x3bcbd  stloc.s  0xC
0x3bcbf  ldarg.0
0x3bcc0  ldloc.s  0xC
0x3bcc2  ldloc.2
0x3bcc3  ldloc.s  9
0x3bcc5  ldloc.s  5
0x3bcc7  ldloc.3
0x3bcc8  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::ProcessControlNodesForExportToTargetVersion(class [System.Xml]System.Xml.XmlDocument document, string formName, string formEntityName, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent)
0x3bccd  or
0x3bcce  ldarg.0
0x3bccf  ldloc.s  0xC
0x3bcd1  ldloc.2
0x3bcd2  ldloc.s  9
0x3bcd4  ldloc.s  5
0x3bcd6  ldloc.3
0x3bcd7  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::ProcessHiddenControlNodesForExportToTargetVersion(class [System.Xml]System.Xml.XmlDocument document, string formName, string currentEntityName, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent)
0x3bcdc  or
0x3bcdd  ldarg.0
0x3bcde  ldloc.s  0xC
0x3bce0  ldloc.2
0x3bce1  ldloc.s  9
0x3bce3  ldloc.s  5
0x3bce5  ldloc.3
0x3bce6  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::ProcessNavigationElementsForExportToTargetVersion(class [System.Xml]System.Xml.XmlDocument document, string formName, string currentEntityName, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent)
0x3bceb  or
0x3bcec  ldarg.0
0x3bced  ldarg.0
0x3bcee  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3bcf3  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x3bcf8  ldloc.s  0xC
0x3bcfa  ldloc.2
0x3bcfb  ldloc.s  9
0x3bcfd  ldloc.3
0x3bcfe  ldloc.s  5
0x3bd00  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::HandleFormEvents(class [mscorlib]System.Version targetVersion, class [System.Xml]System.Xml.XmlDocument document, string formName, string formEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies)
0x3bd05  or
0x3bd06  ldarg.0
0x3bd07  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3bd0c  ldloc.s  0xC
0x3bd0e  ldloc.s  0xB
0x3bd10  ldloc.2
0x3bd11  ldloc.s  9
0x3bd13  ldloc.3
0x3bd14  ldloc.s  5
0x3bd16  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::ProcessWebResourceControlNodeExportToTargetVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlDocument document, string componentType, string formName, string formEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies)
0x3bd1b  or
0x3bd1c  ldarg.0
0x3bd1d  ldstr    aAvailableforph// "availableforphone"
0x3bd22  ldc.i4.1
0x3bd23  ldloc.s  0xC
0x3bd25  ldarg.0
0x3bd26  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::get_ExportToTargetVersionContext()
0x3bd2b  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::get_TargetVersion()
0x3bd30  ldsfld   class [mscorlib]System.Version [Microsoft.Crm]Microsoft.Crm.CrmVersions::CarinaVersion
0x3bd35  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::ProcessFormXmlSchemaAttributeOrNode(string elementName, bool isAttribute, class [System.Xml]System.Xml.XmlDocument doc, class [mscorlib]System.Version targetVersion, class [mscorlib]System.Version introducedVersion)
0x3bd3a  or
0x3bd3b  ldarg.0
0x3bd3c  ldloc.s  0xC
0x3bd3e  ldloc.2
0x3bd3f  ldloc.s  9
0x3bd41  ldloc.3
0x3bd42  ldloc.s  5
0x3bd44  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::HandleScriptResources(class [System.Xml]System.Xml.XmlDocument document, string formName, string formEntityName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity> dependencies)
0x3bd49  or
0x3bd4a  brfalse.s loc_3BD5E
0x3bd4c  ldarg.1
0x3bd4d  ldstr    aFormxml_0// "formxml"
0x3bd52  ldloc.s  0xC
0x3bd54  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3bd59  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3bd5e  ldloc.3
0x3bd5f  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Comments()
0x3bd64  brfalse.s loc_3BD8F
0x3bd66  ldloc.3
0x3bd67  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Comments()
0x3bd6c  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::get_Count()
0x3bd71  ldc.i4.1
0x3bd72  ble.s    loc_3BD8F
0x3bd74  ldloc.3
0x3bd75  ldloc.3
0x3bd76  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::get_Comments()
0x3bd7b  call     T0x2B000035
0x3bd80  call     T0x2B000004
0x3bd85  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x3bd8a  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent::set_Comments(class [mscorlib]System.Collections.ObjectModel.Collection`1<string> value)
0x3bd8f  ldc.i4.0
0x3bd90  ret
```
