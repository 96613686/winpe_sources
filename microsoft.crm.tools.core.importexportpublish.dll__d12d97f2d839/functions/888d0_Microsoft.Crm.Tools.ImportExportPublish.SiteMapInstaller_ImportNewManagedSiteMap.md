# Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::ImportNewManagedSiteMap

- ea: `0x888d0`
- end: `0x88b92`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::ImportNewManagedSiteMap`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x881a0`

## callees

- `0x888d0`

## string_xrefs

- `0x88988`: `sitemapxml`
- `0x88a05`: `sitemapxml`
- `0x88a79`: `sitemapxml`
- `0x88b39`: `sitemapxml`
- `0x88a86`: `sitemapxmlmanaged`
- `0x8892a`: `full siteMapXml is expected to update an unmanaged siteMap`
- `0x88acf`: `full siteMapXml is expected to create a siteMap`

## pseudocode

```c

```

## disassembly

```asm
0x888d0  ldarg.3
0x888d1  brfalse.s loc_888DF
0x888d3  ldarg.s  5
0x888d5  ldstr    aStates// "states"
0x888da  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x888df  ldarg.s  4
0x888e1  ldstr    aSitemapnode// "siteMapNode"
0x888e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x888eb  ldnull
0x888ec  stloc.0
0x888ed  ldarg.s  4
0x888ef  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::ImportingFullFormXml(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x888f4  stloc.1
0x888f5  ldarg.1
0x888f6  ldarg.0
0x888f7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x888fc  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::IsExistingSiteMap(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88901  ldarg.3
0x88902  or
0x88903  brfalse  loc_88ACC
0x88908  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x8890d  stloc.2
0x8890e  ldarg.s  5
0x88910  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetLastManagedEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState)
0x88915  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap
0x8891a  stloc.3
0x8891b  ldloc.3
0x8891c  brtrue   loc_889F2
0x88921  ldarg.3
0x88922  brtrue   loc_889F2
0x88927  ldloc.1
0x88928  brtrue.s loc_88935
0x8892a  ldstr    aFullSitemapxml_0// "full siteMapXml is expected to update a"...
0x8892f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x88934  throw
0x88935  ldarg.0
0x88936  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x8893b  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88940  stloc.s  4
0x88942  ldloc.s  4
0x88944  ldstr    aSitemapid// "sitemapid"
0x88949  ldarg.1
0x8894a  ldarg.0
0x8894b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88950  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetSiteMapIdUsingUniqueName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88955  box      [mscorlib]System.Guid
0x8895a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8895f  ldstr    aSitemapname// "sitemapname"
0x88964  ldarg.0
0x88965  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x8896a  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8896f  brfalse.s loc_8897E
0x88971  ldloc.s  4
0x88973  ldstr    aSitemapname// "sitemapname"
0x88978  ldarg.2
0x88979  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8897e  ldarg.s  4
0x88980  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x88985  stloc.0
0x88986  ldloc.s  4
0x88988  ldstr    aSitemapxml// "sitemapxml"
0x8898d  ldarg.s  4
0x8898f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x88994  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88999  ldstr    aIsappaware// "isappaware"
0x8899e  ldarg.0
0x8899f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x889a4  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x889a9  brfalse.s loc_889C0
0x889ab  ldloc.s  4
0x889ad  ldstr    aIsappaware// "isappaware"
0x889b2  ldarg.3
0x889b3  ldc.i4.0
0x889b4  ceq
0x889b6  box      [mscorlib]System.Boolean
0x889bb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x889c0  ldstr    aSitemapnameuni// "sitemapnameunique"
0x889c5  ldarg.0
0x889c6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x889cb  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x889d0  brfalse.s loc_889DF
0x889d2  ldloc.s  4
0x889d4  ldstr    aSitemapnameuni// "sitemapnameunique"
0x889d9  ldarg.1
0x889da  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x889df  ldloc.2
0x889e0  ldloc.s  4
0x889e2  ldarg.0
0x889e3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x889e8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x889ed  br       loc_88B90
0x889f2  ldloc.3
0x889f3  ldstr    aSitemapid// "sitemapid"
0x889f8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x889fd  unbox.any [mscorlib]System.Guid
0x88a02  stloc.s  5
0x88a04  ldloc.3
0x88a05  ldstr    aSitemapxml// "sitemapxml"
0x88a0a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x88a0f  castclass [mscorlib]System.String
0x88a14  ldarg.s  4
0x88a16  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x88a1b  stloc.s  6
0x88a1d  ldloc.1
0x88a1e  brfalse.s loc_88A30
0x88a20  ldarg.s  5
0x88a22  ldarg.s  4
0x88a24  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x88a29  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::CalculateSiteMapInstallTimeXmlDiff(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, string)
0x88a2e  stloc.s  6
0x88a30  ldloc.s  6
0x88a32  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::MergeSiteMapXmlDiff(string, string)
0x88a37  stloc.0
0x88a38  ldarg.0
0x88a39  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88a3e  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88a43  stloc.s  7
0x88a45  ldloc.s  7
0x88a47  ldstr    aSitemapid// "sitemapid"
0x88a4c  ldloc.s  5
0x88a4e  box      [mscorlib]System.Guid
0x88a53  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88a58  ldstr    aSitemapname// "sitemapname"
0x88a5d  ldarg.0
0x88a5e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88a63  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88a68  brfalse.s loc_88A77
0x88a6a  ldloc.s  7
0x88a6c  ldstr    aSitemapname// "sitemapname"
0x88a71  ldarg.2
0x88a72  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88a77  ldloc.s  7
0x88a79  ldstr    aSitemapxml// "sitemapxml"
0x88a7e  ldloc.0
0x88a7f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88a84  ldloc.s  7
0x88a86  ldstr    aSitemapxmlmana// "sitemapxmlmanaged"
0x88a8b  ldloc.s  6
0x88a8d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88a92  ldstr    aIsappaware// "isappaware"
0x88a97  ldarg.0
0x88a98  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88a9d  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88aa2  brfalse.s loc_88AB9
0x88aa4  ldloc.s  7
0x88aa6  ldstr    aIsappaware// "isappaware"
0x88aab  ldarg.3
0x88aac  ldc.i4.0
0x88aad  ceq
0x88aaf  box      [mscorlib]System.Boolean
0x88ab4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88ab9  ldloc.2
0x88aba  ldloc.s  7
0x88abc  ldarg.0
0x88abd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88ac2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88ac7  br       loc_88B90
0x88acc  ldloc.1
0x88acd  brtrue.s loc_88ADA
0x88acf  ldstr    aFullSitemapxml_1// "full siteMapXml is expected to create a"...
0x88ad4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x88ad9  throw
0x88ada  ldarg.s  4
0x88adc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x88ae1  stloc.0
0x88ae2  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x88ae7  stloc.s  8
0x88ae9  ldarg.0
0x88aea  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88aef  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x88af4  stloc.s  9
0x88af6  ldstr    aSitemapnameuni// "sitemapnameunique"
0x88afb  ldarg.0
0x88afc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88b01  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88b06  brfalse.s loc_88B18
0x88b08  ldarg.3
0x88b09  brtrue.s loc_88B18
0x88b0b  ldloc.s  9
0x88b0d  ldstr    aSitemapnameuni// "sitemapnameunique"
0x88b12  ldarg.1
0x88b13  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88b18  ldstr    aSitemapname// "sitemapname"
0x88b1d  ldarg.0
0x88b1e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88b23  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88b28  brfalse.s loc_88B37
0x88b2a  ldloc.s  9
0x88b2c  ldstr    aSitemapname// "sitemapname"
0x88b31  ldarg.2
0x88b32  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88b37  ldloc.s  9
0x88b39  ldstr    aSitemapxml// "sitemapxml"
0x88b3e  ldloc.0
0x88b3f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88b44  ldstr    aIsappaware// "isappaware"
0x88b49  ldarg.0
0x88b4a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88b4f  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88b54  brfalse.s loc_88B6B
0x88b56  ldloc.s  9
0x88b58  ldstr    aIsappaware// "isappaware"
0x88b5d  ldarg.3
0x88b5e  ldc.i4.0
0x88b5f  ceq
0x88b61  box      [mscorlib]System.Boolean
0x88b66  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x88b6b  ldarg.3
0x88b6c  brfalse.s loc_88B80
0x88b6e  ldloc.s  8
0x88b70  ldloc.s  9
0x88b72  ldarg.0
0x88b73  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88b78  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88b7d  pop
0x88b7e  br.s     loc_88B90
0x88b80  ldloc.s  8
0x88b82  ldloc.s  9
0x88b84  ldarg.0
0x88b85  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88b8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::CreateAppSiteMap(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x88b8f  pop
0x88b90  ldloc.0
0x88b91  ret
```
