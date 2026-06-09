# Microsoft.Crm.Application.CrmCustomization::CustomizeSiteMap

- ea: `0x26310`
- end: `0x264ac`
- name: `Microsoft.Crm.Application.CrmCustomization::CustomizeSiteMap`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x218f0`

## callees

- `0x82d0`
- `0xe910`
- `0x227e0`
- `0x25830`
- `0x25de0`
- `0x26010`
- `0x26310`
- `0x264e0`
- `0x26570`
- `0x265d0`
- `0x39f70`
- `0x470b0`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x26348`: `configuration/Root/Areas/`
- `0x26467`: `A site map sub area with title {0} already exists, it will not be added.  The site map sub areas must have unique titles under a single group.\nDuplicate site map sub area XML : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x26310  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ISVExtensions()
0x26315  ldarg.2
0x26316  call     bool Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition pd, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x2631b  brfalse  loc_264AB
0x26320  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x26325  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x2632a  ldstr    a0// "{0}"
0x2632f  ldc.i4.1
0x26330  newarr   [mscorlib]System.Object
0x26335  dup
0x26336  ldc.i4.0
0x26337  ldstr    aLoadingSiteMap_0// "Loading site map customizations."
0x2633c  stelem.ref
0x2633d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26342  ldarg.2
0x26343  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Application.CrmCustomization::IsvXmlInternal(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x26348  ldstr    aConfigurationR// "configuration/Root/Areas/"
0x2634d  ldarg.0
0x2634e  ldstr    aNavbaritem// "/NavBarItem"
0x26353  call     string [mscorlib]System.String::Concat(string, string, string)
0x26358  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2635d  stloc.0
0x2635e  ldloc.0
0x2635f  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x26364  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0x26369  stloc.1
0x2636a  ldloc.0
0x2636b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x26370  stloc.2
0x26371  br       loc_26480
0x26376  ldloc.2
0x26377  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2637c  castclass [System.Xml]System.Xml.XmlNode
0x26381  stloc.3
0x26382  call     valuetype Microsoft.Crm.Application.Types.Client Microsoft.Crm.Application.Utility.Util::GetCurrentClient()
0x26387  ldloc.3
0x26388  call     bool Microsoft.Crm.Application.CrmCustomization::ItemIsValidForClient(valuetype Microsoft.Crm.Application.Types.Client client, class [System.Xml]System.Xml.XmlNode item)
0x2638d  brfalse  loc_26480
0x26392  ldloc.3
0x26393  call     string Microsoft.Crm.Application.CrmCustomization::GetLocalizedValue(class [System.Xml]System.Xml.XmlNode parentNode)
0x26398  stloc.s  4
0x2639a  ldloc.3
0x2639b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x263a0  ldstr    aUrl// "Url"
0x263a5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x263aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x263af  ldarg.2
0x263b0  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x263b5  stloc.s  5
0x263b7  ldloc.3
0x263b8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x263bd  ldstr    aIcon_0// "Icon"
0x263c2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x263c7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x263cc  ldarg.2
0x263cd  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x263d2  stloc.s  6
0x263d4  ldloc.3
0x263d5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x263da  ldstr    aVectoricon// "VectorIcon"
0x263df  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x263e4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x263e9  ldarg.2
0x263ea  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string path, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x263ef  stloc.s  7
0x263f1  ldloc.3
0x263f2  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x263f7  ldstr    aId_0// "Id"
0x263fc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x26401  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x26406  stloc.s  8
0x26408  ldloc.3
0x26409  ldstr    aPassparams// "PassParams"
0x2640e  ldc.i4.0
0x2640f  call     bool Microsoft.Crm.XmlUtil::GetBooleanAttribute(class [System.Xml]System.Xml.XmlNode node, string attributeName, bool defaultValue)
0x26414  stloc.s  9
0x26416  ldloc.1
0x26417  ldloc.s  4
0x26419  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x2641e  brtrue.s loc_2645C
0x26420  ldarg.1
0x26421  ldloc.s  8
0x26423  ldloc.s  4
0x26425  ldloc.s  6
0x26427  ldloc.s  7
0x26429  ldnull
0x2642a  ldloc.s  5
0x2642c  ldnull
0x2642d  ldloc.s  9
0x2642f  ldnull
0x26430  ldnull
0x26431  ldnull
0x26432  ldnull
0x26433  ldc.i4.0
0x26434  newobj   instance void Microsoft.Crm.Application.MasterSiteMapSubArea::.ctor(class Microsoft.Crm.Application.SiteMapGroup parentGroup, string id, string title, class Microsoft.Crm.Application.Utility.CrmUri icon, class Microsoft.Crm.Application.Utility.CrmUri vectorIcon, class Microsoft.Crm.Application.Utility.CrmUri outlookIcon, class Microsoft.Crm.Application.Utility.CrmUri url, string dynamicPage, bool passParameters, string getStartedPanePath, string getStartedPanePathOutlook, string getStartedPanePathAdmin, string getStartedPanePathAdminOutlook, bool availableOffline)
0x26439  stloc.s  0xA
0x2643b  ldloc.s  0xA
0x2643d  ldc.i4.1
0x2643e  callvirt instance void Microsoft.Crm.Application.MasterSiteMapSubArea::set_Client(valuetype Microsoft.Crm.Application.Types.Client value)
0x26443  ldarg.1
0x26444  callvirt instance class Microsoft.Crm.Application.SiteMapSubAreaCollection Microsoft.Crm.Application.SiteMapGroup::get_SubAreas()
0x26449  ldloc.s  0xA
0x2644b  callvirt instance int32 Microsoft.Crm.Application.SiteMapSubAreaCollection::Add(class Microsoft.Crm.Application.SiteMapSubArea value)
0x26450  pop
0x26451  ldloc.1
0x26452  ldloc.s  4
0x26454  ldnull
0x26455  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x2645a  br.s     loc_26480
0x2645c  ldnull
0x2645d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x26462  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x26467  ldstr    aASiteMapSubAre// "A site map sub area with title {0} alre"...
0x2646c  ldc.i4.2
0x2646d  newarr   [mscorlib]System.Object
0x26472  dup
0x26473  ldc.i4.0
0x26474  ldloc.s  4
0x26476  stelem.ref
0x26477  dup
0x26478  ldc.i4.1
0x26479  ldloc.3
0x2647a  stelem.ref
0x2647b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26480  ldloc.2
0x26481  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x26486  brtrue   loc_26376
0x2648b  leave.s  loc_264AB
0x2648d  ldloc.2
0x2648e  isinst   [mscorlib]System.IDisposable
0x26493  stloc.s  0xB
0x26495  ldloc.s  0xB
0x26497  brfalse.s loc_264A0
0x26499  ldloc.s  0xB
0x2649b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x264a0  endfinally
0x264a1  ldloc.0
0x264a2  brfalse.s loc_264AA
0x264a4  ldloc.0
0x264a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x264aa  endfinally
0x264ab  ret
```
