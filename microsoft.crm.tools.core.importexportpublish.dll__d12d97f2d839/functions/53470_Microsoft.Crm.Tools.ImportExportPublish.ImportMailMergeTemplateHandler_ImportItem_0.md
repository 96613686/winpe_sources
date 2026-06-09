# Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::ImportItem_0

- ea: `0x53470`
- end: `0x538dd`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::ImportItem_0`
- size: `1133`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x35bb0`
- `0x4ca60`
- `0x50510`
- `0x508e0`
- `0x50c30`
- `0x50fd0`
- `0x52050`
- `0x522e0`
- `0x53470`
- `0x538e0`
- `0x63780`
- `0x63b10`
- `0x63db0`
- `0x63df0`
- `0x8f0b0`
- `0x94c90`

## string_xrefs

- `0x535ea`: `mailmergetemplateid`
- `0x5367b`: `mailmergetemplateid`
- `0x53681`: `mailmergetemplateid`
- `0x5370b`: `mailmergetemplateid`
- `0x5372d`: `mailmergetemplateid`
- `0x53763`: `mailmergetemplateid`
- `0x537ad`: `mailmergetemplateid`
- `0x5383c`: `mailmergetemplateid`
- `0x5353f`: `templatetypecode`
- `0x535d8`: `componentstate`
- `0x53629`: `componentstate`
- `0x534c5`: `MailMergeTemplate`
- `0x53676`: `MailMergeTemplate`
- `0x53772`: `MailMergeTemplate`
- `0x5384b`: `MailMergeTemplate`
- `0x53560`: `The {0} mail merge template was not imported because the {1} entity associated with this template is not in the target system.`
- `0x536ee`: `EmailTemplate_Upgrade_Conflict_NewTitleMask`
- `0x5379f`: `No update since the template '{0}' already exists.`

## pseudocode

```c

```

## disassembly

