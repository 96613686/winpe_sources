# Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::ImportItem

- ea: `0xa50`
- end: `0xc7b`
- name: `Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::ImportItem`
- size: `555`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xa50`
- `0xc80`
- `0xd30`
- `0x1100`

## string_xrefs

- `0xa9e`: `ContractTemplate`
- `0xad4`: `ContractTemplate`
- `0xb62`: `ContractTemplate`
- `0xad9`: `contracttemplateid`
- `0xadf`: `contracttemplateid`
- `0xb67`: `contracttemplateid`
- `0xb6d`: `contracttemplateid`
- `0xb08`: `ImportExportXml/SolutionManifest/UniqueName`
- `0xb1f`: `msdynce_Service`
- `0xb3b`: `Internal System Converted solution failed to import contract template. Retrying with cache flush.`
- `0xbcb`: `ContractTemplate_Upgrade_Conflict_NewAbbreviationMask`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldarg.0
0xa51  ldfld    class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0xa56  ldarg.0
0xa57  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_templateId
0xa5c  ldarg.0
0xa5d  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_langFilter
0xa62  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetContractTemplateNodeById(class [System.Xml]System.Xml.XmlDocument, string, string)
0xa67  stloc.0
0xa68  ldloc.0
0xa69  brtrue.s loc_A6C
0xa6b  ret
0xa6c  ldc.i4.s 0x25
0xa6e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0xa73  ldarg.0
0xa74  ldfld    class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0xa79  ldsfld   string [mscorlib]System.String::Empty
0xa7e  ldarg.0
0xa7f  ldfld    string Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_templateId
0xa84  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xa89  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa8e  ldarg.0
0xa8f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xa94  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xa99  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::get_ServiceInstance()
0xa9e  ldstr    aContracttempla_0// "ContractTemplate"
0xaa3  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ServiceTemplateService [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ITemplateServiceFactory::GetService(string)
0xaa8  stloc.1
0xaa9  ldarg.0
0xaaa  ldloc.0
0xaab  ldloc.1
0xaac  call     instance bool Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::AddUnmodifiedTemplateToSolutionComponent(class [System.Xml]System.Xml.XmlNode templateNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject templateService)
0xab1  brfalse.s loc_AB4
0xab3  ret
0xab4  newobj   instance void Microsoft.Crm.Tools.Service.ImportExportPublish.ContractTemplateConvertor::.ctor()
0xab9  ldarg.0
0xaba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xabf  ldloc.0
0xac0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.IXmlToBusinessEntityConvertor::GetBusinessEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class [System.Xml]System.Xml.XmlNode)
0xac5  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.ContractTemplate
0xaca  stloc.2
0xacb  ldnull
0xacc  stloc.3
0xacd  ldarg.0
0xace  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_importHelper
0xad3  ldloc.1
0xad4  ldstr    aContracttempla_0// "ContractTemplate"
0xad9  ldstr    aContracttempla_1// "contracttemplateid"
0xade  ldloc.2
0xadf  ldstr    aContracttempla_1// "contracttemplateid"
0xae4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xae9  unbox.any [mscorlib]System.Guid
0xaee  ldarg.0
0xaef  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xaf4  ldc.i4.0
0xaf5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject, string, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xafa  stloc.3
0xafb  leave    loc_B8F
0xb00  stloc.s  4
0xb02  ldarg.0
0xb03  ldfld    class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0xb08  ldstr    aImportexportxm_0// "ImportExportXml/SolutionManifest/Unique"...
0xb0d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xb12  stloc.s  5
0xb14  ldloc.s  5
0xb16  brfalse.s loc_B8B
0xb18  ldloc.s  5
0xb1a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xb1f  ldstr    aMsdynceService// "msdynce_Service"
0xb24  ldc.i4.5
0xb25  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xb2a  brfalse.s loc_B8B
0xb2c  ldloc.s  4
0xb2e  ldarg.0
0xb2f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xb34  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xb39  ldc.i4.s 0x18
0xb3b  ldstr    aInternalSystem// "Internal System Converted solution fail"...
0xb40  ldc.i4.0
0xb41  newarr   [mscorlib]System.Object
0xb46  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb4b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0xb50  ldarg.0
0xb51  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xb56  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb5b  ldarg.0
0xb5c  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::_importHelper
0xb61  ldloc.1
0xb62  ldstr    aContracttempla_0// "ContractTemplate"
0xb67  ldstr    aContracttempla_1// "contracttemplateid"
0xb6c  ldloc.2
0xb6d  ldstr    aContracttempla_1// "contracttemplateid"
0xb72  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xb77  unbox.any [mscorlib]System.Guid
0xb7c  ldarg.0
0xb7d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xb82  ldc.i4.0
0xb83  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::TryGetEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject, string, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xb88  stloc.3
0xb89  br.s     loc_B8D
0xb8b  rethrow
0xb8d  leave.s  loc_B8F
0xb8f  nop
0xb90  ldarg.0
0xb91  call     instance bool [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Setup()
0xb96  brfalse.s loc_BE4
0xb98  ldarg.0
0xb99  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xb9e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xba3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0xba8  brfalse.s loc_BBC
0xbaa  ldarg.0
0xbab  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xbb0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbb5  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationCulture()
0xbba  br.s     loc_BC1
0xbbc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbc1  stloc.s  7
0xbc3  ldloc.1
0xbc4  ldloc.3
0xbc5  ldloc.2
0xbc6  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.LocalizationHelper::get_Resources()
0xbcb  ldstr    aContracttempla_4// "ContractTemplate_Upgrade_Conflict_NewAb"...
0xbd0  ldloc.s  7
0xbd2  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0xbd7  ldarg.0
0xbd8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xbdd  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ServiceTemplateService::Upgrade(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbe2  br.s     loc_C04
0xbe4  ldloc.3
0xbe5  brtrue.s loc_BF7
0xbe7  ldloc.1
0xbe8  ldloc.2
0xbe9  ldarg.0
0xbea  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xbef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xbf4  pop
0xbf5  br.s     loc_C04
0xbf7  ldloc.1
0xbf8  ldloc.2
0xbf9  ldarg.0
0xbfa  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::context
0xbff  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc09  ldsfld   string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ContractTemplateImportSuccessMessage
0xc0e  ldc.i4.1
0xc0f  newarr   [mscorlib]System.Object
0xc14  dup
0xc15  ldc.i4.0
0xc16  ldloc.2
0xc17  ldstr    aAbbreviation// "abbreviation"
0xc1c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xc21  stelem.ref
0xc22  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc27  stloc.s  6
0xc29  ldarg.0
0xc2a  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::tracer
0xc2f  ldloc.s  6
0xc31  ldc.i4.1
0xc32  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string, int32)
0xc37  leave.s  loc_C7A
0xc39  stloc.s  8
0xc3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc40  ldsfld   string [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ContractTemplateImportErrorMessage
0xc45  ldc.i4.1
0xc46  newarr   [mscorlib]System.Object
0xc4b  dup
0xc4c  ldc.i4.0
0xc4d  ldloc.2
0xc4e  ldstr    aAbbreviation// "abbreviation"
0xc53  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xc58  stelem.ref
0xc59  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xc5e  stloc.s  9
0xc60  ldarg.0
0xc61  ldfld    class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.Service.ImportExportPublish.ImportContractTemplateHandler::tracer
0xc66  ldloc.s  9
0xc68  ldloc.s  8
0xc6a  ldc.i4.3
0xc6b  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string, class [mscorlib]System.Exception, int32)
0xc70  ldloc.s  9
0xc72  ldloc.s  8
0xc74  newobj   instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportContractTemplateException::.ctor(string, class [mscorlib]System.Exception)
0xc79  throw
0xc7a  ret
```
