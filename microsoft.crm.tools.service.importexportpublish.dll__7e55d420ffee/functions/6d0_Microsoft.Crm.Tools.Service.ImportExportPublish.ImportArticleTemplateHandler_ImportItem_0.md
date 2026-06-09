# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::ImportItem_0

- ea: `0x6d0`
- end: `0x8c5`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::ImportItem_0`
- size: `501`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x6d0`
- `0x8d0`
- `0x990`
- `0xf00`

## string_xrefs

- `0x72f`: `KbArticleTemplate`
- `0x779`: `KbArticleTemplate`
- `0x77e`: `kbarticletemplateid`
- `0x784`: `kbarticletemplateid`
- `0x804`: `KBArticleTemplate_Upgrade_Conflict_NewTitleMask`

## pseudocode

```c

```

## disassembly

```asm
0x6d0  ldarg.0
0x6d1  ldfld    class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x6d6  ldarg.0
0x6d7  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_templateId
0x6dc  ldarg.0
0x6dd  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_langFilter
0x6e2  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetArticleTemplateNodeById(class [System.Xml]System.Xml.XmlDocument, string, string)
0x6e7  stloc.0
0x6e8  ldloc.0
0x6e9  brtrue.s loc_6EC
0x6eb  ret
0x6ec  ldc.i4.s 0x26
0x6ee  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x6f3  ldarg.0
0x6f4  ldfld    class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x6f9  ldsfld   string [mscorlib]System.String::Empty
0x6fe  ldarg.0
0x6ff  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_templateId
0x704  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x709  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x70e  ldarg.0
0x70f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x714  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x719  ldarg.0
0x71a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x71f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x724  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate::.ctor(valuetype [mscorlib]System.Guid)
0x729  stloc.1
0x72a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::get_ServiceInstance()
0x72f  ldstr    aKbarticletempl_0// "KbArticleTemplate"
0x734  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ServiceTemplateService [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory::GetService(string)
0x739  stloc.2
0x73a  ldarg.0
0x73b  ldloc.0
0x73c  ldloc.2
0x73d  call     instance bool Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::AddUnmodifiedTemplateToSolutionComponent(class [System.Xml]System.Xml.XmlNode templateNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject templateService)
0x742  brfalse.s loc_745
0x744  ret
0x745  ldloc.1
0x746  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x74b  ldarg.0
0x74c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x751  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x756  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddPrimaryKey()
0x75b  newobj   instance void Microsoft.Crm.Tools.Service.ImportExportPublish.KbArticleTemplateConvertor::.ctor()
0x760  ldarg.0
0x761  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x766  ldloc.0
0x767  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.IXmlToBusinessEntityConvertor::GetBusinessEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [System.Xml]System.Xml.XmlNode)
0x76c  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate
0x771  stloc.1
0x772  ldarg.0
0x773  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::_importHelper
0x778  ldloc.2
0x779  ldstr    aKbarticletempl_0// "KbArticleTemplate"
0x77e  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x783  ldloc.1
0x784  ldstr    aKbarticletempl_1// "kbarticletemplateid"
0x789  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x78e  unbox.any [mscorlib]System.Guid
0x793  ldarg.0
0x794  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x799  ldc.i4.0
0x79a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject, string, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x79f  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate
0x7a4  stloc.3
0x7a5  ldarg.0
0x7a6  call     instance bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0x7ab  brfalse.s loc_81D
0x7ad  ldarg.0
0x7ae  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x7b3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x7bd  brfalse.s loc_7D1
0x7bf  ldarg.0
0x7c0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x7c5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ca  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationCulture()
0x7cf  br.s     loc_7D6
0x7d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7d6  stloc.s  5
0x7d8  ldloc.1
0x7d9  ldstr    aLanguagecode// "languagecode"
0x7de  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x7e3  brtrue.s loc_7FC
0x7e5  ldloc.1
0x7e6  ldstr    aLanguagecode// "languagecode"
0x7eb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7f0  unbox.any [mscorlib]System.Int32
0x7f5  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x7fa  stloc.s  5
0x7fc  ldloc.2
0x7fd  ldloc.3
0x7fe  ldloc.1
0x7ff  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.LocalizationHelper::get_Resources()
0x804  ldstr    aKbarticletempl_5// "KBArticleTemplate_Upgrade_Conflict_NewT"...
0x809  ldloc.s  5
0x80b  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x810  ldarg.0
0x811  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x816  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ServiceTemplateService::Upgrade(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x81b  br.s     loc_84E
0x81d  ldloc.3
0x81e  brtrue.s loc_841
0x820  ldloc.1
0x821  ldstr    aIsactive// "isactive"
0x826  ldc.i4.1
0x827  box      [mscorlib]System.Boolean
0x82c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x831  ldloc.2
0x832  ldloc.1
0x833  ldarg.0
0x834  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x839  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x83e  pop
0x83f  br.s     loc_84E
0x841  ldloc.2
0x842  ldloc.1
0x843  ldarg.0
0x844  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::context
0x849  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x84e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x853  ldsfld   string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ArticleTemplateImportSuccessMessage
0x858  ldc.i4.1
0x859  newarr   [mscorlib]System.Object
0x85e  dup
0x85f  ldc.i4.0
0x860  ldloc.1
0x861  ldstr    aTitle// "title"
0x866  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86b  stelem.ref
0x86c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x871  stloc.s  4
0x873  ldarg.0
0x874  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::tracer
0x879  ldloc.s  4
0x87b  ldc.i4.1
0x87c  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string, int32)
0x881  leave.s  loc_8C4
0x883  stloc.s  6
0x885  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x88a  ldsfld   string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ArticleTemplateImportErrorMessage
0x88f  ldc.i4.1
0x890  newarr   [mscorlib]System.Object
0x895  dup
0x896  ldc.i4.0
0x897  ldloc.1
0x898  ldstr    aTitle// "title"
0x89d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8a2  stelem.ref
0x8a3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8a8  stloc.s  7
0x8aa  ldarg.0
0x8ab  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ImportArticleTemplateHandler::tracer
0x8b0  ldloc.s  7
0x8b2  ldloc.s  6
0x8b4  ldc.i4.3
0x8b5  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string, class [mscorlib]System.Exception, int32)
0x8ba  ldloc.s  7
0x8bc  ldloc.s  6
0x8be  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportArticleTemplateException::.ctor(string, class [mscorlib]System.Exception)
0x8c3  throw
0x8c4  ret
```
