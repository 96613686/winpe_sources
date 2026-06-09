# Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::PreProcessNewXml

- ea: `0x87f00`
- end: `0x8809a`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::PreProcessNewXml`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x879f0`

## callees

- `0x87f00`

## string_xrefs

- `0x87f44`: `Sitemap installTimeDiff : {0}`
- `0x87ff7`: `Sitemap updated InstallTimeDiff : {0}`
- `0x88072`: `Sitemap updated install XML : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x87f00  ldc.i4.m1
0x87f01  stloc.0
0x87f02  ldarg.1
0x87f03  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::RemoveIntroducedVersion(class [System.Xml]System.Xml.XmlDocument)
0x87f08  stloc.1
0x87f09  ldarg.2
0x87f0a  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::RemoveIntroducedVersion(class [System.Xml]System.Xml.XmlDocument)
0x87f0f  castclass [System.Xml]System.Xml.XmlDocument
0x87f14  stloc.2
0x87f15  ldloc.2
0x87f16  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87f1b  ldloc.1
0x87f1c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87f21  ldc.i4.0
0x87f22  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::CalculateSiteMapXmlDiff(string, string, bool)
0x87f27  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x87f2c  stloc.3
0x87f2d  ldloc.3
0x87f2e  brtrue.s loc_87F32
0x87f30  ldarg.2
0x87f31  ret
0x87f32  ldarg.0
0x87f33  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87f38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87f3d  ldc.i4.s 0x11
0x87f3f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87f44  ldstr    aSitemapInstall_0// "Sitemap installTimeDiff : {0}"
0x87f49  ldc.i4.1
0x87f4a  newarr   [mscorlib]System.Object
0x87f4f  dup
0x87f50  ldc.i4.0
0x87f51  ldloc.3
0x87f52  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87f57  stelem.ref
0x87f58  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x87f5d  ldc.i4.0
0x87f5e  newarr   [mscorlib]System.Object
0x87f63  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x87f68  ldnull
0x87f69  stloc.s  4
0x87f6b  ldarg.2
0x87f6c  ldc.i4.1
0x87f6d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::CloneNode(bool)
0x87f72  castclass [System.Xml]System.Xml.XmlDocument
0x87f77  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x87f7c  ldstr    a6000// "6.0.0.0"
0x87f81  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::AddIntroducedVersion(class [System.Xml]System.Xml.XmlNode, string)
0x87f86  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x87f8b  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x87f90  stloc.2
0x87f91  ldarg.3
0x87f92  brfalse.s loc_87FC7
0x87f94  ldloc.2
0x87f95  ldc.i4.0
0x87f96  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.XmlDiffUtility::PreprocessSiteMap(class [System.Xml]System.Xml.XPath.IXPathNavigable, bool)
0x87f9b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x87fa0  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::set_ModifiedURLs(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x87fa5  ldloc.2
0x87fa6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87fab  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x87fb0  ldloc.3
0x87fb1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x87fb6  ldstr    asc_9A18C// ""
0x87fbb  ldarg.1
0x87fbc  ldloca.s 0
0x87fbe  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::UpdateInstallTimeDiff(class [System.Xml]System.Xml.XmlDocument, class [System.Xml]System.Xml.XmlNode, string, class [System.Xml]System.Xml.XmlNode, int32&)
0x87fc3  stloc.s  4
0x87fc5  br.s     loc_87FE5
0x87fc7  ldloc.2
0x87fc8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x87fcd  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x87fd2  ldloc.3
0x87fd3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x87fd8  ldstr    asc_9A18C// ""
0x87fdd  ldarg.1
0x87fde  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::UpdateInstallTimeDiff(class [System.Xml]System.Xml.XmlDocument, class [System.Xml]System.Xml.XmlNode, string, class [System.Xml]System.Xml.XmlNode)
0x87fe3  stloc.s  4
0x87fe5  ldarg.0
0x87fe6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x87feb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x87ff0  ldc.i4.s 0x11
0x87ff2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x87ff7  ldstr    aSitemapUpdated// "Sitemap updated InstallTimeDiff : {0}"
0x87ffc  ldc.i4.1
0x87ffd  newarr   [mscorlib]System.Object
0x88002  dup
0x88003  ldc.i4.0
0x88004  ldloc.s  4
0x88006  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8800b  stelem.ref
0x8800c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x88011  ldc.i4.0
0x88012  newarr   [mscorlib]System.Object
0x88017  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8801c  ldarg.2
0x8801d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x88022  ldstr    a6000// "6.0.0.0"
0x88027  call     class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::AddIntroducedVersion(class [System.Xml]System.Xml.XmlNode, string)
0x8802c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x88031  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x88036  starg.s  2
0x88038  ldarg.2
0x88039  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8803e  ldstr    aSitemap_1// "<SiteMap>"
0x88043  ldloc.s  4
0x88045  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8804a  ldstr    aSitemap_2// "</SiteMap > "
0x8804f  call     string [mscorlib]System.String::Concat(string, string, string)
0x88054  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::MergeSiteMapXmlDiff(string, string)
0x88059  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x8805e  stloc.s  5
0x88060  ldarg.0
0x88061  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SiteMapInstaller::_context
0x88066  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8806b  ldc.i4.s 0x11
0x8806d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x88072  ldstr    aSitemapUpdated_0// "Sitemap updated install XML : {0}"
0x88077  ldc.i4.1
0x88078  newarr   [mscorlib]System.Object
0x8807d  dup
0x8807e  ldc.i4.0
0x8807f  ldloc.s  5
0x88081  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x88086  stelem.ref
0x88087  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8808c  ldc.i4.0
0x8808d  newarr   [mscorlib]System.Object
0x88092  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x88097  ldloc.s  5
0x88099  ret
```
