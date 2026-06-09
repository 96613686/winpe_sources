# Microsoft.Crm.Tools.ImportExportPublish.ImportTeamTemplateHandler::ImportItem

- ea: `0x63610`
- end: `0x63746`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportTeamTemplateHandler::ImportItem`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x35e50`
- `0x46410`
- `0x464d0`
- `0x508e0`
- `0x63610`
- `0x63db0`
- `0x63df0`
- `0x686f0`

## string_xrefs

- `0x63616`: `/ImportExportXml/TeamTemplates`
- `0x6362d`: `TeamTemplate`
- `0x636a3`: `Team Template with name {0} can not be created or updated since the entity with OTC - {1} is not enabled for access teams.`
- `0x636aa`: `teamtemplatename`

## pseudocode

```c

```

## disassembly

```asm
0x63610  ldarg.0
0x63611  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_doc
0x63616  ldstr    aImportexportxm_169// "/ImportExportXml/TeamTemplates"
0x6361b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x63620  stloc.0
0x63621  ldloc.0
0x63622  brtrue.s loc_63625
0x63624  ret
0x63625  nop
0x63626  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.TeamTemplateService::.ctor()
0x6362b  stloc.1
0x6362c  ldloc.0
0x6362d  ldstr    aTeamtemplate// "TeamTemplate"
0x63632  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x63637  stloc.2
0x63638  ldloc.2
0x63639  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6363e  stloc.3
0x6363f  br       loc_636E2
0x63644  ldloc.3
0x63645  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6364a  castclass [System.Xml]System.Xml.XmlNode
0x6364f  stloc.s  4
0x63651  ldarg.0
0x63652  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x63657  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6365c  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.TeamTemplate::.ctor(valuetype [mscorlib]System.Guid)
0x63661  stloc.s  5
0x63663  ldarg.0
0x63664  ldloc.s  4
0x63666  ldloc.s  5
0x63668  ldc.i4.0
0x63669  newarr   [mscorlib]System.String
0x6366e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::InitializeEntity(class [System.Xml]System.Xml.XmlNode entityNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, string[] excludedNodes)
0x63673  ldloc.1
0x63674  ldloc.s  5
0x63676  ldstr    aObjecttypecode_0// "objecttypecode"
0x6367b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63680  unbox.any [mscorlib]System.Int32
0x63685  ldarg.0
0x63686  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x6368b  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.TeamTemplateService::IsEntityEnabledForCollaboration(int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63690  brtrue.s loc_636D3
0x63692  ldarg.0
0x63693  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x63698  ldarg.0
0x63699  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x6369e  ldstr    aWarning// "warning"
0x636a3  ldstr    aTeamTemplateWi// "Team Template with name {0} can not be "...
0x636a8  ldloc.s  5
0x636aa  ldstr    aTeamtemplatena// "teamtemplatename"
0x636af  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x636b4  ldloc.s  5
0x636b6  ldstr    aObjecttypecode_0// "objecttypecode"
0x636bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x636c0  call     string [mscorlib]System.String::Format(string, object, object)
0x636c5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x636ca  ldc.i4.0
0x636cb  ldc.i4.0
0x636cc  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x636d1  br.s     loc_636E2
0x636d3  ldarg.0
0x636d4  ldloc.1
0x636d5  ldloc.s  5
0x636d7  ldarg.0
0x636d8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_context
0x636dd  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::EnsureEntityExisted(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x636e2  ldloc.3
0x636e3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x636e8  brtrue   loc_63644
0x636ed  leave.s  loc_63703
0x636ef  ldloc.3
0x636f0  isinst   [mscorlib]System.IDisposable
0x636f5  stloc.s  6
0x636f7  ldloc.s  6
0x636f9  brfalse.s loc_63702
0x636fb  ldloc.s  6
0x636fd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63702  endfinally
0x63703  leave.s  loc_6370F
0x63705  ldloc.2
0x63706  brfalse.s loc_6370E
0x63708  ldloc.2
0x63709  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6370e  endfinally
0x6370f  ldarg.0
0x63710  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x63715  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::TeamTemplateImportSuccessMessage
0x6371a  ldc.i4.1
0x6371b  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x63720  leave.s  loc_63745
0x63722  stloc.s  7
0x63724  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::TeamTemplateImportErrorMessage
0x63729  stloc.s  8
0x6372b  ldarg.0
0x6372c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportEntityHandlerBase::_tracer
0x63731  ldloc.s  8
0x63733  ldloc.s  7
0x63735  ldc.i4.1
0x63736  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x6373b  ldloc.s  8
0x6373d  ldloc.s  7
0x6373f  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportGenericEntitiesException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x63744  throw
0x63745  ret
```
