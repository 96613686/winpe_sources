# Microsoft.Crm.Web.Workplace.UIXmlDescriptionGenerator::GetFolderXml

- ea: `0x3a630`
- end: `0x3ad60`
- name: `Microsoft.Crm.Web.Workplace.UIXmlDescriptionGenerator::GetFolderXml`
- size: `1840`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3a3b0`

## callees

- `0x3a5b0`
- `0x3a630`
- `0x3ad60`
- `0x3aed0`
- `0x3af00`

## string_xrefs

- `0x3ac23`: `sitemappath`
- `0x3aa61`: `sitemappath=`
- `0x3ab57`: `sitemappath=`
- `0x3abde`: `sitemappath=`
- `0x3abc8`: `servicecalendar`

## pseudocode

```c

```

## disassembly

```asm
0x3a630  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3a635  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x3a63a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x3a63f  stloc.0
0x3a640  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.UserSiteMapCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.UserSiteMapCache::Instance()
0x3a645  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x3a64a  ldarg.2
0x3a64b  ldarg.3
0x3a64c  ldstr    asc_11EF2A// ""
0x3a651  ldnull
0x3a652  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.UserSiteMapCache::LookupEntry(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.Client, bool, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a657  stloc.1
0x3a658  ldarg.1
0x3a659  ldstr    aFolders// "Folders"
0x3a65e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3a663  ldloc.1
0x3a664  brfalse  loc_3AD59
0x3a669  ldarg.1
0x3a66a  ldstr    aFolder// "Folder"
0x3a66f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3a674  ldarg.1
0x3a675  ldstr    aUrl_0// "Url"
0x3a67a  ldloc.1
0x3a67b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::get_Url()
0x3a680  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x3a685  brtrue.s loc_3A699
0x3a687  ldloc.1
0x3a688  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::get_Url()
0x3a68d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetOrganizationNameSafeUriForIfdEnabled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3a692  callvirt instance string [mscorlib]System.Object::ToString()
0x3a697  br.s     loc_3A69E
0x3a699  ldstr    aSitemapnavpage// "SiteMapNavPage.aspx"
0x3a69e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a6a3  ldarg.1
0x3a6a4  ldstr    aId_0// "Id"
0x3a6a9  ldstr    aRoot_1// "root"
0x3a6ae  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a6b3  ldloc.1
0x3a6b4  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapAreaCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMap::get_Areas()
0x3a6b9  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3a6be  stloc.2
0x3a6bf  br       loc_3AD32
0x3a6c4  ldloc.2
0x3a6c5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3a6ca  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea
0x3a6cf  stloc.3
0x3a6d0  ldarg.1
0x3a6d1  ldstr    aFolder// "Folder"
0x3a6d6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3a6db  ldarg.1
0x3a6dc  ldstr    aId_0// "Id"
0x3a6e1  ldloc.3
0x3a6e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Id()
0x3a6e7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a6ec  ldarg.1
0x3a6ed  ldstr    aName_0// "Name"
0x3a6f2  ldloc.3
0x3a6f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0x3a6f8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a6fd  ldarg.1
0x3a6fe  ldstr    aUrl_0// "Url"
0x3a703  ldloc.3
0x3a704  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Url()
0x3a709  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x3a70e  brtrue.s loc_3A722
0x3a710  ldloc.3
0x3a711  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Url()
0x3a716  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetOrganizationNameSafeUriForIfdEnabled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3a71b  callvirt instance string [mscorlib]System.Object::ToString()
0x3a720  br.s     loc_3A732
0x3a722  ldloc.3
0x3a723  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Id()
0x3a728  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Web.Workplace.UIXmlDescriptionGenerator::GetAreaFolderUrl(string areaId)
0x3a72d  callvirt instance string [mscorlib]System.Object::ToString()
0x3a732  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a737  ldarg.1
0x3a738  ldstr    aIcon_0// "Icon"
0x3a73d  ldloc.3
0x3a73e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Icon()
0x3a743  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetOrganizationNameSafeUriForIfdEnabled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3a748  callvirt instance string [mscorlib]System.Object::ToString()
0x3a74d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a752  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x3a757  stloc.s  4
0x3a759  ldloc.3
0x3a75a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroupCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Groups()
0x3a75f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3a764  stloc.s  5
0x3a766  br       loc_3AD09
0x3a76b  ldloc.s  5
0x3a76d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3a772  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup
0x3a777  stloc.s  6
0x3a779  ldloc.3
0x3a77a  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_ShowGroups()
0x3a77f  brfalse  loc_3A819
0x3a784  ldarg.1
0x3a785  ldstr    aFolder// "Folder"
0x3a78a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3a78f  ldarg.1
0x3a790  ldstr    aId_0// "Id"
0x3a795  ldloc.s  6
0x3a797  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0x3a79c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a7a1  ldarg.1
0x3a7a2  ldstr    aName_0// "Name"
0x3a7a7  ldloc.s  6
0x3a7a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0x3a7ae  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a7b3  ldarg.1
0x3a7b4  ldstr    aUrl_0// "Url"
0x3a7b9  ldloc.s  6
0x3a7bb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Url()
0x3a7c0  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x3a7c5  brtrue.s loc_3A7DA
0x3a7c7  ldloc.s  6
0x3a7c9  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Url()
0x3a7ce  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetOrganizationNameSafeUriForIfdEnabled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3a7d3  callvirt instance string [mscorlib]System.Object::ToString()
0x3a7d8  br.s     loc_3A7F1
0x3a7da  ldloc.3
0x3a7db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Id()
0x3a7e0  ldloc.s  6
0x3a7e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0x3a7e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Web.Workplace.UIXmlDescriptionGenerator::GetGroupFolderUrl(string areaId, string groupId)
0x3a7ec  callvirt instance string [mscorlib]System.Object::ToString()
0x3a7f1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a7f6  ldarg.1
0x3a7f7  ldstr    aIcon_0// "Icon"
0x3a7fc  ldloc.s  6
0x3a7fe  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Icon()
0x3a803  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetOrganizationNameSafeUriForIfdEnabled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3a808  callvirt instance string [mscorlib]System.Object::ToString()
0x3a80d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a812  ldloc.s  4
0x3a814  callvirt instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::Clear()
0x3a819  ldloc.s  6
0x3a81b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubAreaCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_SubAreas()
0x3a820  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x3a825  stloc.s  7
0x3a827  br       loc_3ACD8
0x3a82c  ldloc.s  7
0x3a82e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3a833  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea
0x3a838  stloc.s  8
0x3a83a  ldloc.s  8
0x3a83c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0x3a841  stloc.s  9
0x3a843  ldc.i4.1
0x3a844  stloc.s  0xA
0x3a846  br.s     loc_3A862
0x3a848  ldloc.s  9
0x3a84a  ldstr    asc_12B0EE// "_"
0x3a84f  ldloc.s  0xA
0x3a851  dup
0x3a852  ldc.i4.1
0x3a853  add
0x3a854  stloc.s  0xA
0x3a856  box      [mscorlib]System.Int32
0x3a85b  call     string [mscorlib]System.String::Concat(object, object, object)
0x3a860  stloc.s  9
0x3a862  ldloc.s  4
0x3a864  ldloc.s  9
0x3a866  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x3a86b  brtrue.s loc_3A848
0x3a86d  ldloc.s  4
0x3a86f  ldloc.s  9
0x3a871  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x3a876  pop
0x3a877  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_IsV4CrmOutlookClient()
0x3a87c  brfalse.s loc_3A894
0x3a87e  ldloc.s  8
0x3a880  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0x3a885  ldstr    aNavPersonalwal// "nav_personalwall"
0x3a88a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3a88f  brtrue   loc_3ACD8
0x3a894  ldloc.s  6
0x3a896  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0x3a89b  ldstr    aSystemSetting// "System_Setting"
0x3a8a0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3a8a5  brfalse.s loc_3A8C4
0x3a8a7  ldloc.s  8
0x3a8a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Id()
0x3a8ae  ldstr    aCrmappOutlook// "crmapp_outlook"
0x3a8b3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3a8b8  brfalse.s loc_3A8C4
0x3a8ba  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsAppsForCrmSiteMapAllowed()
0x3a8bf  brfalse  loc_3ACD8
0x3a8c4  ldarg.1
0x3a8c5  ldstr    aFolder// "Folder"
0x3a8ca  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x3a8cf  ldarg.1
0x3a8d0  ldstr    aId_0// "Id"
0x3a8d5  ldloc.s  9
0x3a8d7  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a8dc  ldarg.1
0x3a8dd  ldstr    aName_0// "Name"
0x3a8e2  ldloc.s  8
0x3a8e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapTitlesAndDescriptionsHelper::get_Title()
0x3a8e9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a8ee  ldarg.1
0x3a8ef  ldstr    aIcon_0// "Icon"
0x3a8f4  ldloc.s  8
0x3a8f6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Icon()
0x3a8fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetOrganizationNameSafeUriForIfdEnabled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3a900  callvirt instance string [mscorlib]System.Object::ToString()
0x3a905  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x3a90a  ldloc.s  8
0x3a90c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_PassParameters()
0x3a911  brtrue.s loc_3A926
0x3a913  ldloc.s  8
0x3a915  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Url()
0x3a91a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Clone()
0x3a91f  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri
0x3a924  br.s     loc_3A933
0x3a926  ldarg.0
0x3a927  ldloc.s  8
0x3a929  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapSubArea::get_Url()
0x3a92e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Web.Workplace.UIXmlDescriptionGenerator::AddParametersToUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri url)
0x3a933  stloc.s  0xB
0x3a935  ldloc.s  0xB
0x3a937  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::SetOrganizationNameSafeUriForIfdEnabled(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x3a93c  stloc.s  0xB
0x3a93e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a943  ldstr    a012_0// "{0}|{1}|{2}"
0x3a948  ldc.i4.3
0x3a949  newarr   [mscorlib]System.Object
0x3a94e  dup
0x3a94f  ldc.i4.0
0x3a950  ldloc.3
0x3a951  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapArea::get_Id()
0x3a956  stelem.ref
0x3a957  dup
0x3a958  ldc.i4.1
0x3a959  ldloc.s  6
0x3a95b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.SiteMapGroup::get_Id()
0x3a960  stelem.ref
0x3a961  dup
0x3a962  ldc.i4.2
0x3a963  ldloc.s  9
0x3a965  stelem.ref
0x3a966  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a96b  stloc.s  0xC
0x3a96d  ldloc.s  0xB
0x3a96f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x3a974  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x3a979  ldstr    aRootHomepageAs_0// "/_ROOT/HOMEPAGE.ASPX"
0x3a97e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3a983  brfalse  loc_3AB11
0x3a988  ldloc.s  0xB
0x3a98a  ldstr    aMainAspx_0// "/main.aspx"
0x3a98f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Path(string)
0x3a994  ldloc.s  0xB
0x3a996  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x3a99b  ldstr    aPagetype// "pagetype"
0x3a9a0  ldstr    aEntitylist// "entitylist"
0x3a9a5  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3a9aa  ldnull
0x3a9ab  stloc.s  0xD
0x3a9ad  ldloc.s  0xB
0x3a9af  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x3a9b4  ldstr    aEtc// "etc"
0x3a9b9  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x3a9be  brfalse.s loc_3A9F8
0x3a9c0  ldloc.s  0xB
0x3a9c2  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x3a9c7  ldstr    aEtc// "etc"
0x3a9cc  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x3a9d1  stloc.s  0xF
0x3a9d3  ldloc.s  0xF
0x3a9d5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3a9da  brtrue.s loc_3AA37
0x3a9dc  ldloc.s  0xF
0x3a9de  ldloca.s 0x10
0x3a9e0  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x3a9e5  brfalse.s loc_3AA37
0x3a9e7  ldloc.0
0x3a9e8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3a9ed  ldloc.s  0x10
0x3a9ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x3a9f4  stloc.s  0xD
0x3a9f6  br.s     loc_3AA37
0x3a9f8  ldloc.s  0xB
0x3a9fa  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x3a9ff  ldstr    aEtn// "etn"
0x3aa04  callvirt instance bool class [System]System.Collections.Generic.SortedDictionary`2<string, string>::ContainsKey(var<u1>)
0x3aa09  brfalse.s loc_3AA37
0x3aa0b  ldloc.s  0xB
0x3aa0d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x3aa12  ldstr    aEtn// "etn"
0x3aa17  callvirt instance var<u1> class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Item(void)
0x3aa1c  stloc.s  0x11
0x3aa1e  ldloc.s  0x11
0x3aa20  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3aa25  brtrue.s loc_3AA37
0x3aa27  ldloc.0
0x3aa28  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3aa2d  ldloc.s  0x11
0x3aa2f  ldc.i4.1
0x3aa30  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
  ... truncated ...
```
