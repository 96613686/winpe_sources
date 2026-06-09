# Microsoft.Crm.Dialogs.ShareDialogPage::ConfigurePage

- ea: `0x1e170`
- end: `0x1e3e2`
- name: `Microsoft.Crm.Dialogs.ShareDialogPage::ConfigurePage`
- size: `626`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x1e288`: `Grid.Common.Alt.SortedColumn.Down`
- `0x1e2a9`: `Grid.Common.Alt.SortedColumn.Up`
- `0x1e17c`: `/_nav/taskbox.css.aspx`
- `0x1e204`: `Web._grid.cmds.getshareaccess.xsl_37`
- `0x1e225`: `Web._grid.cmds.getshareaccess.xsl_30`
- `0x1e246`: `GetShareAccess.OrganizationOwned`
- `0x1e301`: `LOCID_PRIVILEGE_READ`
- `0x1e322`: `LOCID_PRIVILEGE_WRITE`
- `0x1e343`: `LOCID_PRIVILEGE_DELETE`
- `0x1e364`: `LOCID_PRIVILEGE_APPEND`
- `0x1e385`: `LOCID_PRIVILEGE_ASSIGN`
- `0x1e3a6`: `LOCID_PRIVILEGE_SHARE`

## pseudocode

```c

```

## disassembly

```asm
0x1e170  ldarg.0
0x1e171  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x1e176  ldarg.0
0x1e177  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e17c  ldstr    aNavTaskboxCssA// "/_nav/taskbox.css.aspx"
0x1e181  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x1e186  ldarg.0
0x1e187  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e18c  ldstr    aStaticGridCmds_0// "/_static/_grid/cmds/multiaction.js"
0x1e191  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1e196  ldarg.0
0x1e197  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e19c  ldstr    aStaticControls_1// "/_static/_controls/lookup/lookup.js"
0x1e1a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1e1a6  ldarg.0
0x1e1a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e1ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0x1e1b1  ldarg.0
0x1e1b2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e1b7  ldstr    aLocidCannotSha// "LOCID_CANNOT_SHARE"
0x1e1bc  ldarg.0
0x1e1bd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e1c2  ldstr    aWebGridCmdsDlg_91// "Web._grid.cmds.dlg_share.aspx_101"
0x1e1c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e1cc  ldc.i4.0
0x1e1cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e1d2  ldarg.0
0x1e1d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e1d8  ldstr    aLocidDoYouWant// "LOCID_DO_YOU_WANT_TO_SHARE"
0x1e1dd  ldarg.0
0x1e1de  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e1e3  ldstr    aWebGridCmdsDlg_92// "Web._grid.cmds.dlg_share.aspx_108"
0x1e1e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e1ed  ldc.i4.0
0x1e1ee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e1f3  ldarg.0
0x1e1f4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e1f9  ldstr    aLocidRecordIsN// "LOCID_RECORD_IS_NOT_SHARED"
0x1e1fe  ldarg.0
0x1e1ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e204  ldstr    aWebGridCmdsGet// "Web._grid.cmds.getshareaccess.xsl_37"
0x1e209  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e20e  ldc.i4.0
0x1e20f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e214  ldarg.0
0x1e215  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e21a  ldstr    aLocidShareOnly// "LOCID_SHARE_ONLY_ONE"
0x1e21f  ldarg.0
0x1e220  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e225  ldstr    aWebGridCmdsGet_0// "Web._grid.cmds.getshareaccess.xsl_30"
0x1e22a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e22f  ldc.i4.0
0x1e230  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e235  ldarg.0
0x1e236  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e23b  ldstr    aLocidShareOrgO// "LOCID_SHARE_ORG_OWNED"
0x1e240  ldarg.0
0x1e241  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e246  ldstr    aGetshareaccess// "GetShareAccess.OrganizationOwned"
0x1e24b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e250  ldc.i4.0
0x1e251  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e256  ldarg.0
0x1e257  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e25c  ldstr    aLocidNoRecords// "LOCID_NO_RECORDS_SELECTED"
0x1e261  ldarg.0
0x1e262  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e267  ldstr    aWebGridCmdsDlg_93// "Web._grid.cmds.dlg_share.aspx_204"
0x1e26c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e271  ldc.i4.0
0x1e272  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e277  ldarg.0
0x1e278  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e27d  ldstr    aLocidAltColumn// "LOCID_ALT_COLUMNSORTORDER_DOWN"
0x1e282  ldarg.0
0x1e283  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e288  ldstr    aGridCommonAltS// "Grid.Common.Alt.SortedColumn.Down"
0x1e28d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e292  ldc.i4.0
0x1e293  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e298  ldarg.0
0x1e299  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e29e  ldstr    aLocidAltColumn_0// "LOCID_ALT_COLUMNSORTORDER_UP"
0x1e2a3  ldarg.0
0x1e2a4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e2a9  ldstr    aGridCommonAltS_0// "Grid.Common.Alt.SortedColumn.Up"
0x1e2ae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e2b3  ldc.i4.0
0x1e2b4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e2b9  ldarg.0
0x1e2ba  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e2bf  ldstr    aLocidFmtSharec// "LOCID_FMT_SHARECHECKBOX"
0x1e2c4  ldarg.0
0x1e2c5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e2ca  ldstr    aGridSharecheck// "Grid.ShareCheckbox.Title.Format"
0x1e2cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e2d4  ldc.i4.0
0x1e2d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e2da  ldarg.0
0x1e2db  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e2e0  ldstr    aLocidTitleSele// "LOCID_TITLE_SELECTUSERTEAM"
0x1e2e5  ldarg.0
0x1e2e6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e2eb  ldstr    aGridSelectuser// "Grid.SelectUserTeam.Title"
0x1e2f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e2f5  ldc.i4.0
0x1e2f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e2fb  ldarg.0
0x1e2fc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e301  ldstr    aLocidPrivilege// "LOCID_PRIVILEGE_READ"
0x1e306  ldarg.0
0x1e307  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e30c  ldstr    aWebGridCmdsDlg_94// "Web._grid.cmds.dlg_share.aspx_449"
0x1e311  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e316  ldc.i4.0
0x1e317  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e31c  ldarg.0
0x1e31d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e322  ldstr    aLocidPrivilege_0// "LOCID_PRIVILEGE_WRITE"
0x1e327  ldarg.0
0x1e328  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e32d  ldstr    aWebGridCmdsDlg_95// "Web._grid.cmds.dlg_share.aspx_450"
0x1e332  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e337  ldc.i4.0
0x1e338  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e33d  ldarg.0
0x1e33e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e343  ldstr    aLocidPrivilege_1// "LOCID_PRIVILEGE_DELETE"
0x1e348  ldarg.0
0x1e349  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e34e  ldstr    aWebGridCmdsDlg_96// "Web._grid.cmds.dlg_share.aspx_451"
0x1e353  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e358  ldc.i4.0
0x1e359  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e35e  ldarg.0
0x1e35f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e364  ldstr    aLocidPrivilege_2// "LOCID_PRIVILEGE_APPEND"
0x1e369  ldarg.0
0x1e36a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e36f  ldstr    aWebGridCmdsDlg_97// "Web._grid.cmds.dlg_share.aspx_452"
0x1e374  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e379  ldc.i4.0
0x1e37a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e37f  ldarg.0
0x1e380  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e385  ldstr    aLocidPrivilege_3// "LOCID_PRIVILEGE_ASSIGN"
0x1e38a  ldarg.0
0x1e38b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e390  ldstr    aWebGridCmdsDlg_98// "Web._grid.cmds.dlg_share.aspx_453"
0x1e395  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e39a  ldc.i4.0
0x1e39b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e3a0  ldarg.0
0x1e3a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e3a6  ldstr    aLocidPrivilege_4// "LOCID_PRIVILEGE_SHARE"
0x1e3ab  ldarg.0
0x1e3ac  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1e3b1  ldstr    aWebGridCmdsDlg_99// "Web._grid.cmds.dlg_share.aspx_454"
0x1e3b6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1e3bb  ldc.i4.0
0x1e3bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1e3c1  ldarg.0
0x1e3c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1e3c7  ldstr    aSself// "_sSelf"
0x1e3cc  ldarg.0
0x1e3cd  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x1e3d2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_SystemUserId()
0x1e3d7  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x1e3dc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x1e3e1  ret
```
