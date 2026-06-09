# Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::ConfigureHeader

- ea: `0xf4d30`
- end: `0xf4f44`
- name: `Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::ConfigureHeader`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xf4d30`

## string_xrefs

- `0xf4e7a`: `LOCID_ALERT_ERROR_HELPLINK`
- `0xf4e7f`: `http://go.microsoft.com/fwlink/?LinkID=398563&lcid={0}&sv={1}&de={2}&client=SSS`
- `0xf4f2a`: `var cmd = Wall.Control.Utils.RemoteCommandFactory.createRemoteCommand('MessageBar', 'UpdateLastAlertsAccessTime', null);\n									cmd.Execute(null);`
- `0xf4f37`: `updatelastalertsaccesstime`

## pseudocode

```c

```

## disassembly

```asm
0xf4d30  ldarg.0
0xf4d31  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::ConfigureHeader()
0xf4d36  ldarg.0
0xf4d37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4d3c  ldc.i4.1
0xf4d3d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xf4d42  ldsfld   string[] Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::styleSheets
0xf4d47  stloc.s  4
0xf4d49  ldc.i4.0
0xf4d4a  stloc.s  5
0xf4d4c  br.s     loc_F4D68
0xf4d4e  ldloc.s  4
0xf4d50  ldloc.s  5
0xf4d52  ldelem.ref
0xf4d53  stloc.s  6
0xf4d55  ldarg.0
0xf4d56  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4d5b  ldloc.s  6
0xf4d5d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xf4d62  ldloc.s  5
0xf4d64  ldc.i4.1
0xf4d65  add
0xf4d66  stloc.s  5
0xf4d68  ldloc.s  5
0xf4d6a  ldloc.s  4
0xf4d6c  ldlen
0xf4d6d  conv.i4
0xf4d6e  blt.s    loc_F4D4E
0xf4d70  ldc.i4.0
0xf4d71  stloc.s  7
0xf4d73  br.s     loc_F4DA6
0xf4d75  ldarg.0
0xf4d76  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4d7b  ldsfld   string[][] Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::resourceStrings
0xf4d80  ldloc.s  7
0xf4d82  ldelem.ref
0xf4d83  ldc.i4.0
0xf4d84  ldelem.ref
0xf4d85  ldarg.0
0xf4d86  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf4d8b  ldsfld   string[][] Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::resourceStrings
0xf4d90  ldloc.s  7
0xf4d92  ldelem.ref
0xf4d93  ldc.i4.1
0xf4d94  ldelem.ref
0xf4d95  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf4d9a  ldc.i4.0
0xf4d9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf4da0  ldloc.s  7
0xf4da2  ldc.i4.1
0xf4da3  add
0xf4da4  stloc.s  7
0xf4da6  ldloc.s  7
0xf4da8  ldsfld   string[][] Microsoft.Crm.Application.Pages.WallPage.TraceWallPage::resourceStrings
0xf4dad  ldlen
0xf4dae  conv.i4
0xf4daf  blt.s    loc_F4D75
0xf4db1  ldarg.0
0xf4db2  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0xf4db7  ldstr    aLocidMailboxTo// "LOCID_MAILBOX_TOOLTIP"
0xf4dbc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf4dc1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf4dc6  ldc.i4   0x2586
0xf4dcb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf4dd0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xf4dd5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xf4dda  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xf4ddf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf4de4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf4de9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xf4dee  ldc.i4.0
0xf4def  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf4df4  ldarg.0
0xf4df5  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0xf4dfa  ldstr    aLocidEmailServ// "LOCID_EMAIL_SERVER_TOOLTIP"
0xf4dff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf4e04  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf4e09  ldc.i4   0x2585
0xf4e0e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xf4e13  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xf4e18  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xf4e1d  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xf4e22  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf4e27  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf4e2c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xf4e31  ldc.i4.0
0xf4e32  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf4e37  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0xf4e3c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf4e41  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf4e46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xf4e4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xf4e50  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf4e55  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0xf4e5a  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0xf4e5f  stloc.0
0xf4e60  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnPremise()
0xf4e65  brtrue.s loc_F4E6E
0xf4e67  ldstr    aOnline_0// "Online"
0xf4e6c  br.s     loc_F4E73
0xf4e6e  ldstr    aOnprem// "OnPrem"
0xf4e73  stloc.1
0xf4e74  ldarg.0
0xf4e75  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentAppHeader()
0xf4e7a  ldstr    aLocidAlertErro// "LOCID_ALERT_ERROR_HELPLINK"
0xf4e7f  ldstr    aHttpGoMicrosof_19// "http://go.microsoft.com/fwlink/?LinkID="...
0xf4e84  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xf4e89  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xf4e8e  box      [mscorlib]System.Int32
0xf4e93  ldloc.0
0xf4e94  ldloc.1
0xf4e95  call     string [mscorlib]System.String::Format(string, object, object, object)
0xf4e9a  ldc.i4.0
0xf4e9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf4ea0  ldarg.0
0xf4ea1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4ea6  ldstr    aMessagebar// "MessageBar"
0xf4eab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xf4eb0  ldarg.0
0xf4eb1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4eb6  ldstr    aTracelog_0// "TraceLog"
0xf4ebb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xf4ec0  ldc.i4   0x7CF
0xf4ec5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xf4eca  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_Teams()
0xf4ecf  ldlen
0xf4ed0  conv.i4
0xf4ed1  call     int32 [mscorlib]System.Math::Min(int32, int32)
0xf4ed6  stloc.2
0xf4ed7  ldloc.2
0xf4ed8  ldc.i4.1
0xf4ed9  add
0xf4eda  newarr   [mscorlib]System.Guid
0xf4edf  stloc.3
0xf4ee0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xf4ee5  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_Teams()
0xf4eea  ldloc.3
0xf4eeb  ldloc.2
0xf4eec  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0xf4ef1  ldloc.3
0xf4ef2  ldloc.2
0xf4ef3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xf4ef8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0xf4efd  stelem   [mscorlib]System.Guid
0xf4f02  ldarg.0
0xf4f03  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4f08  ldstr    aAllOwnerIds// "ALL_OWNER_IDS"
0xf4f0d  ldloc.3
0xf4f0e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVarArray(string, class [mscorlib]System.Collections.IEnumerable)
0xf4f13  ldarg.0
0xf4f14  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xf4f19  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xf4f1e  ldstr    aId// "id"
0xf4f23  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xf4f28  brtrue.s loc_F4F43
0xf4f2a  ldstr    aVarCmdWallCont// "var cmd = Wall.Control.Utils.RemoteComm"...
0xf4f2f  stloc.s  8
0xf4f31  ldarg.0
0xf4f32  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xf4f37  ldstr    aUpdatelastaler// "updatelastalertsaccesstime"
0xf4f3c  ldloc.s  8
0xf4f3e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(string, string)
0xf4f43  ret
```
