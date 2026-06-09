# Microsoft.Crm.Application.Menus.AppMenuBar::BuildHelpMenu_0

- ea: `0x24c00`
- end: `0x250df`
- name: `Microsoft.Crm.Application.Menus.AppMenuBar::BuildHelpMenu_0`
- size: `1247`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x24bf0`

## callees

- `0x24c00`
- `0x25120`
- `0x25700`
- `0x25740`
- `0x25760`
- `0x25780`
- `0x25800`

## string_xrefs

- `0x24e1d`: `safeWindowOpen( Mscrm.CrmUri.create('http://go.microsoft.com/fwlink/?LinkId=35152&clcid=0x`
- `0x24e7e`: `http://go.microsoft.com/fwlink/?LinkId=`
- `0x24eb3`: `safeWindowOpen( Mscrm.CrmUri.create('`
- `0x24fcf`: `safeWindowOpen( Mscrm.CrmUri.create('`
- `0x25034`: `safeWindowOpen( Mscrm.CrmUri.create('`
- `0x24eba`: `'), 'HelpUpdates', 'width=790, height=500, menubar=1, toolbar=1, status=1, scrollbars=1, resizable=1');`
- `0x24ecf`: `AppMenuBar_Help_HelpUpdates`
- `0x24ede`: `mnu_helpUpdates`
- `0x24f2d`: `safeWindowOpen( '`
- `0x25085`: `openStdDlg(Mscrm.CrmUri.create('/about/default.aspx'), 'MSCRMAbout', 570, 548)`

## pseudocode

```c

```

## disassembly

```asm
0x24c00  ldarg.1
0x24c01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24c06  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x24c0b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24c10  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup
0x24c15  stloc.0
0x24c16  ldloc.0
0x24c17  ldarg.0
0x24c18  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x24c1d  ldstr    aHelp// "help"
0x24c22  call     string [mscorlib]System.String::Concat(string, string)
0x24c27  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24c2c  ldloc.0
0x24c2d  ldloc.0
0x24c2e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24c33  ldstr    aMenuLabelHelp// "Menu_Label_Help"
0x24c38  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24c3d  dup
0x24c3e  stloc.3
0x24c3f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x24c44  ldloc.3
0x24c45  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24c4a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24c4f  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserUICulture()
0x24c54  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x24c59  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x24c5e  brfalse.s loc_24CA4
0x24c60  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24c65  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_ClientUserUILanguageId()
0x24c6a  stloc.s  4
0x24c6c  ldc.i4   0x40D
0x24c71  stloc.s  5
0x24c73  ldloca.s 4
0x24c75  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x24c7a  ldloc.s  5
0x24c7c  beq.s    loc_24C81
0x24c7e  ldc.i4.1
0x24c7f  br.s     loc_24C8B
0x24c81  ldloca.s 4
0x24c83  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x24c88  ldc.i4.0
0x24c89  ceq
0x24c8b  brfalse.s loc_24CA4
0x24c8d  ldloc.0
0x24c8e  ldstr    aImgsIco16HelpR// "/_imgs/ico/16_help_rtl.gif"
0x24c93  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24c98  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24c9d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x24ca2  br.s     loc_24CB9
0x24ca4  ldloc.0
0x24ca5  ldstr    aImgsIco16HelpG// "/_imgs/ico/16_help.gif"
0x24caa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24caf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24cb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x24cb9  ldloc.0
0x24cba  ldc.i4.2
0x24cbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Alignment(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarAlignment)
0x24cc0  ldloc.0
0x24cc1  ldc.i4.1
0x24cc2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x24cc7  ldloc.0
0x24cc8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24ccd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24cd2  ldarg.0
0x24cd3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24cd8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24cdd  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24ce2  dup
0x24ce3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24ce8  ldstr    aAppmenubarHelp// "AppMenuBar_HelpOn"
0x24ced  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24cf2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24cf7  dup
0x24cf8  ldstr    aLoadhelp// "loadHelp();"
0x24cfd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24d02  ldstr    aMnuHelpon// "mnu_helpOn"
0x24d07  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24d0c  ldloc.0
0x24d0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24d12  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x24d17  ldloc.0
0x24d18  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24d1d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24d22  ldarg.0
0x24d23  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24d28  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24d2d  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24d32  dup
0x24d33  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24d38  ldstr    aAppmenubarHelp_0// "AppMenuBar_Help_Contents"
0x24d3d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24d42  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24d47  dup
0x24d48  ldstr    aLoadhelpWhatsn// "loadHelp('##WHATSNEW##');"
0x24d4d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24d52  ldstr    aMnuHelpcontent// "mnu_helpContent"
0x24d57  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24d5c  ldloc.0
0x24d5d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24d62  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24d67  ldarg.0
0x24d68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24d6d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24d72  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24d77  dup
0x24d78  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24d7d  ldstr    aAppmenubarHelp_1// "AppMenuBar_Help_AdministratorsGuide"
0x24d82  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24d87  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24d8c  dup
0x24d8d  ldstr    aLoadhelpAdming// "loadHelp('##ADMINGUIDE##');"
0x24d92  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24d97  ldstr    aMnuAdminguide// "mnu_adminGuide"
0x24d9c  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24da1  ldloc.0
0x24da2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24da7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24dac  ldarg.0
0x24dad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24db2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24db7  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24dbc  dup
0x24dbd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24dc2  ldstr    aAppmenubarHelp_2// "AppMenuBar_Help_Troubleshooting"
0x24dc7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24dcc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24dd1  dup
0x24dd2  ldstr    aLoadhelpTroubl// "loadHelp('##TROUBLESHOOT##');"
0x24dd7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24ddc  ldstr    aMnuTroubleshoo// "mnu_troubleShoot"
0x24de1  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24de6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsLive()
0x24deb  stloc.1
0x24dec  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x24df1  brfalse  loc_24F57
0x24df6  ldloc.0
0x24df7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24dfc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x24e01  ldloc.0
0x24e02  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24e07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24e0c  ldarg.0
0x24e0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24e12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24e17  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24e1c  dup
0x24e1d  ldstr    aSafewindowopen// "safeWindowOpen( Mscrm.CrmUri.create('ht"...
0x24e22  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x24e27  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x24e2c  stloc.s  5
0x24e2e  ldloca.s 5
0x24e30  ldstr    aX// "X"
0x24e35  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24e3a  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x24e3f  ldstr    aMscrmliveWidth// "'), 'MSCRMLive', 'width=790, height=500"...
0x24e44  call     string [mscorlib]System.String::Concat(string, string, string)
0x24e49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24e4e  dup
0x24e4f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24e54  ldstr    aAppmenubarHelp_3// "AppMenuBar_Help_CrmLive"
0x24e59  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24e5e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24e63  ldstr    aMnuCrmlive// "mnu_crmLive"
0x24e68  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24e6d  ldloc.1
0x24e6e  brtrue.s loc_24EE8
0x24e70  ldstr    a76816// "76816"
0x24e75  stloc.s  6
0x24e77  ldstr    a76815// "76815"
0x24e7c  stloc.s  7
0x24e7e  ldstr    aHttpGoMicrosof// "http://go.microsoft.com/fwlink/?LinkId="
0x24e83  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x24e88  brtrue.s loc_24E8E
0x24e8a  ldloc.s  6
0x24e8c  br.s     loc_24E90
0x24e8e  ldloc.s  7
0x24e90  call     string [mscorlib]System.String::Concat(string, string)
0x24e95  stloc.s  8
0x24e97  ldloc.0
0x24e98  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24e9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24ea2  ldarg.0
0x24ea3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24ea8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24ead  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24eb2  dup
0x24eb3  ldstr    aSafewindowopen_0// "safeWindowOpen( Mscrm.CrmUri.create('"
0x24eb8  ldloc.s  8
0x24eba  ldstr    aHelpupdatesWid// "'), 'HelpUpdates', 'width=790, height=5"...
0x24ebf  call     string [mscorlib]System.String::Concat(string, string, string)
0x24ec4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24ec9  dup
0x24eca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24ecf  ldstr    aAppmenubarHelp_4// "AppMenuBar_Help_HelpUpdates"
0x24ed4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24ed9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24ede  ldstr    aMnuHelpupdates// "mnu_helpUpdates"
0x24ee3  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24ee8  ldloc.1
0x24ee9  brfalse.s loc_24F57
0x24eeb  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveProductTourLinkUrl()
0x24ef0  stloc.s  9
0x24ef2  ldloc.s  9
0x24ef4  ldnull
0x24ef5  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x24efa  brfalse.s loc_24F57
0x24efc  ldloc.0
0x24efd  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24f02  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24f07  ldarg.0
0x24f08  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24f0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24f12  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24f17  dup
0x24f18  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24f1d  ldstr    aAppmenubarHelp_5// "AppMenuBar_Help_ProductTour"
0x24f22  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24f27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24f2c  dup
0x24f2d  ldstr    aSafewindowopen_1// "safeWindowOpen( '"
0x24f32  ldloc.s  9
0x24f34  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x24f39  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x24f3e  ldstr    aMscrmproductto// "', 'MSCRMProductTour', 'width=810, heig"...
0x24f43  call     string [mscorlib]System.String::Concat(string, string, string)
0x24f48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24f4d  ldstr    aMnuProducttour// "mnu_producttour"
0x24f52  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24f57  ldloc.1
0x24f58  brfalse  loc_2505E
0x24f5d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOsdpOrganization()
0x24f62  brtrue   loc_2505E
0x24f67  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveLegalLinkUrl()
0x24f6c  stloc.s  0xA
0x24f6e  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrievePrivacyLinkUrl()
0x24f73  stloc.s  0xB
0x24f75  ldloc.s  0xB
0x24f77  ldnull
0x24f78  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x24f7d  brtrue.s loc_24F89
0x24f7f  ldloc.s  0xA
0x24f81  ldnull
0x24f82  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x24f87  brfalse.s loc_24F94
0x24f89  ldloc.0
0x24f8a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24f8f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x24f94  ldloc.s  0xA
0x24f96  ldnull
0x24f97  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x24f9c  brfalse.s loc_24FF9
0x24f9e  ldloc.0
0x24f9f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x24fa4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x24fa9  ldarg.0
0x24faa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x24faf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x24fb4  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x24fb9  dup
0x24fba  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x24fbf  ldstr    aAppmenubarHelp_6// "AppMenuBar_Help_Legal"
0x24fc4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24fc9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x24fce  dup
0x24fcf  ldstr    aSafewindowopen_0// "safeWindowOpen( Mscrm.CrmUri.create('"
0x24fd4  ldloc.s  0xA
0x24fd6  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x24fdb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x24fe0  ldstr    aMscrmlegalWidt// "'), 'MSCRMLegal', 'width=790, height=50"...
0x24fe5  call     string [mscorlib]System.String::Concat(string, string, string)
0x24fea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x24fef  ldstr    aMnuLegal// "mnu_legal"
0x24ff4  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x24ff9  ldloc.s  0xB
0x24ffb  ldnull
0x24ffc  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x25001  brfalse.s loc_2505E
0x25003  ldloc.0
0x25004  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x25009  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x2500e  ldarg.0
0x2500f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton Microsoft.Crm.Application.Menus.AppMenuBar::CreateButton()
0x25014  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x25019  castclass [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton
0x2501e  dup
0x2501f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x25024  ldstr    aAppmenubarHelp_7// "AppMenuBar_Help_Privacy"
0x25029  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2502e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x25033  dup
0x25034  ldstr    aSafewindowopen_0// "safeWindowOpen( Mscrm.CrmUri.create('"
0x25039  ldloc.s  0xB
0x2503b  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x25040  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x25045  ldstr    aMscrmprivacyWi// "'), 'MSCRMPrivacy', 'width=790, height="...
0x2504a  call     string [mscorlib]System.String::Concat(string, string, string)
0x2504f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x25054  ldstr    aMnuPrivacy// "mnu_privacy"
0x25059  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2505e  ldloc.0
  ... truncated ...
```
