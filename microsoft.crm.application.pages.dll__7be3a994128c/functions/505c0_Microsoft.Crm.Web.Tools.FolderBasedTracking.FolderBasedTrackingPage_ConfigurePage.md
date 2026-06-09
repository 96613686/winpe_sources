# Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::ConfigurePage

- ea: `0x505c0`
- end: `0x50865`
- name: `Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::ConfigurePage`
- size: `677`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x504b0`
- `0x505c0`
- `0x50870`
- `0x50a00`
- `0x50a20`
- `0x50ad0`
- `0x50ba0`
- `0x512f0`

## string_xrefs

- `0x50688`: `FolderBasedTracking.EnableServerSideSync`
- `0x5069a`: `<a href='/tools/social/social_area.aspx?pid=02&web=true' target='new' class='NavigateLink'>`
- `0x506a4`: `FolderBasedTracking.EnableServerSideSync.MailBox`
- `0x506d0`: `FolderBasedTracking.LearnMore.FwLink`
- `0x506dd`: `' target='new' class='NavigateLink'>`

## pseudocode

```c

```

## disassembly

```asm
0x505c0  ldarg.0
0x505c1  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::MailboxId
0x505c6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x505cb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultMailbox()
0x505d0  stloc.2
0x505d1  ldloca.s 2
0x505d3  constrained. [mscorlib]System.Guid
0x505d9  callvirt instance string [mscorlib]System.Object::ToString()
0x505de  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x505e3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x505e8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x505ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x505f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x505f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x505fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x50601  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x50606  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x5060b  call     class [mscorlib]System.Version Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::get_CarinaVersion()
0x50610  call     bool [mscorlib]System.Version::op_LessThan(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x50615  brfalse.s loc_50628
0x50617  ldarg.0
0x50618  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::IsDBVersionLesserThanCarina
0x5061d  ldstr    aTrue_0// "true"
0x50622  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x50627  ret
0x50628  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x5062d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x50632  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x50637  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5063c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x50641  stloc.0
0x50642  ldloc.0
0x50643  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_IsFolderBasedTrackingEnabled()
0x50648  brtrue.s loc_5065B
0x5064a  ldarg.0
0x5064b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::IsFolderBasedTrackingEnabled
0x50650  ldstr    aFalse// "false"
0x50655  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x5065a  ret
0x5065b  ldarg.0
0x5065c  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::IsFolderBasedTrackingEnabled
0x50661  ldstr    aTrue_0// "true"
0x50666  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x5066b  ldarg.0
0x5066c  call     instance void Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetMailboxInfo()
0x50671  ldarg.0
0x50672  ldloc.0
0x50673  call     instance bool Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::CheckIfServerSideSyncIsEnabled(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings orgSettings)
0x50678  brtrue   loc_5070E
0x5067d  ldarg.0
0x5067e  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::EnableServerSideSync
0x50683  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x50688  ldstr    aFolderbasedtra_3// "FolderBasedTracking.EnableServerSideSyn"...
0x5068d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x50692  ldc.i4.2
0x50693  newarr   [mscorlib]System.Object
0x50698  dup
0x50699  ldc.i4.0
0x5069a  ldstr    aAHrefToolsSoci// "<a href='/tools/social/social_area.aspx"...
0x5069f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x506a4  ldstr    aFolderbasedtra_4// "FolderBasedTracking.EnableServerSideSyn"...
0x506a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x506ae  ldstr    aA// "</a>"
0x506b3  call     string [mscorlib]System.String::Concat(string, string, string)
0x506b8  stelem.ref
0x506b9  dup
0x506ba  ldc.i4.1
0x506bb  ldc.i4.5
0x506bc  newarr   [mscorlib]System.String
0x506c1  dup
0x506c2  ldc.i4.0
0x506c3  ldstr    aAHref// "<a href='"
0x506c8  stelem.ref
0x506c9  dup
0x506ca  ldc.i4.1
0x506cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x506d0  ldstr    aFolderbasedtra_5// "FolderBasedTracking.LearnMore.FwLink"
0x506d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x506da  stelem.ref
0x506db  dup
0x506dc  ldc.i4.2
0x506dd  ldstr    aTargetNewClass// "' target='new' class='NavigateLink'>"
0x506e2  stelem.ref
0x506e3  dup
0x506e4  ldc.i4.3
0x506e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x506ea  ldstr    aFolderbasedtra_6// "FolderBasedTracking.LearnMore"
0x506ef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x506f4  stelem.ref
0x506f5  dup
0x506f6  ldc.i4.4
0x506f7  ldstr    aA// "</a>"
0x506fc  stelem.ref
0x506fd  call     string [mscorlib]System.String::Concat(string[])
0x50702  stelem.ref
0x50703  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x50708  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x5070d  ret
0x5070e  ldarg.0
0x5070f  ldloc.0
0x50710  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_MaxFolderBasedTrackingMappings()
0x50715  stfld    int32 Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::maxRecords
0x5071a  ldarg.0
0x5071b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::FolderBasedTrackingDialogDescriptionWithEmail
0x50720  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x50725  ldstr    aFolderbasedtra_7// "FolderBasedTracking.DialogDescription"
0x5072a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5072f  ldc.i4.1
0x50730  newarr   [mscorlib]System.Object
0x50735  dup
0x50736  ldc.i4.0
0x50737  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x5073c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_EmailAddress()
0x50741  callvirt instance string [mscorlib]System.Object::ToString()
0x50746  stelem.ref
0x50747  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0x5074c  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x50751  ldc.i4.4
0x50752  newarr   [mscorlib]System.String
0x50757  dup
0x50758  ldc.i4.0
0x50759  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x5075e  ldstr    aFolderbasedtra_8// "FolderBasedTracking.ExchangeFolder.Colu"...
0x50763  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x50768  stelem.ref
0x50769  dup
0x5076a  ldc.i4.1
0x5076b  ldstr    asc_11EF2A// ""
0x50770  stelem.ref
0x50771  dup
0x50772  ldc.i4.2
0x50773  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x50778  ldstr    aFoldebasedtrac// "FoldeBasedTracking.RegardingRecord.Colu"...
0x5077d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x50782  stelem.ref
0x50783  dup
0x50784  ldc.i4.3
0x50785  ldstr    asc_11EF2A// ""
0x5078a  stelem.ref
0x5078b  stloc.1
0x5078c  ldarg.0
0x5078d  call     instance string Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::get_FolderHierarchy()
0x50792  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Parse(string)
0x50797  ldstr    aFolder// "Folder"
0x5079c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x507a1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x507a6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x507ab  stloc.3
0x507ac  br.s     loc_507D7
0x507ae  ldloc.3
0x507af  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x507b4  stloc.s  4
0x507b6  ldarg.0
0x507b7  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::folderHierarchyIds
0x507bc  ldloc.s  4
0x507be  ldstr    aFolderid// "FolderId"
0x507c3  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x507c8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x507cd  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x507d2  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x507d7  ldloc.3
0x507d8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x507dd  brtrue.s loc_507AE
0x507df  leave.s  loc_507EB
0x507e1  ldloc.3
0x507e2  brfalse.s loc_507EA
0x507e4  ldloc.3
0x507e5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x507ea  endfinally
0x507eb  ldarg.0
0x507ec  call     instance void Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetUsersTrackedFoldersAndMappings()
0x507f1  ldarg.0
0x507f2  call     instance void Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::AddANewRowIfOpenedFromAnEntityContext()
0x507f7  ldarg.0
0x507f8  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::allFolderMappings
0x507fd  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x50802  ldarg.0
0x50803  ldloc.1
0x50804  ldarg.0
0x50805  ldfld    string[] Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::columnsIds
0x5080a  ldc.i4.0
0x5080b  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetDataRow(object[] columnData, string[] columnIds, int32 rowId)
0x50810  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x50815  ldc.i4.1
0x50816  stloc.s  5
0x50818  br.s     loc_5083F
0x5081a  ldarg.0
0x5081b  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::allFolderMappings
0x50820  callvirt instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection [System.Web]System.Web.UI.HtmlControls.HtmlTable::get_Rows()
0x50825  ldarg.0
0x50826  ldloc.1
0x50827  ldarg.0
0x50828  ldfld    string[] Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::columnsIds
0x5082d  ldloc.s  5
0x5082f  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetDataRow(object[] columnData, string[] columnIds, int32 rowId)
0x50834  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlTableRowCollection::Add(class [System.Web]System.Web.UI.HtmlControls.HtmlTableRow)
0x50839  ldloc.s  5
0x5083b  ldc.i4.1
0x5083c  add
0x5083d  stloc.s  5
0x5083f  ldloc.s  5
0x50841  ldarg.0
0x50842  ldfld    int32 Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::maxRecords
0x50847  ble.s    loc_5081A
0x50849  ldarg.0
0x5084a  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlInputHidden Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::MaxRecordsLength
0x5084f  ldarg.0
0x50850  ldflda   int32 Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::maxRecords
0x50855  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5085a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5085f  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlInputControl::set_Value(string)
0x50864  ret
```
