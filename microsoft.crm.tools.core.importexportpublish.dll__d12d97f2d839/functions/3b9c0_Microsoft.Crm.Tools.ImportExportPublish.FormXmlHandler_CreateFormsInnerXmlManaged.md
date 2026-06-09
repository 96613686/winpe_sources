# Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormsInnerXmlManaged

- ea: `0x3b9c0`
- end: `0x3bb69`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormsInnerXmlManaged`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x3b700`

## callees

- `0x3b7d0`
- `0x3b820`
- `0x3b9c0`
- `0x3bb70`
- `0x3c070`
- `0x3c090`
- `0x3c450`
- `0x3c4d0`
- `0x3c4f0`
- `0x3c520`

## string_xrefs

- `0x3b9cd`: `FormXml`
- `0x3ba23`: `formxml`
- `0x3ba82`: `formxml`
- `0x3ba89`: `formxml`
- `0x3baab`: `formxml`
- `0x3bab2`: `formxml`

## pseudocode

```c

```

## disassembly

```asm
0x3b9c0  ldarg.0
0x3b9c1  ldc.i4.1
0x3b9c2  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RetrieveFormsWithAllLanguages(bool customLabelsOnly)
0x3b9c7  ldarg.1
0x3b9c8  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x3b9cd  ldstr    aFormxml// "FormXml"
0x3b9d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x3b9d7  stloc.0
0x3b9d8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3b9dd  stloc.2
0x3b9de  br       loc_3BB41
0x3b9e3  ldloc.2
0x3b9e4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3b9e9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x3b9ee  stloc.3
0x3b9ef  ldarg.0
0x3b9f0  ldloc.3
0x3b9f1  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::DoesFormNeedToBeSkippedForExportToTargetVersion(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity systemFormEntity)
0x3b9f6  brtrue   loc_3BB41
0x3b9fb  ldloc.3
0x3b9fc  ldstr    aType_0// "type"
0x3ba01  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3ba06  unbox.any [mscorlib]System.Int32
0x3ba0b  stloc.s  4
0x3ba0d  ldarg.0
0x3ba0e  ldloc.s  4
0x3ba10  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::GetFormType(int32 formType)
0x3ba15  stloc.s  5
0x3ba17  ldloc.s  4
0x3ba19  ldc.i4.s 9
0x3ba1b  bne.un.s loc_3BA3E
0x3ba1d  ldarg.0
0x3ba1e  ldloc.0
0x3ba1f  ldloc.s  5
0x3ba21  ldloc.3
0x3ba22  ldloc.3
0x3ba23  ldstr    aFormxml_0// "formxml"
0x3ba28  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3ba2d  castclass [mscorlib]System.String
0x3ba32  ldc.i4.0
0x3ba33  ldarg.2
0x3ba34  call     instance void Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormNode(class [System.Xml]System.Xml.XmlElement containerElement, string formType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity formEntity, string formNodeInitialXml, bool isManaged, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService localizedLabelService)
0x3ba39  br       loc_3BB41
0x3ba3e  ldloc.s  4
0x3ba40  ldc.i4.5
0x3ba41  bne.un.s loc_3BA79
0x3ba43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x3ba48  ldstr    aMobileFormsWon// "Mobile forms wont be exported as they h"...
0x3ba4d  ldc.i4.0
0x3ba4e  newarr   [mscorlib]System.Object
0x3ba53  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3ba58  stloc.s  6
0x3ba5a  ldarg.0
0x3ba5b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::context
0x3ba60  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3ba65  ldc.i4.s 0x17
0x3ba67  ldloc.s  6
0x3ba69  ldc.i4.0
0x3ba6a  newarr   [mscorlib]System.Object
0x3ba6f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3ba74  br       loc_3BB41
0x3ba79  ldarg.0
0x3ba7a  ldloc.3
0x3ba7b  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CalculateFormXmlCustomizationDiff(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity topManagedEntity)
0x3ba80  stloc.1
0x3ba81  ldloc.3
0x3ba82  ldstr    aFormxml_0// "formxml"
0x3ba87  ldarg.0
0x3ba88  ldloc.3
0x3ba89  ldstr    aFormxml_0// "formxml"
0x3ba8e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3ba93  isinst   [mscorlib]System.String
0x3ba98  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RemoveDisplayAsCustomer360Tile(string formXml)
0x3ba9d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3baa2  ldarg.0
0x3baa3  ldloc.1
0x3baa4  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RemoveDisplayAsCustomer360Tile(string formXml)
0x3baa9  stloc.1
0x3baaa  ldloc.3
0x3baab  ldstr    aFormxml_0// "formxml"
0x3bab0  ldarg.0
0x3bab1  ldloc.3
0x3bab2  ldstr    aFormxml_0// "formxml"
0x3bab7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3babc  isinst   [mscorlib]System.String
0x3bac1  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RemoveActivityWallSortingParams(string formXml)
0x3bac6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x3bacb  ldarg.0
0x3bacc  ldloc.1
0x3bacd  call     instance string Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RemoveActivityWallSortingParams(string formXml)
0x3bad2  stloc.1
0x3bad3  ldc.i4.0
0x3bad4  stloc.s  7
0x3bad6  ldloc.1
0x3bad7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3badc  brfalse.s loc_3BB32
0x3bade  ldarg.0
0x3badf  ldloc.3
0x3bae0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::RetrieveLastManagedFormsWithAllLanguages(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity systemFormEntity)
0x3bae5  stloc.s  8
0x3bae7  ldloc.s  8
0x3bae9  brfalse.s loc_3BB2E
0x3baeb  ldloc.3
0x3baec  ldstr    aFormactivation// "formactivationstate"
0x3baf1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3baf6  brfalse.s loc_3BB2E
0x3baf8  ldloc.s  8
0x3bafa  ldstr    aFormactivation// "formactivationstate"
0x3baff  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3bb04  brfalse.s loc_3BB2E
0x3bb06  ldloc.3
0x3bb07  ldstr    aFormactivation// "formactivationstate"
0x3bb0c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3bb11  unbox.any [mscorlib]System.Int32
0x3bb16  ldloc.s  8
0x3bb18  ldstr    aFormactivation// "formactivationstate"
0x3bb1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x3bb22  unbox.any [mscorlib]System.Int32
0x3bb27  ceq
0x3bb29  ldc.i4.0
0x3bb2a  ceq
0x3bb2c  stloc.s  7
0x3bb2e  ldloc.s  7
0x3bb30  brfalse.s loc_3BB41
0x3bb32  ldarg.0
0x3bb33  ldloc.0
0x3bb34  ldloc.s  5
0x3bb36  ldloc.3
0x3bb37  ldloc.1
0x3bb38  ldc.i4.1
0x3bb39  ldarg.2
0x3bb3a  ldloc.s  7
0x3bb3c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.FormXmlHandler::CreateFormNode(class [System.Xml]System.Xml.XmlElement containerElement, string formType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity formEntity, string formNodeInitialXml, bool isManaged, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService localizedLabelService, bool isOnlyFormStateModified)
0x3bb41  ldloc.2
0x3bb42  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3bb47  brtrue   loc_3B9E3
0x3bb4c  leave.s  loc_3BB62
0x3bb4e  ldloc.2
0x3bb4f  isinst   [mscorlib]System.IDisposable
0x3bb54  stloc.s  9
0x3bb56  ldloc.s  9
0x3bb58  brfalse.s loc_3BB61
0x3bb5a  ldloc.s  9
0x3bb5c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3bb61  endfinally
0x3bb62  ldloc.0
0x3bb63  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x3bb68  ret
```
