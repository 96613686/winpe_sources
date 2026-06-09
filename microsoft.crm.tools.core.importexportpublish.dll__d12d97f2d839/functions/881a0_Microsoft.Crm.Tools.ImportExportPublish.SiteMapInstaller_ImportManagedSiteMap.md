# Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::ImportManagedSiteMap

- ea: `0x881a0`
- end: `0x885fb`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::ImportManagedSiteMap`
- size: `1115`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x879f0`

## callees

- `0x880a0`
- `0x881a0`
- `0x88600`
- `0x888d0`

## string_xrefs

- `0x88594`: `sitemapxml`
- `0x881d6`: `Sitemap published XML diff : {0}`
- `0x8828d`: `Sitemap updated current XML diff : {0}`
- `0x884e2`: `Sitemap updated current XML : {0}`
- `0x88587`: `sitemapxmlmanaged`

## pseudocode

```c

```

## disassembly

```asm
0x881a0  ldarg.3
0x881a1  brfalse.s loc_881AF
0x881a3  ldarg.s  5
0x881a5  ldstr    aStates// "states"
0x881aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x881af  ldarg.s  4
0x881b1  ldstr    aSitemapnode// "siteMapNode"
0x881b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x881bb  ldarg.s  5
0x881bd  ldc.i4.0
0x881be  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::CalculateSiteMapPublishedCustomizationXmlDiff(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, bool)
0x881c3  stloc.0
0x881c4  ldarg.0
0x881c5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x881ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x881cf  ldc.i4.s 0x11
0x881d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x881d6  ldstr    aSitemapPublish// "Sitemap published XML diff : {0}"
0x881db  ldc.i4.1
0x881dc  newarr   [mscorlib]System.Object
0x881e1  dup
0x881e2  ldc.i4.0
0x881e3  ldloc.0
0x881e4  stelem.ref
0x881e5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x881ea  ldc.i4.0
0x881eb  newarr   [mscorlib]System.Object
0x881f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x881f5  ldarg.s  5
0x881f7  ldarg.0
0x881f8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x881fd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x88202  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x88207  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::IsExistingSolution(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, valuetype [mscorlib]System.Guid)
0x8820c  stloc.1
0x8820d  ldnull
0x8820e  stloc.2
0x8820f  ldarg.0
0x88210  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88215  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8821a  ldc.i4.s 0x11
0x8821c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x88221  ldstr    aSitemapIsExist// "Sitemap: Is existing solution : {0}"
0x88226  ldc.i4.1
0x88227  newarr   [mscorlib]System.Object
0x8822c  dup
0x8822d  ldc.i4.0
0x8822e  ldloc.1
0x8822f  box      [mscorlib]System.Boolean
0x88234  stelem.ref
0x88235  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8823a  ldc.i4.0
0x8823b  newarr   [mscorlib]System.Object
0x88240  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x88245  ldloc.1
0x88246  brfalse.s loc_88258
0x88248  ldarg.0
0x88249  ldarg.3
0x8824a  ldarg.s  4
0x8824c  ldarg.s  5
0x8824e  ldarg.1
0x8824f  ldarg.2
0x88250  call     instance string Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::UpdateSolutionStack(bool isDefaultSiteMap, class [System.Xml]System.Xml.XmlNode siteMapNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states, string siteMapUniqueName, string siteMapNameParam)
0x88255  stloc.2
0x88256  br.s     loc_88266
0x88258  ldarg.0
0x88259  ldarg.1
0x8825a  ldarg.2
0x8825b  ldarg.3
0x8825c  ldarg.s  4
0x8825e  ldarg.s  5
0x88260  call     instance string Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::ImportNewManagedSiteMap(string siteMapUniqueNameParam, string siteMapNameParam, bool isDefaultSiteMap, class [System.Xml]System.Xml.XmlNode siteMapNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState states)
0x88265  stloc.2
0x88266  ldloc.0
0x88267  brfalse  loc_885FA
0x8826c  ldarg.0
0x8826d  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_setup
0x88272  brfalse.s loc_882AC
0x88274  ldloc.0
0x88275  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::UpdateCustomizedXMLDiffWithURL(string)
0x8827a  stloc.0
0x8827b  ldarg.0
0x8827c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88281  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x88286  ldc.i4.s 0x11
0x88288  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8828d  ldstr    aSitemapUpdated_1// "Sitemap updated current XML diff : {0}"
0x88292  ldc.i4.1
0x88293  newarr   [mscorlib]System.Object
0x88298  dup
0x88299  ldc.i4.0
0x8829a  ldloc.0
0x8829b  stelem.ref
0x8829c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x882a1  ldc.i4.0
0x882a2  newarr   [mscorlib]System.Object
0x882a7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x882ac  ldloc.2
0x882ad  ldloc.0
0x882ae  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::MergeSiteMapXmlDiff(string, string)
0x882b3  stloc.3
0x882b4  ldarg.0
0x882b5  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_setup
0x882ba  brfalse  loc_884D0
0x882bf  ldloc.3
0x882c0  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x882c5  stloc.s  4
0x882c7  ldloc.s  4
0x882c9  brfalse  loc_884D0
0x882ce  ldloc.s  4
0x882d0  stloc.s  5
0x882d2  ldloc.s  5
0x882d4  brfalse  loc_884C8
0x882d9  ldloc.s  5
0x882db  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x882e0  stloc.s  6
0x882e2  ldloc.s  6
0x882e4  brfalse  loc_884C8
0x882e9  ldloc.s  6
0x882eb  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x882f0  brfalse  loc_884C8
0x882f5  ldloc.s  6
0x882f7  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x882fc  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x88301  stloc.s  7
0x88303  br       loc_884A5
0x88308  ldloc.s  7
0x8830a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8830f  castclass [System.Xml]System.Xml.XmlNode
0x88314  stloc.s  8
0x88316  ldloc.s  8
0x88318  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x8831d  ldc.i4.1
0x8831e  bne.un   loc_884A5
0x88323  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::.ctor()
0x88328  stloc.s  9
0x8832a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::.ctor()
0x8832f  stloc.s  0xA
0x88331  ldloc.s  8
0x88333  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x88338  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8833d  stloc.s  0xB
0x8833f  br       loc_8844B
0x88344  ldloc.s  0xB
0x88346  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8834b  castclass [System.Xml]System.Xml.XmlNode
0x88350  stloc.s  0xC
0x88352  ldloc.s  0xC
0x88354  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x88359  ldc.i4.1
0x8835a  bne.un   loc_8844B
0x8835f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::.ctor()
0x88364  stloc.s  0xD
0x88366  ldloc.s  0xC
0x88368  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8836d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x88372  stloc.s  0xE
0x88374  br.s     loc_883DD
0x88376  ldloc.s  0xE
0x88378  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8837d  castclass [System.Xml]System.Xml.XmlNode
0x88382  stloc.s  0xF
0x88384  ldloc.s  0xF
0x88386  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x8838b  ldc.i4.1
0x8838c  bne.un.s loc_883DD
0x8838e  ldloc.s  0xF
0x88390  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x88395  stloc.s  0x10
0x88397  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::IntroducedVersionRegex
0x8839c  ldloc.s  0x10
0x8839e  ldstr    asc_9A18C// ""
0x883a3  callvirt instance string [System]System.Text.RegularExpressions.Regex::Replace(string, string)
0x883a8  stloc.s  0x11
0x883aa  ldarg.0
0x883ab  ldloc.s  9
0x883ad  ldloc.s  0x11
0x883af  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::IsSubAreaAlreadyAvailableInThisArea(class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode> list, string outerXml_modified)
0x883b4  brfalse.s loc_883CF
0x883b6  ldloc.s  0x10
0x883b8  ldstr    aIntroducedvers_1// "IntroducedVersion=\"7.0.0.0\""
0x883bd  callvirt instance bool [mscorlib]System.String::Contains(string)
0x883c2  brfalse.s loc_883DD
0x883c4  ldloc.s  0xD
0x883c6  ldloc.s  0xF
0x883c8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::Add(var<u1>)
0x883cd  br.s     loc_883DD
0x883cf  ldloc.s  9
0x883d1  ldloc.s  0x11
0x883d3  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x883d8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::Add(var<u1>)
0x883dd  ldloc.s  0xE
0x883df  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x883e4  brtrue.s loc_88376
0x883e6  leave.s  loc_883FD
0x883e8  ldloc.s  0xE
0x883ea  isinst   [mscorlib]System.IDisposable
0x883ef  stloc.s  0x12
0x883f1  ldloc.s  0x12
0x883f3  brfalse.s loc_883FC
0x883f5  ldloc.s  0x12
0x883f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x883fc  endfinally
0x883fd  ldloc.s  0xD
0x883ff  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::GetEnumerator()
0x88404  stloc.s  0x13
0x88406  br.s     loc_8841B
0x88408  ldloca.s 0x13
0x8840a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Xml]System.Xml.XmlNode>::get_Current()
0x8840f  stloc.s  0x14
0x88411  ldloc.s  0xC
0x88413  ldloc.s  0x14
0x88415  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x8841a  pop
0x8841b  ldloca.s 0x13
0x8841d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Xml]System.Xml.XmlNode>::MoveNext()
0x88422  brtrue.s loc_88408
0x88424  leave.s  loc_88434
0x88426  ldloca.s 0x13
0x88428  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Xml]System.Xml.XmlNode>
0x8842e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x88433  endfinally
0x88434  ldloc.s  0xC
0x88436  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8843b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x88440  brtrue.s loc_8844B
0x88442  ldloc.s  0xA
0x88444  ldloc.s  0xC
0x88446  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::Add(var<u1>)
0x8844b  ldloc.s  0xB
0x8844d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x88452  brtrue   loc_88344
0x88457  leave.s  loc_8846E
0x88459  ldloc.s  0xB
0x8845b  isinst   [mscorlib]System.IDisposable
0x88460  stloc.s  0x12
0x88462  ldloc.s  0x12
0x88464  brfalse.s loc_8846D
0x88466  ldloc.s  0x12
0x88468  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8846d  endfinally
0x8846e  ldloc.s  0xA
0x88470  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.Xml]System.Xml.XmlNode>::GetEnumerator()
0x88475  stloc.s  0x13
0x88477  br.s     loc_8848C
0x88479  ldloca.s 0x13
0x8847b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Xml]System.Xml.XmlNode>::get_Current()
0x88480  stloc.s  0x15
0x88482  ldloc.s  8
0x88484  ldloc.s  0x15
0x88486  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x8848b  pop
0x8848c  ldloca.s 0x13
0x8848e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Xml]System.Xml.XmlNode>::MoveNext()
0x88493  brtrue.s loc_88479
0x88495  leave.s  loc_884A5
0x88497  ldloca.s 0x13
0x88499  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [System.Xml]System.Xml.XmlNode>
0x8849f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x884a4  endfinally
0x884a5  ldloc.s  7
0x884a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x884ac  brtrue   loc_88308
0x884b1  leave.s  loc_884C8
0x884b3  ldloc.s  7
0x884b5  isinst   [mscorlib]System.IDisposable
0x884ba  stloc.s  0x12
0x884bc  ldloc.s  0x12
0x884be  brfalse.s loc_884C7
0x884c0  ldloc.s  0x12
0x884c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x884c7  endfinally
0x884c8  ldloc.s  4
0x884ca  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x884cf  stloc.3
0x884d0  ldarg.0
0x884d1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x884d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x884db  ldc.i4.s 0x11
0x884dd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x884e2  ldstr    aSitemapUpdated_2// "Sitemap updated current XML : {0}"
0x884e7  ldc.i4.1
0x884e8  newarr   [mscorlib]System.Object
0x884ed  dup
0x884ee  ldc.i4.0
0x884ef  ldloc.3
0x884f0  stelem.ref
0x884f1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x884f6  ldc.i4.0
0x884f7  newarr   [mscorlib]System.Object
0x884fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x88501  ldarg.0
0x88502  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88507  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSetSolutionToDefaultModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8850c  stloc.s  0x16
0x8850e  ldarg.s  5
0x88510  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetLastManagedEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState)
0x88515  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SiteMap
0x8851a  stloc.s  0x17
0x8851c  ldloc.s  0x17
  ... truncated ...
```
