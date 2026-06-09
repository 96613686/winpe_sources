# Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateImportJobEntryAtTheEndOfImport

- ea: `0x68480`
- end: `0x686aa`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateImportJobEntryAtTheEndOfImport`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x680f0`

## callees

- `0x33df0`
- `0x68380`
- `0x68480`
- `0x68bc0`

## string_xrefs

- `0x6859c`: `completedon`
- `0x684e2`: `importexportxml`
- `0x6850b`: `importexportxml`
- `0x6854f`: `importexportxml`
- `0x684a8`: `/importexportxml/solutionManifests/solutionManifest/result`
- `0x6865e`: `Error occured while updating the ImportJob table at the end of import. Solution import originally failed with Message: {0} Details: {1}. ImportJob update failed with Message: {2} Details: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x68480  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x68485  box      [mscorlib]System.Guid
0x6848a  ldarg.0
0x6848b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_importJobId
0x68490  box      [mscorlib]System.Guid
0x68495  call     bool [mscorlib]System.Object::Equals(object, object)
0x6849a  brtrue   loc_68657
0x6849f  ldarg.1
0x684a0  brfalse.s loc_684DC
0x684a2  ldarg.0
0x684a3  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x684a8  ldstr    aImportexportxm_189// "/importexportxml/solutionManifests/solu"...
0x684ad  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x684b2  castclass [System.Xml]System.Xml.XmlElement
0x684b7  stloc.1
0x684b8  ldloc.1
0x684b9  brfalse.s loc_684DC
0x684bb  ldloc.1
0x684bc  ldstr    aResult// "result"
0x684c1  ldstr    aFailure// "failure"
0x684c6  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x684cb  ldloc.1
0x684cc  ldstr    aErrortext_0// "errortext"
0x684d1  ldarg.1
0x684d2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x684d7  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x684dc  ldarg.0
0x684dd  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x684e2  ldstr    aImportexportxm_95// "importexportxml"
0x684e7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x684ec  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x684f1  ldstr    aProcessed// "processed"
0x684f6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x684fb  ldstr    aTrue// "true"
0x68500  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x68505  ldarg.0
0x68506  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x6850b  ldstr    aImportexportxm_95// "importexportxml"
0x68510  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x68515  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6851a  ldstr    aStop// "stop"
0x6851f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x68524  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x68529  stloc.2
0x6852a  ldloca.s 2
0x6852c  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x68531  stloc.3
0x68532  ldloca.s 3
0x68534  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x68539  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x6853e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x68543  ldarg.0
0x68544  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_excelHelper
0x68549  ldarg.0
0x6854a  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x6854f  ldstr    aImportexportxm_95// "importexportxml"
0x68554  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x68559  callvirt instance float64 Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetProgress(class [System.Xml]System.Xml.XmlNode node)
0x6855e  stloc.0
0x6855f  ldarg.0
0x68560  ldloc.0
0x68561  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::AddProgressToData(float64 progress)
0x68566  ldarg.0
0x68567  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x6856c  ldstr    aData// "data"
0x68571  ldarg.0
0x68572  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportXml::parameterXmlDoc
0x68577  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x6857c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x68581  ldarg.0
0x68582  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x68587  ldstr    aModifiedon// "modifiedon"
0x6858c  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x68591  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x68596  ldarg.0
0x68597  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x6859c  ldstr    aCompletedon// "completedon"
0x685a1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x685a6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x685ab  ldarg.0
0x685ac  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x685b1  ldstr    aProgress// "progress"
0x685b6  ldloc.0
0x685b7  box      [mscorlib]System.Double
0x685bc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x685c1  ldarg.0
0x685c2  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::context
0x685c7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x685cc  ldstr    aImportjob_0// "importjob"
0x685d1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x685d6  ldstr    aSolutionid// "solutionid"
0x685db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x685e0  brfalse.s loc_6863F
0x685e2  ldarg.0
0x685e3  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x685e8  ldstr    aSolutionid// "solutionid"
0x685ed  ldarg.0
0x685ee  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_solutionId
0x685f3  box      [mscorlib]System.Guid
0x685f8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x685fd  ldarg.0
0x685fe  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x68603  ldstr    aImportcontext// "importcontext"
0x68608  ldarg.0
0x68609  ldflda   valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_importContext
0x6860e  constrained. [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext
0x68614  callvirt instance string [mscorlib]System.Object::ToString()
0x68619  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6861e  ldarg.0
0x6861f  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x68624  ldstr    aOperationconte// "operationcontext"
0x68629  ldarg.0
0x6862a  ldflda   valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::_operationContext
0x6862f  constrained. [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext
0x68635  callvirt instance string [mscorlib]System.Object::ToString()
0x6863a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x6863f  ldarg.0
0x68640  ldarg.0
0x68641  ldfld    class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob Microsoft.Crm.Tools.ImportExportPublish.ImportXml::importJob
0x68646  ldarg.0
0x68647  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportXml::context
0x6864c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x68651  ldc.i4.0
0x68652  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::CreateOrUpdateImportJob(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ImportJob importJob, valuetype [mscorlib]System.Guid organizationId, bool isCreate)
0x68657  leave.s  loc_686A9
0x68659  stloc.s  4
0x6865b  ldarg.1
0x6865c  brfalse.s loc_68690
0x6865e  ldstr    aErrorOccuredWh_0// "Error occured while updating the Import"...
0x68663  ldc.i4.4
0x68664  newarr   [mscorlib]System.Object
0x68669  dup
0x6866a  ldc.i4.0
0x6866b  ldarg.1
0x6866c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x68671  stelem.ref
0x68672  dup
0x68673  ldc.i4.1
0x68674  ldarg.1
0x68675  stelem.ref
0x68676  dup
0x68677  ldc.i4.2
0x68678  ldloc.s  4
0x6867a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6867f  stelem.ref
0x68680  dup
0x68681  ldc.i4.3
0x68682  ldloc.s  4
0x68684  stelem.ref
0x68685  call     string [mscorlib]System.String::Format(string, object[])
0x6868a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x6868f  throw
0x68690  ldstr    aSolutionImport// "Solution import succeded, error occured"...
0x68695  ldloc.s  4
0x68697  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6869c  ldloc.s  4
0x6869e  call     string [mscorlib]System.String::Format(string, object, object)
0x686a3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x686a8  throw
0x686a9  ret
```
