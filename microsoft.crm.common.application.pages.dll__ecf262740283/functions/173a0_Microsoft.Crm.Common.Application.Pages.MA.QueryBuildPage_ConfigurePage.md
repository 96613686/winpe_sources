# Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::ConfigurePage

- ea: `0x173a0`
- end: `0x17844`
- name: `Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::ConfigurePage`
- size: `1188`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x173a0`
- `0x178e0`
- `0x179a0`

## string_xrefs

- `0x173ee`: `/_static/_common/scripts/stage.js`
- `0x17708`: `MA.List.Dialogs.LQ.RemoveMembers.Button`

## pseudocode

```c

```

## disassembly

```asm
0x173a0  ldarg.0
0x173a1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x173a6  ldarg.0
0x173a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x173ac  ldstr    aLocidLqNorecor// "LOCID_LQ_NORECORDFOUND"
0x173b1  ldarg.0
0x173b2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x173b7  ldstr    aErrorMessageNo// "Error_Message_NoRecordFound_LQ"
0x173bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x173c1  ldc.i4.0
0x173c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x173c7  ldarg.0
0x173c8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x173cd  ldstr    aLocidLqNorecor_0// "LOCID_LQ_NORECORDSELECTED"
0x173d2  ldarg.0
0x173d3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x173d8  ldstr    aErrorMessageNo_0// "Error_Message_NoRecordSelected_LQ"
0x173dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x173e2  ldc.i4.0
0x173e3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x173e8  ldarg.0
0x173e9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x173ee  ldstr    aStaticCommonSc_0// "/_static/_common/scripts/stage.js"
0x173f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x173f8  ldarg.0
0x173f9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x173fe  ldstr    aStaticOobwebre_0// "/_static/oobwebresource/CRM/ClientUtili"...
0x17403  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x17408  ldarg.0
0x17409  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1740e  ldstr    aStaticOobwebre_1// "/_static/oobwebresource/Marketing/List/"...
0x17413  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x17418  ldarg.0
0x17419  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1741e  ldstr    aStaticGridCmds_0// "/_static/_grid/cmds/util.js"
0x17423  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x17428  ldarg.0
0x17429  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1742e  ldstr    aStaticGridActi// "/_static/_grid/action.js"
0x17433  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x17438  ldarg.0
0x17439  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1743e  ldstr    aMaListsListqua// "/MA/Lists/ListQualificationdlg/dlg_List"...
0x17443  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x17448  ldarg.0
0x17449  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1744e  ldstr    aMaListsListqua_0// "/MA/Lists/ListQualificationdlg/dlg_List"...
0x17453  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x17458  ldarg.0
0x17459  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1745e  ldstr    aMaListsListqua_1// "/MA/Lists/ListQualificationdlg/dlg_dyna"...
0x17463  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x17468  ldarg.0
0x17469  ldstr    aUserquery// "userquery"
0x1746e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17473  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17478  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1747d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17482  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17487  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::_privilegeCheck
0x1748c  ldarg.0
0x1748d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::_privilegeCheck
0x17492  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.PrivilegeCheck::get_CanRead()
0x17497  brfalse.s loc_1749F
0x17499  ldarg.0
0x1749a  call     instance void Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::ConfigureSavedSearches()
0x1749f  ldarg.0
0x174a0  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x174a5  ldc.i4.3
0x174a6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_Modes(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindModes)
0x174ab  ldarg.0
0x174ac  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x174b1  ldc.i4.2
0x174b2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_StartupMode(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindStartupMode)
0x174b7  ldarg.0
0x174b8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x174bd  ldc.i4   0x187
0x174c2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_Buttons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AdvancedFindButtons)
0x174c7  ldarg.0
0x174c8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x174cd  ldc.i4.0
0x174ce  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ValidQueryType(int32)
0x174d3  ldarg.0
0x174d4  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x174d9  ldc.i4.1
0x174da  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_IncludeSystemQuery(bool)
0x174df  ldarg.0
0x174e0  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x174e5  ldc.i4.1
0x174e6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_IncludeUserQuery(bool)
0x174eb  ldarg.0
0x174ec  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x174f1  ldc.i4.0
0x174f2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_SaveChangesAlert(bool)
0x174f7  ldarg.0
0x174f8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x174fd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17502  ldstr    aViewtype_0// "ViewType"
0x17507  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1750c  stloc.0
0x1750d  ldloc.0
0x1750e  brfalse.s loc_17531
0x17510  ldloc.0
0x17511  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17516  ldc.i4.0
0x17517  ble.s    loc_17531
0x17519  ldarg.0
0x1751a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x1751f  ldloc.0
0x17520  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17525  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1752a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x1752f  br.s     loc_17541
0x17531  ldarg.0
0x17532  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x17537  ldc.i4   0x1086
0x1753c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x17541  ldarg.0
0x17542  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17547  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1754c  ldstr    aFetchpresent// "fetchPresent"
0x17551  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17556  stloc.1
0x17557  ldarg.0
0x17558  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1755d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17562  ldstr    aQueryobjecttyp// "QueryObjectType"
0x17567  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1756c  stloc.2
0x1756d  ldloc.2
0x1756e  brfalse.s loc_17591
0x17570  ldloc.2
0x17571  callvirt instance int32 [mscorlib]System.String::get_Length()
0x17576  ldc.i4.0
0x17577  ble.s    loc_17591
0x17579  ldarg.0
0x1757a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x1757f  ldloc.2
0x17580  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17585  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1758a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x1758f  br.s     loc_175A1
0x17591  ldarg.0
0x17592  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x17597  ldc.i4   0x1086
0x1759c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ViewType(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ViewType)
0x175a1  ldarg.0
0x175a2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x175a7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x175ac  ldstr    aQueryid// "QueryId"
0x175b1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x175b6  stloc.3
0x175b7  ldloc.3
0x175b8  brfalse.s loc_175E0
0x175ba  ldloc.3
0x175bb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x175c0  ldc.i4.0
0x175c1  ble.s    loc_175E0
0x175c3  ldloc.1
0x175c4  brtrue.s loc_175E0
0x175c6  ldloc.2
0x175c7  ldnull
0x175c8  cgt.un
0x175ca  ldstr    aToLoadAQueryBo// "To load a query, both QueryId and Query"...
0x175cf  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x175d4  ldarg.0
0x175d5  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x175da  ldloc.3
0x175db  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_QueryId(string)
0x175e0  ldarg.0
0x175e1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x175e6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::get_EntityList()
0x175eb  ldarg.0
0x175ec  ldc.i4.0
0x175ed  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::PopulateAdvancedFindEntities(bool forGrid)
0x175f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x175f7  ldarg.0
0x175f8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x175fd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17602  ldstr    aListid// "ListId"
0x17607  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1760c  stloc.s  4
0x1760e  ldstr    aList// "list"
0x17613  ldloc.s  4
0x17615  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x1761a  ldc.i4.1
0x1761b  newarr   [mscorlib]System.String
0x17620  dup
0x17621  ldc.i4.0
0x17622  ldstr    aQuery// "query"
0x17627  stelem.ref
0x17628  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1762d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17632  stloc.s  5
0x17634  ldloc.s  5
0x17636  ldstr    aQuery// "query"
0x1763b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x17640  brfalse.s loc_17659
0x17642  ldarg.0
0x17643  ldloc.s  5
0x17645  ldstr    aQuery// "query"
0x1764a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1764f  castclass [mscorlib]System.String
0x17654  stfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::fetchXml
0x17659  ldarg.0
0x1765a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1765f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17664  ldstr    aListmembertype// "ListMemberType"
0x17669  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1766e  stloc.s  8
0x17670  ldloc.s  8
0x17672  brfalse.s loc_176A9
0x17674  ldloc.s  8
0x17676  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1767b  ldc.i4.0
0x1767c  ble.s    loc_176A9
0x1767e  ldarg.0
0x1767f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::lqAdvFind
0x17684  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17689  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1768e  ldloc.s  8
0x17690  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17695  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x1769a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1769f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x176a4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_EntityName(string)
0x176a9  ldarg.0
0x176aa  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x176af  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x176b4  ldstr    aInvoketype// "InvokeType"
0x176b9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x176be  ldarg.0
0x176bf  ldfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryAddAction
0x176c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x176c9  brfalse.s loc_176E0
0x176cb  ldarg.0
0x176cc  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::btnLqAction
0x176d1  ldstr    aMaListDialogsL// "MA.List.Dialogs.LQ.AddMembers.Button"
0x176d6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x176db  br       loc_177D1
0x176e0  ldarg.0
0x176e1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x176e6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x176eb  ldstr    aInvoketype// "InvokeType"
0x176f0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x176f5  ldarg.0
0x176f6  ldfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryRemoveAction
0x176fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17700  brfalse.s loc_17717
0x17702  ldarg.0
0x17703  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::btnLqAction
0x17708  ldstr    aMaListDialogsL_0// "MA.List.Dialogs.LQ.RemoveMembers.Button"
0x1770d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x17712  br       loc_177D1
0x17717  ldarg.0
0x17718  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1771d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17722  ldstr    aInvoketype// "InvokeType"
0x17727  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1772c  ldarg.0
0x1772d  ldfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryKeepAction
0x17732  call     bool [mscorlib]System.String::op_Equality(string, string)
0x17737  brfalse.s loc_1774E
0x17739  ldarg.0
0x1773a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::btnLqAction
0x1773f  ldstr    aMaListDialogsL_1// "MA.List.Dialogs.LQ.KeepMembers.Button"
0x17744  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_ResourceId(string)
0x17749  br       loc_177D1
0x1774e  ldarg.0
0x1774f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x17754  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x17759  ldstr    aInvoketype// "InvokeType"
0x1775e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x17763  ldarg.0
0x17764  ldfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryUseAction
0x17769  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1776e  brfalse.s loc_177C5
0x17770  ldarg.0
0x17771  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x17776  ldstr    aMaListDialogsL_2// "MA.List.Dialogs.LQ.UseQuery.Button"
0x1777b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17780  dup
0x17781  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAccessKey(string)
0x17786  stloc.s  6
0x17788  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::DecorateAccessKey(string)
0x1778d  stloc.s  7
0x1778f  ldarg.0
0x17790  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::btnLqAction
0x17795  ldloc.s  6
0x17797  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x1779c  ldarg.0
0x1779d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::btnLqAction
0x177a2  ldloc.s  7
0x177a4  callvirt instance void [System.Web]System.Web.UI.HtmlControls.HtmlContainerControl::set_InnerHtml(string)
0x177a9  ldarg.0
0x177aa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::btnUseQuery
0x177af  ldloc.s  6
0x177b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button::set_AccessKey(string)
0x177b6  ldarg.0
0x177b7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Button Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::btnUseQuery
  ... truncated ...
```
