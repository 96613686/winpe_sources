# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessDialogXml

- ea: `0x89b0`
- end: `0x8b76`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProcessDialogXml`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7050`
- `0xddc0`

## callees

- `0x89b0`
- `0xa3a0`
- `0xa5a0`
- `0xa910`
- `0xd390`
- `0xd3b0`
- `0xf7a0`

## string_xrefs

- `0x89d1`: `ImportExportXml/Dialogs/Dialog`
- `0x8a7d`: `DialogXml`
- `0x8ade`: `FormXml/forms/form`

## pseudocode

```c

```

## disassembly

```asm
0x89b0  ldarg.0
0x89b1  ldarg.s  5
0x89b3  call     instance bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::IsSystemSolution(class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo solutionInfo)
0x89b8  stloc.0
0x89b9  ldarg.0
0x89ba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x89bf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x89c4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x89c9  pop
0x89ca  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x89cf  stloc.1
0x89d0  ldarg.1
0x89d1  ldstr    aImportexportxm_10// "ImportExportXml/Dialogs/Dialog"
0x89d6  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x89db  stloc.2
0x89dc  ldloc.2
0x89dd  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x89e2  stloc.3
0x89e3  br       loc_8B4A
0x89e8  ldloc.3
0x89e9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x89ee  castclass [System.Xml]System.Xml.XmlNode
0x89f3  stloc.s  4
0x89f5  ldloc.s  4
0x89f7  ldstr    aFormid_0// "FormId"
0x89fc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a01  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8a06  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x8a0b  stloc.s  5
0x8a0d  ldarg.s  5
0x8a0f  ldstr    aSystemform_0// "SystemForm"
0x8a14  ldstr    aFormid// "formid"
0x8a19  ldloc.s  5
0x8a1b  box      [mscorlib]System.Guid
0x8a20  ldc.i4.0
0x8a21  ldarg.0
0x8a22  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8a27  call     bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ShouldSkipComponent(class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, string entityName, string primaryAttributeName, object attributeValue, bool isMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8a2c  brfalse.s loc_8A58
0x8a2e  ldstr    aSystemform_0// "SystemForm"
0x8a33  ldstr    aFormid// "formid"
0x8a38  ldloca.s 5
0x8a3a  constrained. [mscorlib]System.Guid
0x8a40  callvirt instance string [mscorlib]System.Object::ToString()
0x8a45  ldarg.2
0x8a46  ldarg.s  5
0x8a48  ldarg.0
0x8a49  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8a4e  call     void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::LogComponentSkippedTrace(string componentName, string idName, string id, int32 languageCode, class Microsoft.Crm.Tools.LangProvisioning.LabelSolutionInfo labelSolutionInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext _context)
0x8a53  br       loc_8B4A
0x8a58  ldstr    aProcessingLabe_5// "Processing labels for isSystemSolution="...
0x8a5d  ldloc.0
0x8a5e  box      [mscorlib]System.Boolean
0x8a63  call     string [mscorlib]System.String::Format(string, object)
0x8a68  stloc.s  6
0x8a6a  ldarg.0
0x8a6b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8a70  ldloca.s 5
0x8a72  constrained. [mscorlib]System.Guid
0x8a78  callvirt instance string [mscorlib]System.Object::ToString()
0x8a7d  ldstr    aDialogxml// "DialogXml"
0x8a82  ldarg.2
0x8a83  ldloc.s  6
0x8a85  call     void Microsoft.Crm.Tools.Core.ImportExportPublish.ProvisionLanguageTelemetry::LangProvisioningTrace(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string componentId, string componentType, int32 languageCode, string message)
0x8a8a  ldarg.0
0x8a8b  ldloc.s  4
0x8a8d  ldstr    aFormid_0// "FormId"
0x8a92  ldstr    aName// "name"
0x8a97  ldarg.2
0x8a98  ldc.i4.5
0x8a99  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::GetLabelDescriptionFromXml(class [System.Xml]System.Xml.XmlNode objectNode, string objectIdAttributeName, string objectColumnName, int32 languageCode, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelType)
0x8a9e  stloc.s  7
0x8aa0  ldarg.0
0x8aa1  ldarg.3
0x8aa2  ldloc.s  7
0x8aa4  ldarg.s  4
0x8aa6  ldloc.0
0x8aa7  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AddUpdateQueue(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag pb, bool reprovision, bool isSystemSolution)
0x8aac  ldarg.0
0x8aad  ldloc.s  4
0x8aaf  ldstr    aFormid_0// "FormId"
0x8ab4  ldstr    aDescription// "description"
0x8ab9  ldarg.2
0x8aba  ldc.i4.5
0x8abb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::GetLabelDescriptionFromXml(class [System.Xml]System.Xml.XmlNode objectNode, string objectIdAttributeName, string objectColumnName, int32 languageCode, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelType)
0x8ac0  stloc.s  8
0x8ac2  ldloc.s  8
0x8ac4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescription::get_Label()
0x8ac9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8ace  brtrue.s loc_8ADC
0x8ad0  ldarg.0
0x8ad1  ldarg.3
0x8ad2  ldloc.s  8
0x8ad4  ldarg.s  4
0x8ad6  ldloc.0
0x8ad7  call     instance void Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::AddUpdateQueue(class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LocalizedLabelDescriptionPropertyBag pb, bool reprovision, bool isSystemSolution)
0x8adc  ldloc.s  4
0x8ade  ldstr    aFormxmlFormsFo// "FormXml/forms/form"
0x8ae3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x8ae8  stloc.s  9
0x8aea  ldloc.s  9
0x8aec  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8af1  stloc.s  0xA
0x8af3  br.s     loc_8B1E
0x8af5  ldloc.s  0xA
0x8af7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8afc  castclass [System.Xml]System.Xml.XmlNode
0x8b01  pop
0x8b02  ldloc.1
0x8b03  ldloc.s  5
0x8b05  ldloc.s  4
0x8b07  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x8b0c  ldc.i4.0
0x8b0d  ldarg.0
0x8b0e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::_context
0x8b13  ldarg.2
0x8b14  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x8b19  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::UpdateFormLabels(valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Nullable`1<int32>)
0x8b1e  ldloc.s  0xA
0x8b20  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8b25  brtrue.s loc_8AF5
0x8b27  leave.s  loc_8B4A
0x8b29  ldloc.s  0xA
0x8b2b  isinst   [mscorlib]System.IDisposable
0x8b30  stloc.s  0xB
0x8b32  ldloc.s  0xB
0x8b34  brfalse.s loc_8B3D
0x8b36  ldloc.s  0xB
0x8b38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b3d  endfinally
0x8b3e  ldloc.s  9
0x8b40  brfalse.s loc_8B49
0x8b42  ldloc.s  9
0x8b44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b49  endfinally
0x8b4a  ldloc.3
0x8b4b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8b50  brtrue   loc_89E8
0x8b55  leave.s  loc_8B75
0x8b57  ldloc.3
0x8b58  isinst   [mscorlib]System.IDisposable
0x8b5d  stloc.s  0xB
0x8b5f  ldloc.s  0xB
0x8b61  brfalse.s loc_8B6A
0x8b63  ldloc.s  0xB
0x8b65  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b6a  endfinally
0x8b6b  ldloc.2
0x8b6c  brfalse.s loc_8B74
0x8b6e  ldloc.2
0x8b6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8b74  endfinally
0x8b75  ret
```
