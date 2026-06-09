# Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::Install

- ea: `0x879f0`
- end: `0x87e98`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::Install`
- size: `1192`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xfc40`
- `0x60620`

## callees

- `0x359e0`
- `0x63db0`
- `0x63df0`
- `0x879f0`
- `0x87ea0`
- `0x87f00`
- `0x881a0`

## string_xrefs

- `0x87a72`: `sitemapxml`
- `0x87bb9`: `sitemapxml`
- `0x87d0d`: `sitemapxml`
- `0x87d6e`: `sitemapxml`
- `0x87aba`: `Sitemap : This is a fresh install.`
- `0x87b2d`: `Sitemap install XML : {0}`
- `0x87b74`: `Sitemap component states count : {0}`
- `0x87be1`: `Sitemap baseXML : {0}`
- `0x87c81`: `siteMap must exist after crm installation`
- `0x87cdb`: `unmanaged solution expects full siteMapXml`
- `0x87d3a`: `Sitemap : This is an app sitemap in unmanaged solution to be created.`
- `0x87df1`: `ImportExportXml/SolutionManifest/RootComponents/RootComponent[@type='{0}' and not(@id)]`

## pseudocode

```c

```

## disassembly

```asm
0x879f0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x879f5  stloc.0
0x879f6  ldc.i4.1
0x879f7  stloc.1
0x879f8  ldstr    aIsappaware// "isappaware"
0x879fd  ldarg.0
0x879fe  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87a03  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87a08  stloc.2
0x87a09  ldstr    aSitemapnameuni// "sitemapnameunique"
0x87a0e  ldarg.0
0x87a0f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87a14  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87a19  stloc.3
0x87a1a  ldstr    aSitemapname// "sitemapname"
0x87a1f  ldarg.0
0x87a20  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87a25  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::DoesAttributeExist(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87a2a  stloc.s  4
0x87a2c  ldarg.2
0x87a2d  brfalse.s loc_87A31
0x87a2f  ldc.i4.0
0x87a30  stloc.1
0x87a31  ldarg.2
0x87a32  ldarg.0
0x87a33  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87a38  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetSiteMapIdUsingUniqueName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87a3d  stloc.0
0x87a3e  ldloc.0
0x87a3f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87a44  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x87a49  brtrue.s loc_87A4E
0x87a4b  ldc.i4.1
0x87a4c  br.s     loc_87A4F
0x87a4e  ldc.i4.0
0x87a4f  stloc.s  5
0x87a51  ldarg.0
0x87a52  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_setup
0x87a57  brfalse  loc_87C36
0x87a5c  ldloc.s  5
0x87a5e  brtrue   loc_87AFE
0x87a63  ldarg.0
0x87a64  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87a69  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x87a6e  stloc.s  6
0x87a70  ldloc.s  6
0x87a72  ldstr    aSitemapxml// "sitemapxml"
0x87a77  ldarg.1
0x87a78  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87a7d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87a82  ldloc.2
0x87a83  brfalse.s loc_87A9A
0x87a85  ldloc.s  6
0x87a87  ldstr    aIsappaware// "isappaware"
0x87a8c  ldloc.1
0x87a8d  ldc.i4.0
0x87a8e  ceq
0x87a90  box      [mscorlib]System.Boolean
0x87a95  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87a9a  ldloc.3
0x87a9b  brfalse.s loc_87AAD
0x87a9d  ldarg.2
0x87a9e  brfalse.s loc_87AAD
0x87aa0  ldloc.s  6
0x87aa2  ldstr    aSitemapnameuni// "sitemapnameunique"
0x87aa7  ldarg.2
0x87aa8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87aad  ldarg.0
0x87aae  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87ab3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87ab8  ldc.i4.s 0x11
0x87aba  ldstr    aSitemapThisIsA// "Sitemap : This is a fresh install."
0x87abf  ldc.i4.0
0x87ac0  newarr   [mscorlib]System.Object
0x87ac5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87aca  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x87acf  stloc.s  7
0x87ad1  ldloc.1
0x87ad2  brfalse.s loc_87AE9
0x87ad4  ldloc.s  7
0x87ad6  ldloc.s  6
0x87ad8  ldarg.0
0x87ad9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87ade  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87ae3  pop
0x87ae4  br       loc_87E47
0x87ae9  ldloc.s  7
0x87aeb  ldloc.s  6
0x87aed  ldarg.0
0x87aee  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87af3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::CreateAppSiteMap(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87af8  pop
0x87af9  br       loc_87E47
0x87afe  ldarg.0
0x87aff  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87b04  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87b09  ldc.i4.s 0x11
0x87b0b  ldstr    aSitemapUpgrade// "Sitemap : Upgrade action begins."
0x87b10  ldc.i4.0
0x87b11  newarr   [mscorlib]System.Object
0x87b16  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87b1b  ldarg.0
0x87b1c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87b21  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87b26  ldc.i4.s 0x11
0x87b28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87b2d  ldstr    aSitemapInstall// "Sitemap install XML : {0}"
0x87b32  ldc.i4.1
0x87b33  newarr   [mscorlib]System.Object
0x87b38  dup
0x87b39  ldc.i4.0
0x87b3a  ldarg.1
0x87b3b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87b40  stelem.ref
0x87b41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87b46  ldc.i4.0
0x87b47  newarr   [mscorlib]System.Object
0x87b4c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87b51  ldnull
0x87b52  stloc.s  8
0x87b54  ldarg.2
0x87b55  ldarg.0
0x87b56  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87b5b  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::RetrieveComponentStatesUsingUniqueName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87b60  stloc.s  8
0x87b62  ldarg.0
0x87b63  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87b68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87b6d  ldc.i4.s 0x11
0x87b6f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87b74  ldstr    aSitemapCompone// "Sitemap component states count : {0}"
0x87b79  ldc.i4.1
0x87b7a  newarr   [mscorlib]System.Object
0x87b7f  dup
0x87b80  ldc.i4.0
0x87b81  ldloc.s  8
0x87b83  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x87b88  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x87b8d  box      [mscorlib]System.Int32
0x87b92  stelem.ref
0x87b93  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87b98  ldc.i4.0
0x87b99  newarr   [mscorlib]System.Object
0x87b9e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87ba3  ldloc.s  8
0x87ba5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BaseInstance()
0x87baa  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x87baf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x87bb4  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap
0x87bb9  ldstr    aSitemapxml// "sitemapxml"
0x87bbe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x87bc3  castclass [mscorlib]System.String
0x87bc8  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x87bcd  stloc.s  9
0x87bcf  ldarg.0
0x87bd0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87bd5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87bda  ldc.i4.s 0x11
0x87bdc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87be1  ldstr    aSitemapBasexml// "Sitemap baseXML : {0}"
0x87be6  ldc.i4.1
0x87be7  newarr   [mscorlib]System.Object
0x87bec  dup
0x87bed  ldc.i4.0
0x87bee  ldloc.s  9
0x87bf0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87bf5  stelem.ref
0x87bf6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87bfb  ldc.i4.0
0x87bfc  newarr   [mscorlib]System.Object
0x87c01  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87c06  ldarg.0
0x87c07  ldarg.1
0x87c08  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87c0d  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x87c12  ldloc.s  9
0x87c14  ldarg.0
0x87c15  ldloc.s  9
0x87c17  ldloc.s  8
0x87c19  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::IsCustomizationPresent(class [System.Xml]System.Xml.XmlDocument siteMapBaseNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x87c1e  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::PreProcessNewXml(class [System.Xml]System.Xml.XmlDocument siteMapNode, class [System.Xml]System.Xml.XmlDocument siteMapBaseNode, [opt] bool isCustomizationPresent)
0x87c23  starg.s  1
0x87c25  ldarg.0
0x87c26  ldarg.2
0x87c27  ldarg.3
0x87c28  ldloc.1
0x87c29  ldarg.1
0x87c2a  ldloc.s  8
0x87c2c  call     instance void Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::ImportManagedSiteMap(string sitemapUniqueNameParam, string siteMapNameParam, bool isDefaultSiteMap, class [System.Xml]System.Xml.XmlNode siteMapNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x87c31  br       loc_87E47
0x87c36  ldc.i4.s 0x3E
0x87c38  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x87c3d  ldarg.0
0x87c3e  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::importDocument
0x87c43  ldsfld   string [mscorlib]System.String::Empty
0x87c48  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87c4d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x87c52  ldarg.0
0x87c53  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87c58  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87c5d  ldnull
0x87c5e  stloc.s  0xA
0x87c60  ldarg.2
0x87c61  ldarg.0
0x87c62  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87c67  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::RetrieveComponentStatesUsingUniqueName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87c6c  stloc.s  0xA
0x87c6e  ldloc.1
0x87c6f  brfalse.s loc_87C9B
0x87c71  ldloc.s  0xA
0x87c73  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetLastManagedEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState)
0x87c78  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap
0x87c7d  dup
0x87c7e  ldnull
0x87c7f  cgt.un
0x87c81  ldstr    aSitemapMustExi// "siteMap must exist after crm installati"...
0x87c86  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x87c8b  ldstr    aSitemapid// "sitemapid"
0x87c90  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x87c95  unbox.any [mscorlib]System.Guid
0x87c9a  stloc.0
0x87c9b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x87ca0  ldarg.0
0x87ca1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87ca6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x87cab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x87cb0  ldarg.0
0x87cb1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87cb6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x87cbb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_IsProtected()
0x87cc0  brfalse.s loc_87CD3
0x87cc2  ldarg.0
0x87cc3  ldarg.2
0x87cc4  ldarg.3
0x87cc5  ldloc.1
0x87cc6  ldarg.1
0x87cc7  ldloc.s  0xA
0x87cc9  call     instance void Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::ImportManagedSiteMap(string sitemapUniqueNameParam, string siteMapNameParam, bool isDefaultSiteMap, class [System.Xml]System.Xml.XmlNode siteMapNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x87cce  br       loc_87DDB
0x87cd3  ldarg.1
0x87cd4  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::ImportingFullFormXml(class [System.Xml]System.Xml.XPath.IXPathNavigable)
0x87cd9  brtrue.s loc_87CE6
0x87cdb  ldstr    aUnmanagedSolut_1// "unmanaged solution expects full siteMap"...
0x87ce0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x87ce5  throw
0x87ce6  ldloc.1
0x87ce7  brtrue.s loc_87D5F
0x87ce9  ldloc.s  5
0x87ceb  brtrue.s loc_87D5F
0x87ced  ldarg.0
0x87cee  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87cf3  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x87cf8  stloc.s  0xD
0x87cfa  ldloc.s  4
0x87cfc  brfalse.s loc_87D0B
0x87cfe  ldloc.s  0xD
0x87d00  ldstr    aSitemapname// "sitemapname"
0x87d05  ldarg.3
0x87d06  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87d0b  ldloc.s  0xD
0x87d0d  ldstr    aSitemapxml// "sitemapxml"
0x87d12  ldarg.1
0x87d13  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87d18  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87d1d  ldloc.3
0x87d1e  brfalse.s loc_87D2D
0x87d20  ldloc.s  0xD
0x87d22  ldstr    aSitemapnameuni// "sitemapnameunique"
0x87d27  ldarg.2
0x87d28  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87d2d  ldarg.0
0x87d2e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87d33  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87d38  ldc.i4.s 0x11
0x87d3a  ldstr    aSitemapThisIsA_0// "Sitemap : This is an app sitemap in unm"...
0x87d3f  ldc.i4.0
0x87d40  newarr   [mscorlib]System.Object
0x87d45  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87d4a  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::.ctor()
0x87d4f  ldloc.s  0xD
0x87d51  ldarg.0
0x87d52  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87d57  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapService::CreateAppSiteMap(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x87d5c  pop
0x87d5d  br.s     loc_87DDB
0x87d5f  ldarg.0
0x87d60  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87d65  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x87d6a  stloc.s  0xE
0x87d6c  ldloc.s  0xE
0x87d6e  ldstr    aSitemapxml// "sitemapxml"
0x87d73  ldarg.1
0x87d74  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87d79  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87d7e  ldloc.s  0xE
0x87d80  ldstr    aSitemapid// "sitemapid"
0x87d85  ldloc.0
0x87d86  box      [mscorlib]System.Guid
0x87d8b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x87d90  ldloc.s  4
  ... truncated ...
```
