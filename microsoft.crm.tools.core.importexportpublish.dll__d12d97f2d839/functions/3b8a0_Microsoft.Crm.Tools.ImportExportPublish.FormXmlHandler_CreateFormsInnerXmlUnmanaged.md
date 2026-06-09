# Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormsInnerXmlUnmanaged

- ea: `0x3b8a0`
- end: `0x3b9c0`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormsInnerXmlUnmanaged`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x3b700`

## callees

- `0x3b7d0`
- `0x3b820`
- `0x3b8a0`
- `0x3bb70`
- `0x3c070`
- `0x3c4f0`
- `0x3c520`

## string_xrefs

- `0x3b8ad`: `FormXml`
- `0x3b8dc`: `formxml`
- `0x3b8e3`: `formxml`
- `0x3b8fd`: `formxml`
- `0x3b904`: `formxml`
- `0x3b982`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0x3b8a0  ldarg.0
0x3b8a1  ldc.i4.0
0x3b8a2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RetrieveFormsWithAllLanguages(bool customLabelsOnly)
0x3b8a7  ldarg.1
0x3b8a8  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x3b8ad  ldstr    aFormxml// "FormXml"
0x3b8b2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3b8b7  stloc.0
0x3b8b8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3b8bd  stloc.1
0x3b8be  br       loc_3B998
0x3b8c3  ldloc.1
0x3b8c4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3b8c9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3b8ce  stloc.2
0x3b8cf  ldarg.0
0x3b8d0  ldloc.2
0x3b8d1  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::DoesFormNeedToBeSkippedForExportToTargetVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity systemFormEntity)
0x3b8d6  brtrue   loc_3B998
0x3b8db  ldloc.2
0x3b8dc  ldstr    aFormxml_0// "formxml"
0x3b8e1  ldarg.0
0x3b8e2  ldloc.2
0x3b8e3  ldstr    aFormxml_0// "formxml"
0x3b8e8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b8ed  isinst   [mscorlib]System.String
0x3b8f2  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RemoveDisplayAsCustomer360Tile(string formXml)
0x3b8f7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3b8fc  ldloc.2
0x3b8fd  ldstr    aFormxml_0// "formxml"
0x3b902  ldarg.0
0x3b903  ldloc.2
0x3b904  ldstr    aFormxml_0// "formxml"
0x3b909  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b90e  isinst   [mscorlib]System.String
0x3b913  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RemoveActivityWallSortingParams(string formXml)
0x3b918  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3b91d  ldarg.0
0x3b91e  ldloc.2
0x3b91f  ldstr    aType_0// "type"
0x3b924  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b929  unbox.any [mscorlib]System.Int32
0x3b92e  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::GetFormType(int32 formType)
0x3b933  stloc.3
0x3b934  ldloc.3
0x3b935  brfalse.s loc_3B998
0x3b937  ldloc.2
0x3b938  ldstr    aType_0// "type"
0x3b93d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b942  unbox.any [mscorlib]System.Int32
0x3b947  ldc.i4.5
0x3b948  bne.un.s loc_3B97D
0x3b94a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x3b94f  ldstr    aMobileFormsWon// "Mobile forms wont be exported as they h"...
0x3b954  ldc.i4.0
0x3b955  newarr   [mscorlib]System.Object
0x3b95a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b95f  stloc.s  4
0x3b961  ldarg.0
0x3b962  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3b967  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3b96c  ldc.i4.s 0x17
0x3b96e  ldloc.s  4
0x3b970  ldc.i4.0
0x3b971  newarr   [mscorlib]System.Object
0x3b976  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3b97b  br.s     loc_3B998
0x3b97d  ldarg.0
0x3b97e  ldloc.0
0x3b97f  ldloc.3
0x3b980  ldloc.2
0x3b981  ldloc.2
0x3b982  ldstr    aFormxml_0// "formxml"
0x3b987  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3b98c  castclass [mscorlib]System.String
0x3b991  ldc.i4.0
0x3b992  ldarg.2
0x3b993  call     instance void Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormNode(class [System.Xml]System.Xml.XmlElement containerElement, string formType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity formEntity, string formNodeInitialXml, bool isManaged, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService localizedLabelService)
0x3b998  ldloc.1
0x3b999  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3b99e  brtrue   loc_3B8C3
0x3b9a3  leave.s  loc_3B9B9
0x3b9a5  ldloc.1
0x3b9a6  isinst   [mscorlib]System.IDisposable
0x3b9ab  stloc.s  5
0x3b9ad  ldloc.s  5
0x3b9af  brfalse.s loc_3B9B8
0x3b9b1  ldloc.s  5
0x3b9b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3b9b8  endfinally
0x3b9b9  ldloc.0
0x3b9ba  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x3b9bf  ret
```