```asm
0x53470  ldarg.0
0x53471  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x53476  ldarg.0
0x53477  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::_templateId
0x5347c  ldarg.0
0x5347d  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::_langFilter
0x53482  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetMailMergeTemplateNodeById(class [System.Xml]System.Xml.XmlDocument importDocument, string templateId, [opt] string langFilter)
0x53487  stloc.0
0x53488  ldloc.0
0x53489  brtrue.s loc_5348C
0x5348b  ret
0x5348c  ldc.i4.s 0x27
0x5348e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x53493  ldarg.0
0x53494  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x53499  ldsfld   string [mscorlib]System.String::Empty
0x5349e  ldarg.0
0x5349f  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::_templateId
0x534a4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x534a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x534ae  ldarg.0
0x534af  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x534b4  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x534b9  ldarg.0
0x534ba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x534bf  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.MailMergeTemplate::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x534c4  stloc.1
0x534c5  ldstr    aMailmergetempl_2// "MailMergeTemplate"
0x534ca  ldarg.0
0x534cb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x534d0  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x534d5  stloc.2
0x534d6  ldarg.0
0x534d7  ldloc.0
0x534d8  ldloc.2
0x534d9  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::AddUnmodifiedTemplateToSolutionComponent(class [System.Xml]System.Xml.XmlNode templateNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject templateService)
0x534de  brfalse.s loc_534E1
0x534e0  ret
0x534e1  ldc.i4   0x2392
0x534e6  call     class Microsoft.Crm.Tools.ImportExportPublish.IXmlToBusinessEntityConvertor Microsoft.Crm.Tools.ImportExportPublish.XmlToBusinessEntityConvertorFactory::GetConvertor(int32 objectTypeCode)
0x534eb  ldarg.0
0x534ec  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x534f1  ldloc.0
0x534f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.Tools.ImportExportPublish.IXmlToBusinessEntityConvertor::GetBusinessEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [System.Xml]System.Xml.XmlNode node)
0x534f7  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.MailMergeTemplate
0x534fc  stloc.1
0x534fd  ldloc.0
0x534fe  ldstr    aEntityplatform// "entityPlatformName"
0x53503  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x53508  stloc.3
0x53509  ldloc.3
0x5350a  brfalse  loc_5359F
0x5350f  ldloc.3
0x53510  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x53515  stloc.s  5
0x53517  ldloc.1
0x53518  ldstr    aName// "name"
0x5351d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x53522  castclass [mscorlib]System.String
0x53527  stloc.s  6
0x53529  ldarg.0
0x5352a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::_importHelper
0x5352f  ldloc.s  5
0x53531  ldc.i4.2
0x53532  callvirt instance int32 Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::RetrieveOTC(string entityName, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType mapping)
0x53537  stloc.s  7
0x53539  ldloc.s  7
0x5353b  ldc.i4.0
0x5353c  blt.s    loc_53552
0x5353e  ldloc.1
0x5353f  ldstr    aTemplatetypeco// "templatetypecode"
0x53544  ldloc.s  7
0x53546  box      [mscorlib]System.Int32
0x5354b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x53550  br.s     loc_5359F
0x53552  ldnull
0x53553  ldarg.0
0x53554  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x53559  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5355e  ldc.i4.s 0x17
0x53560  ldstr    aThe0MailMergeT// "The {0} mail merge template was not imp"...
0x53565  ldc.i4.2
0x53566  newarr   [mscorlib]System.Object
0x5356b  dup
0x5356c  ldc.i4.0
0x5356d  ldloc.s  6
0x5356f  stelem.ref
0x53570  dup
0x53571  ldc.i4.1
0x53572  ldloc.s  5
0x53574  stelem.ref
0x53575  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5357a  ldc.i4.2
0x5357b  newarr   [mscorlib]System.String
0x53580  stloc.s  8
0x53582  ldloc.s  8
0x53584  ldc.i4.0
0x53585  ldloc.s  6
0x53587  stelem.ref
0x53588  ldloc.s  8
0x5358a  ldc.i4.1
0x5358b  ldloc.s  5
0x5358d  stelem.ref
0x5358e  ldc.i4   0x80048480
0x53593  ldloc.s  8
0x53595  stloc.s  9
0x53597  ldloc.s  9
0x53599  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5359e  throw
0x5359f  ldnull
0x535a0  stloc.s  4
0x535a2  ldarg.0
0x535a3  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x535a8  brfalse  loc_5366F
0x535ad  ldloc.1
0x535ae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x535b3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x535b8  ldarg.0
0x535b9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x535be  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x535c3  stloc.s  0xA
0x535c5  ldloc.s  0xA
0x535c7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x535cc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x535d1  ldloc.s  0xA
0x535d3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x535d8  ldstr    aComponentstate_0// "componentstate"
0x535dd  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x535e2  ldloc.s  0xA
0x535e4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x535e9  ldloc.1
0x535ea  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x535ef  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x535f4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddPrimaryKeyCondition(object)
0x535f9  pop
0x535fa  ldloc.2
0x535fb  ldloc.s  0xA
0x535fd  ldc.i4.2
0x535fe  ldarg.0
0x535ff  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x53604  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x53609  stloc.s  0xB
0x5360b  ldloc.s  0xB
0x5360d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x53612  ldc.i4.0
0x53613  ble      loc_536A3
0x53618  ldloc.s  0xB
0x5361a  ldc.i4.0
0x5361b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x53620  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.MailMergeTemplate
0x53625  stloc.s  4
0x53627  ldloc.s  4
0x53629  ldstr    aComponentstate_0// "componentstate"
0x5362e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x53633  unbox.any [mscorlib]System.Int32
0x53638  ldc.i4.2
0x53639  bne.un.s loc_536A3
0x5363b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53640  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::MailMergeTemplateImportPreviouslyDeletedMessage
0x53645  ldc.i4.1
0x53646  newarr   [mscorlib]System.Object
0x5364b  dup
0x5364c  ldc.i4.0
0x5364d  ldloc.1
0x5364e  ldstr    aName// "name"
0x53653  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x53658  stelem.ref
0x53659  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5365e  stloc.s  0xC
0x53660  ldarg.0
0x53661  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::tracer
0x53666  ldloc.s  0xC
0x53668  ldc.i4.1
0x53669  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x5366e  ret
0x5366f  ldarg.0
0x53670  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::_importHelper
0x53675  ldloc.2
0x53676  ldstr    aMailmergetempl_2// "MailMergeTemplate"
0x5367b  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x53680  ldloc.1
0x53681  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x53686  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5368b  unbox.any [mscorlib]System.Guid
0x53690  ldarg.0
0x53691  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x53696  ldc.i4.0
0x53697  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, string platformName, string idColumnName, valuetype [mscorlib]System.Guid primaryId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool retrieveDeleted)
0x5369c  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.MailMergeTemplate
0x536a1  stloc.s  4
0x536a3  nop
0x536a4  ldarg.0
0x536a5  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x536aa  brtrue.s loc_536C9
0x536ac  ldarg.0
0x536ad  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x536b2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x536b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x536bc  ldarg.0
0x536bd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x536c2  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsInternalSystemConvertedSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x536c7  brfalse.s loc_536DD
0x536c9  ldloc.2
0x536ca  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.MailMergeTemplateService
0x536cf  stloc.s  0xF
0x536d1  ldloc.s  0xF
0x536d3  brfalse.s loc_536DD
0x536d5  ldloc.s  0xF
0x536d7  ldc.i4.1
0x536d8  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AttachmentServiceBase::set_SkipFileNameAndSizeValidation(bool)
0x536dd  ldc.i4.0
0x536de  stloc.s  0xD
0x536e0  ldarg.0
0x536e1  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x536e6  brfalse.s loc_53748
0x536e8  ldloc.s  4
0x536ea  brtrue.s loc_53748
0x536ec  ldarg.0
0x536ed  ldloc.1
0x536ee  ldstr    aEmailtemplateU// "EmailTemplate_Upgrade_Conflict_NewTitle"...
0x536f3  ldnull
0x536f4  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::GetNewTitleMaskForUpgradeTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity template, string resourceString, [opt] class [mscorlib]System.Collections.Generic.IDictionary`2<int32, bool> allLanguages)
0x536f9  stloc.s  0x10
0x536fb  ldloc.s  0x10
0x536fd  brtrue.s loc_53704
0x536ff  leave    loc_538DC
0x53704  ldarg.0
0x53705  ldloc.s  4
0x53707  ldloc.1
0x53708  ldloc.s  0x10
0x5370a  ldloc.2
0x5370b  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x53710  ldstr    aName// "name"
0x53715  ldc.i4.4
0x53716  newarr   [mscorlib]System.String
0x5371b  dup
0x5371c  ldc.i4.0
0x5371d  ldstr    aFilename_0// "filename"
0x53722  stelem.ref
0x53723  dup
0x53724  ldc.i4.1
0x53725  ldstr    aBody// "body"
0x5372a  stelem.ref
0x5372b  dup
0x5372c  ldc.i4.2
0x5372d  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x53732  stelem.ref
0x53733  dup
0x53734  ldc.i4.3
0x53735  ldstr    aName// "name"
0x5373a  stelem.ref
0x5373b  ldstr    aMailMerge// "Mail Merge"
0x53740  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::UpgradeTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity oldTemplate, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity newTemplate, string newTitleMask, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, string idAttribute, string nameAttribute, string[] columnSet, string traceTemplateType)
0x53745  ldc.i4.1
0x53746  stloc.s  0xD
0x53748  ldloc.s  0xD
0x5374a  brtrue   loc_53866
0x5374f  ldloc.s  4
0x53751  brtrue.s loc_53792
0x53753  ldloc.2
0x53754  ldloc.1
0x53755  ldarg.0
0x53756  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x5375b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x53760  pop
0x53761  ldloc.2
0x53762  ldloc.1
0x53763  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x53768  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5376d  unbox.any [mscorlib]System.Guid
0x53772  ldstr    aMailmergetempl_2// "MailMergeTemplate"
0x53777  ldarg.0
0x53778  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x5377d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x53782  ldarg.0
0x53783  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x53788  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::GrantAccessToOrganization(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5378d  br       loc_53866
0x53792  ldarg.0
0x53793  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x53798  brfalse.s loc_537DC
0x5379a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5379f  ldstr    aNoUpdateSinceT// "No update since the template '{0}' alre"...
0x537a4  ldc.i4.1
0x537a5  newarr   [mscorlib]System.Object
0x537aa  dup
0x537ab  ldc.i4.0
0x537ac  ldloc.1
0x537ad  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x537b2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x537b7  unbox.any [mscorlib]System.Guid
0x537bc  box      [mscorlib]System.Guid
0x537c1  stelem.ref
0x537c2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x537c7  stloc.s  0x11
0x537c9  ldarg.0
0x537ca  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportMailMergeTemplateHandler::tracer
0x537cf  ldloc.s  0x11
0x537d1  ldc.i4.1
0x537d2  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
  ... truncated ...
```
