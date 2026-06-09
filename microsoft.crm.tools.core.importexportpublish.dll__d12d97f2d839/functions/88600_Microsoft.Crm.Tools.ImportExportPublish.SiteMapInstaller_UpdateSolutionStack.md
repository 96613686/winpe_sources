# Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::UpdateSolutionStack

- ea: `0x88600`
- end: `0x888c5`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::UpdateSolutionStack`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x881a0`

## callees

- `0x88600`

## string_xrefs

- `0x8865a`: `sitemapxml`
- `0x8878a`: `sitemapxml`
- `0x8883c`: `sitemapxml`
- `0x8879f`: `sitemapxmlmanaged`
- `0x88851`: `sitemapxmlmanaged`
- `0x88675`: `full siteMapXml is expected to update base solution`
- `0x88692`: `SiteMap merged Xml : {0}`
- `0x886dd`: `Last SiteMap xml after updating all the sitemap instances above the solution with current context: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x88600  ldarg.3
0x88601  ldstr    aStates// "states"
0x88606  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8860b  ldarg.2
0x8860c  ldstr    aSitemapnode// "siteMapNode"
0x88611  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x88616  ldnull
0x88617  stloc.0
0x88618  ldarg.2
0x88619  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8861e  stloc.1
0x8861f  ldarg.2
0x88620  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::ImportingFullFormXml(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x88625  stloc.2
0x88626  ldarg.3
0x88627  ldarg.0
0x88628  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x8862d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x88632  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetPriorEntityInstance(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x88637  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap
0x8863c  stloc.3
0x8863d  ldloc.3
0x8863e  brfalse.s loc_88672
0x88640  ldloc.2
0x88641  brfalse.s loc_88652
0x88643  ldarg.3
0x88644  ldarg.2
0x88645  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8864a  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::CalculateSiteMapInstallTimeXmlDiff(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, string)
0x8864f  stloc.0
0x88650  br.s     loc_88659
0x88652  ldarg.2
0x88653  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x88658  stloc.0
0x88659  ldloc.3
0x8865a  ldstr    aSitemapxml// "sitemapxml"
0x8865f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x88664  castclass [mscorlib]System.String
0x88669  ldloc.0
0x8866a  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::MergeSiteMapXmlDiff(string, string)
0x8866f  stloc.1
0x88670  br.s     loc_88680
0x88672  ldloc.2
0x88673  brtrue.s loc_88680
0x88675  ldstr    aFullSitemapxml// "full siteMapXml is expected to update b"...
0x8867a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x8867f  throw
0x88680  ldarg.0
0x88681  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88686  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8868b  ldc.i4.s 0x11
0x8868d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x88692  ldstr    aSitemapMergedX// "SiteMap merged Xml : {0}"
0x88697  ldc.i4.1
0x88698  newarr   [mscorlib]System.Object
0x8869d  dup
0x8869e  ldc.i4.0
0x8869f  ldloc.1
0x886a0  stelem.ref
0x886a1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x886a6  ldc.i4.0
0x886a7  newarr   [mscorlib]System.Object
0x886ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x886b1  ldarg.3
0x886b2  ldloc.1
0x886b3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x886b8  ldarg.0
0x886b9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x886be  ldarg.0
0x886bf  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_setup
0x886c4  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::RecalculateSolutionStacks(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x886c9  stloc.s  4
0x886cb  ldarg.0
0x886cc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x886d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x886d6  ldc.i4.s 0x11
0x886d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x886dd  ldstr    aLastSitemapXml// "Last SiteMap xml after updating all the"...
0x886e2  ldc.i4.1
0x886e3  newarr   [mscorlib]System.Object
0x886e8  dup
0x886e9  ldc.i4.0
0x886ea  ldloc.s  4
0x886ec  stelem.ref
0x886ed  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x886f2  ldc.i4.0
0x886f3  newarr   [mscorlib]System.Object
0x886f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x886fd  ldarg.3
0x886fe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetLastManagedEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState)
0x88703  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap
0x88708  stloc.s  5
0x8870a  ldarg.s  4
0x8870c  ldarg.0
0x8870d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88712  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetSiteMapIdUsingUniqueName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88717  stloc.s  6
0x88719  ldarg.1
0x8871a  brfalse.s loc_8872F
0x8871c  ldloc.s  5
0x8871e  ldstr    aSitemapid// "sitemapid"
0x88723  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x88728  unbox.any [mscorlib]System.Guid
0x8872d  stloc.s  6
0x8872f  ldloc.s  6
0x88731  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x88736  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8873b  brtrue.s loc_88740
0x8873d  ldc.i4.1
0x8873e  br.s     loc_88741
0x88740  ldc.i4.0
0x88741  ldarg.1
0x88742  or
0x88743  brfalse  loc_887F4
0x88748  ldarg.0
0x88749  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x8874e  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88753  stloc.s  7
0x88755  ldloc.s  7
0x88757  ldstr    aSitemapid// "sitemapid"
0x8875c  ldloc.s  6
0x8875e  box      [mscorlib]System.Guid
0x88763  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88768  ldstr    aSitemapname// "sitemapname"
0x8876d  ldarg.0
0x8876e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88773  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88778  brfalse.s loc_88788
0x8877a  ldloc.s  7
0x8877c  ldstr    aSitemapname// "sitemapname"
0x88781  ldarg.s  5
0x88783  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88788  ldloc.s  7
0x8878a  ldstr    aSitemapxml// "sitemapxml"
0x8878f  ldloc.1
0x88790  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88795  ldloc.0
0x88796  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8879b  brtrue.s loc_887AA
0x8879d  ldloc.s  7
0x8879f  ldstr    aSitemapxmlmana// "sitemapxmlmanaged"
0x887a4  ldloc.0
0x887a5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x887aa  ldstr    aIsappaware// "isappaware"
0x887af  ldarg.0
0x887b0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x887b5  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x887ba  brfalse.s loc_887D1
0x887bc  ldloc.s  7
0x887be  ldstr    aIsappaware// "isappaware"
0x887c3  ldarg.1
0x887c4  ldc.i4.0
0x887c5  ceq
0x887c7  box      [mscorlib]System.Boolean
0x887cc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x887d1  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x887d6  dup
0x887d7  ldarg.0
0x887d8  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_setup
0x887dd  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::set_IsSetup(bool)
0x887e2  ldloc.s  7
0x887e4  ldarg.0
0x887e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x887ea  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x887ef  br       loc_888C2
0x887f4  ldarg.1
0x887f5  brtrue   loc_888C2
0x887fa  ldarg.0
0x887fb  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88800  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88805  stloc.s  8
0x88807  ldloc.s  8
0x88809  ldstr    aSitemapid// "sitemapid"
0x8880e  ldloc.s  6
0x88810  box      [mscorlib]System.Guid
0x88815  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8881a  ldstr    aSitemapname// "sitemapname"
0x8881f  ldarg.0
0x88820  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88825  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8882a  brfalse.s loc_8883A
0x8882c  ldloc.s  8
0x8882e  ldstr    aSitemapname// "sitemapname"
0x88833  ldarg.s  5
0x88835  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8883a  ldloc.s  8
0x8883c  ldstr    aSitemapxml// "sitemapxml"
0x88841  ldloc.1
0x88842  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88847  ldloc.0
0x88848  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8884d  brtrue.s loc_8885C
0x8884f  ldloc.s  8
0x88851  ldstr    aSitemapxmlmana// "sitemapxmlmanaged"
0x88856  ldloc.0
0x88857  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8885c  ldstr    aIsappaware// "isappaware"
0x88861  ldarg.0
0x88862  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88867  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8886c  brfalse.s loc_88883
0x8886e  ldloc.s  8
0x88870  ldstr    aIsappaware// "isappaware"
0x88875  ldarg.1
0x88876  ldc.i4.0
0x88877  ceq
0x88879  box      [mscorlib]System.Boolean
0x8887e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88883  ldstr    aSitemapnameuni// "sitemapnameunique"
0x88888  ldarg.0
0x88889  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x8888e  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88893  brfalse.s loc_888A3
0x88895  ldloc.s  8
0x88897  ldstr    aSitemapnameuni// "sitemapnameunique"
0x8889c  ldarg.s  4
0x8889e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x888a3  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x888a8  dup
0x888a9  ldarg.0
0x888aa  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_setup
0x888af  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::set_IsSetup(bool)
0x888b4  ldloc.s  8
0x888b6  ldarg.0
0x888b7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x888bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::CreateAppSiteMap(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x888c1  pop
0x888c2  ldloc.s  4
0x888c4  ret
```
