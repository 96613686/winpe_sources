# Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::ImportItem

- ea: `0x5c510`
- end: `0x5cd07`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::ImportItem`
- size: `2039`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xa1b0`
- `0x35020`
- `0x35090`
- `0x35100`
- `0x4cb60`
- `0x4cba0`
- `0x50510`
- `0x50580`
- `0x505c0`
- `0x508a0`
- `0x508e0`
- `0x50d00`
- `0x50dc0`
- `0x50ee0`
- `0x51090`
- `0x511e0`
- `0x52610`
- `0x5c480`
- `0x5c490`
- `0x5c510`
- `0x5d110`
- `0x5d1d0`
- `0x5d4d0`
- `0x5d6c0`
- `0x5d7e0`
- `0x5d800`
- `0x63db0`
- `0x63df0`
- `0x686b0`
- `0x686f0`

## string_xrefs

- `0x5c823`: `componentstate`
- `0x5ca7d`: `componentstate`
- `0x5c745`: `layoutxml/grid`
- `0x5cb7e`: `The following View was undeleted during the import process. Name: '{0}'.  Id = {1}`

## pseudocode

```c

```

## disassembly

```asm
0x5c510  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionAwareLocalizedLabelService::.ctor()
0x5c515  stloc.0
0x5c516  ldarg.0
0x5c517  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5c51c  ldarg.0
0x5c51d  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_EntityName()
0x5c522  ldarg.0
0x5c523  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::importHelper
0x5c528  ldarg.0
0x5c529  ldflda   int32 Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::objectTypeCode
0x5c52e  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetEntityNodeAndAdjustObjectTypeCode(class [System.Xml]System.Xml.XmlDocument importDocument, string entityName, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, int32& objectTypeCode)
0x5c533  stloc.1
0x5c534  ldloc.1
0x5c535  brtrue.s loc_5C538
0x5c537  ret
0x5c538  ldarg.0
0x5c539  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetOriginalBaseLanguage()
0x5c53e  stloc.2
0x5c53f  ldloc.1
0x5c540  ldstr    aSavedqueries// "SavedQueries"
0x5c545  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5c54a  stloc.3
0x5c54b  ldloc.3
0x5c54c  brtrue.s loc_5C54F
0x5c54e  ret
0x5c54f  ldloc.3
0x5c550  ldstr    aSavedqueries_0// "savedqueries"
0x5c555  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5c55a  stloc.s  4
0x5c55c  ldloc.s  4
0x5c55e  brtrue.s loc_5C561
0x5c560  ret
0x5c561  ldloc.s  4
0x5c563  ldstr    aSavedquery_1// "savedquery"
0x5c568  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5c56d  stloc.s  5
0x5c56f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x5c574  stloc.s  6
0x5c576  ldloc.1
0x5c577  call     int32 Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetEntityObjectTypeCode(class [System.Xml]System.Xml.XmlNode entityNode)
0x5c57c  stloc.s  0xE
0x5c57e  ldloca.s 0xE
0x5c580  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c585  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5c58a  stloc.s  7
0x5c58c  ldloc.s  7
0x5c58e  ldstr    a1_0// "-1"
0x5c593  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5c598  brfalse.s loc_5C5AC
0x5c59a  ldarg.0
0x5c59b  ldflda   int32 Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::objectTypeCode
0x5c5a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c5a5  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5c5aa  stloc.s  7
0x5c5ac  ldarg.0
0x5c5ad  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c5b2  ldarg.0
0x5c5b3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c5b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5c5bd  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x5c5c2  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x5c5c7  stloc.s  8
0x5c5c9  ldarg.0
0x5c5ca  ldc.i4.0
0x5c5cb  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::TryCheckDefaultSavedQuery(int32 queryType)
0x5c5d0  stloc.s  9
0x5c5d2  ldarg.0
0x5c5d3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c5d8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c5dd  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x5c5e2  stloc.s  0xA
0x5c5e4  ldarg.0
0x5c5e5  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::RetrieveActvityFeedsFollowSavedQueryIds()
0x5c5ea  stloc.s  0xB
0x5c5ec  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x5c5f1  stloc.s  0xC
0x5c5f3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5c5f8  stloc.s  0xD
0x5c5fa  ldloc.s  5
0x5c5fc  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5c601  stloc.s  0xF
0x5c603  br       loc_5CC0F
0x5c608  ldloc.s  0xF
0x5c60a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5c60f  castclass [System.Xml]System.Xml.XmlNode
0x5c614  stloc.s  0x10
0x5c616  ldloc.s  0x10
0x5c618  ldstr    aIsquickfindque// "isquickfindquery"
0x5c61d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c622  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5c627  ldstr    a1// "1"
0x5c62c  ldc.i4.4
0x5c62d  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5c632  stloc.s  0x11
0x5c634  ldloc.s  0x10
0x5c636  ldstr    aQuerytype// "querytype"
0x5c63b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c640  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5c645  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c64a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x5c64f  stloc.s  0x12
0x5c651  ldarg.0
0x5c652  ldloc.s  0x11
0x5c654  ldloc.s  0x12
0x5c656  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::ShouldProcessQueryOfGivenType(bool isQuickFindQuery, int32 queryType)
0x5c65b  brfalse  loc_5CC0F
0x5c660  ldloc.s  0xA
0x5c662  ldloc.s  0x10
0x5c664  call     bool Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::IsNodeValidForLcid(int32 language, class [System.Xml]System.Xml.XPath.IXPathNavigable nodeNavigable)
0x5c669  brfalse  loc_5CC0F
0x5c66e  ldloc.s  0x10
0x5c670  ldstr    aSavedqueryid// "savedqueryid"
0x5c675  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c67a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x5c67f  stloc.s  0x13
0x5c681  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x5c686  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x5c68b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_SolutionSegmentation()
0x5c690  ldarg.0
0x5c691  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c696  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c69b  brfalse.s loc_5C6BB
0x5c69d  ldarg.0
0x5c69e  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x5c6a3  brtrue.s loc_5C6BB
0x5c6a5  ldarg.0
0x5c6a6  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::createEntity
0x5c6ab  brtrue.s loc_5C6BB
0x5c6ad  ldloc.s  0xC
0x5c6af  ldloc.s  0x13
0x5c6b1  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x5c6b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5c6bb  ldloc.s  0x10
0x5c6bd  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5c6c2  ldstr    aUnmodified// "unmodified"
0x5c6c7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5c6cc  brtrue   loc_5CC0F
0x5c6d1  ldarg.0
0x5c6d2  ldc.i4.s 0x1A
0x5c6d4  ldloc.s  0x13
0x5c6d6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x5c6db  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::IsComponentToBeSkipped(int32 type, valuetype [mscorlib]System.Guid id)
0x5c6e0  brtrue.s loc_5C6F2
0x5c6e2  ldloc.s  0xB
0x5c6e4  ldloc.s  0x13
0x5c6e6  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x5c6eb  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x5c6f0  brfalse.s loc_5C70C
0x5c6f2  ldarg.0
0x5c6f3  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Parent()
0x5c6f8  ldarg.0
0x5c6f9  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x5c6fe  ldloc.s  0x13
0x5c700  ldc.i4.s 0x1A
0x5c702  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateSkippedComponentProgress(string path, string componentIdentifier, int32 componentType)
0x5c707  br       loc_5CC0F
0x5c70c  ldarg.0
0x5c70d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c712  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5c717  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_LanguageCode()
0x5c71c  stloc.s  0xE
0x5c71e  ldloca.s 0xE
0x5c720  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c725  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5c72a  stloc.s  0x14
0x5c72c  ldloc.s  0x10
0x5c72e  ldloc.s  0x14
0x5c730  ldloc.2
0x5c731  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetBaseLanguageName(class [System.Xml]System.Xml.XmlNode node, string baseLanguage, string originalBaseLanguage)
0x5c736  stloc.s  0x15
0x5c738  ldarg.0
0x5c739  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x5c73e  brtrue   loc_5C7DE
0x5c743  ldloc.s  0x10
0x5c745  ldstr    aLayoutxmlGrid// "layoutxml/grid"
0x5c74a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5c74f  stloc.s  0x1B
0x5c751  ldloc.s  0x1B
0x5c753  brfalse  loc_5C7DE
0x5c758  ldloc.s  0x1B
0x5c75a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5c75f  ldstr    aObject// "object"
0x5c764  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5c769  brfalse.s loc_5C7DE
0x5c76b  ldloc.s  0x1B
0x5c76d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5c772  ldstr    aObject// "object"
0x5c777  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5c77c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5c781  ldloc.s  7
0x5c783  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5c788  brfalse.s loc_5C7DE
0x5c78a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c78f  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::QueryImportErrorMessage2
0x5c794  ldc.i4.3
0x5c795  newarr   [mscorlib]System.Object
0x5c79a  dup
0x5c79b  ldc.i4.0
0x5c79c  ldloc.s  0x15
0x5c79e  stelem.ref
0x5c79f  dup
0x5c7a0  ldc.i4.1
0x5c7a1  ldarg.0
0x5c7a2  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_EntityName()
0x5c7a7  stelem.ref
0x5c7a8  dup
0x5c7a9  ldc.i4.2
0x5c7aa  ldarg.0
0x5c7ab  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::objectTypeCode
0x5c7b0  box      [mscorlib]System.Int32
0x5c7b5  stelem.ref
0x5c7b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5c7bb  stloc.s  0x1C
0x5c7bd  ldloc.s  0x1C
0x5c7bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5c7c4  stloc.s  0x1D
0x5c7c6  ldarg.0
0x5c7c7  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::tracer
0x5c7cc  ldloc.s  0x1C
0x5c7ce  ldloc.s  0x1D
0x5c7d0  ldc.i4.1
0x5c7d1  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x5c7d6  ldloc.s  0x1C
0x5c7d8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryOtcMismatchException::.ctor(string message)
0x5c7dd  throw
0x5c7de  ldstr    aSavedquery// "SavedQuery"
0x5c7e3  ldarg.0
0x5c7e4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c7e9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5c7ee  stloc.s  0x16
0x5c7f0  ldloc.s  0x16
0x5c7f2  ldstr    aSavedqueryid// "savedqueryid"
0x5c7f7  ldc.i4.0
0x5c7f8  ldloc.s  0x10
0x5c7fa  ldstr    aSavedqueryid// "savedqueryid"
0x5c7ff  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c804  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x5c809  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5c80e  pop
0x5c80f  ldstr    aSavedquery// "SavedQuery"
0x5c814  ldarg.0
0x5c815  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c81a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5c81f  stloc.s  0x17
0x5c821  ldloc.s  0x17
0x5c823  ldstr    aComponentstate_0// "componentstate"
0x5c828  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5c82d  ldloc.s  0x17
0x5c82f  ldstr    aSolutionid// "solutionid"
0x5c834  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5c839  ldloc.s  0x16
0x5c83b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x5c840  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5c845  ldarg.0
0x5c846  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c84b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5c850  stloc.s  0x18
0x5c852  ldloc.s  0x18
0x5c854  ldloc.s  0x16
0x5c856  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x5c85b  ldloc.s  0x18
0x5c85d  ldloc.s  0x17
0x5c85f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x5c864  ldloc.s  6
0x5c866  ldloc.s  0x18
0x5c868  ldc.i4.1
0x5c869  ldarg.0
0x5c86a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c86f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublishedMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5c874  stloc.s  0x19
0x5c876  ldloc.s  0x19
0x5c878  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5c87d  brtrue   loc_5C985
0x5c882  ldarg.0
0x5c883  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::importHelper
0x5c888  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_LookupNameMatches()
0x5c88d  brfalse  loc_5C985
0x5c892  ldstr    aSavedquery// "SavedQuery"
0x5c897  ldarg.0
0x5c898  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::context
0x5c89d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5c8a2  stloc.s  0x1E
0x5c8a4  ldloc.s  0x1E
0x5c8a6  ldstr    aName// "name"
0x5c8ab  ldc.i4.0
0x5c8ac  ldloc.s  0x15
0x5c8ae  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5c8b3  pop
0x5c8b4  ldloc.s  0x1E
0x5c8b6  ldstr    aReturnedtypeco// "returnedtypecode"
0x5c8bb  ldc.i4.0
0x5c8bc  ldarg.0
0x5c8bd  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportSavedQueryHandler::objectTypeCode
0x5c8c2  box      [mscorlib]System.Int32
0x5c8c7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5c8cc  pop
0x5c8cd  ldloc.s  0x16
0x5c8cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x5c8d4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5c8d9  ldarg.0
  ... truncated ...
```
