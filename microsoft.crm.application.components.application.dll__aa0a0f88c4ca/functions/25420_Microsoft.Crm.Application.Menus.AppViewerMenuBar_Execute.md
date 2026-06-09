# Microsoft.Crm.Application.Menus.AppViewerMenuBar::Execute

- ea: `0x25420`
- end: `0x256d3`
- name: `Microsoft.Crm.Application.Menus.AppViewerMenuBar::Execute`
- size: `691`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x24210`
- `0x24240`
- `0x242b0`
- `0x24430`
- `0x24bf0`
- `0x25400`
- `0x25420`

## string_xrefs

- `0x254fa`: `Menu_Label_ShowComments`
- `0x25613`: `Menu_Label_ShowComments`
- `0x25647`: `Menu_Label_ShowComments`
- `0x25504`: `ShowComments();`
- `0x2561d`: `ShowComments();`
- `0x2550a`: `mnuShowComments`
- `0x25651`: `btnShowComments`

## pseudocode

```c

```

## disassembly

```asm
0x25420  ldarg.0
0x25421  ldc.i4.1
0x25422  call     instance void Microsoft.Crm.Application.Menus.AppMenuBar::Execute(bool showToolBar)
0x25427  ldarg.0
0x25428  ldfld    bool Microsoft.Crm.Application.Menus.AppViewerMenuBar::_isRestrictedMode
0x2542d  brtrue   loc_25551
0x25432  ldarg.0
0x25433  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x25438  ldarg.0
0x25439  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2543e  ldstr    aMenuLabelFile// "Menu_Label_File"
0x25443  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25448  ldstr    aFile// "file"
0x2544d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::CreateMenu(string, string)
0x25452  stloc.0
0x25453  ldloc.0
0x25454  ldarg.0
0x25455  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2545a  ldstr    aMenuitemLabelP// "MenuItem_Label_Print"
0x2545f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25464  ldstr    aPrint// "Print();"
0x25469  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x2546e  pop
0x2546f  ldloc.0
0x25470  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x25475  ldloc.0
0x25476  ldarg.0
0x25477  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2547c  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x25481  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25486  ldstr    aClosewindow// "closeWindow();"
0x2548b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x25490  pop
0x25491  ldarg.0
0x25492  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x25497  ldloc.0
0x25498  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddMenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu)
0x2549d  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::.ctor()
0x254a2  stloc.1
0x254a3  ldloc.1
0x254a4  ldstr    aAction// "action"
0x254a9  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x254ae  ldloc.1
0x254af  ldstr    aImgsMnuActions// "/_imgs/mnu_actions.gif"
0x254b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x254b9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x254be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x254c3  ldloc.1
0x254c4  ldarg.0
0x254c5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x254ca  ldstr    aMenuLabelActio// "Menu_Label_Actions"
0x254cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x254d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x254d9  ldloc.1
0x254da  ldloc.1
0x254db  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x254e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x254e5  ldloc.1
0x254e6  ldc.i4.1
0x254e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::set_DownArrow(bool)
0x254ec  ldloc.1
0x254ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarPopup::get_PopupMenu()
0x254f2  stloc.2
0x254f3  ldloc.2
0x254f4  ldarg.0
0x254f5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x254fa  ldstr    aMenuLabelShowc// "Menu_Label_ShowComments"
0x254ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25504  ldstr    aShowcomments// "ShowComments();"
0x25509  ldnull
0x2550a  ldstr    aMnushowcomment// "mnuShowComments"
0x2550f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri, string)
0x25514  pop
0x25515  ldarg.0
0x25516  call     instance bool Microsoft.Crm.Application.Menus.AppViewerMenuBar::get_ShowEmailButton()
0x2551b  brfalse.s loc_2553F
0x2551d  ldloc.2
0x2551e  ldarg.0
0x2551f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x25524  ldstr    aMenuLabelEmail// "Menu_Label_EmailKB"
0x25529  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2552e  ldstr    aEmailarticle// "EmailArticle();"
0x25533  ldnull
0x25534  ldstr    aMnuemailarticl// "mnuEmailArticle"
0x25539  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri, string)
0x2553e  pop
0x2553f  ldarg.0
0x25540  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x25545  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x2554a  ldloc.1
0x2554b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x25550  pop
0x25551  ldarg.0
0x25552  ldfld    bool Microsoft.Crm.Application.Menus.AppViewerMenuBar::_isRestrictedMode
0x25557  brtrue   loc_25607
0x2555c  ldarg.0
0x2555d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x25562  ldarg.0
0x25563  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x25568  ldstr    aButtonLabelPri// "Button_Label_Print"
0x2556d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25572  ldstr    aPrint// "Print();"
0x25577  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x2557c  ldc.i4.1
0x2557d  newarr   [mscorlib]System.Char
0x25582  dup
0x25583  ldc.i4.0
0x25584  ldc.i4.s 0x2F
0x25586  stelem.i2
0x25587  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x2558c  ldstr    aImgsIco16Print// "/_imgs/ico/16_print.gif"
0x25591  call     string [mscorlib]System.String::Concat(string, string)
0x25596  ldarg.0
0x25597  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2559c  ldstr    aMenuitemToolti// "MenuItem_ToolTip_Print"
0x255a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x255a6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x255ab  pop
0x255ac  ldarg.0
0x255ad  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x255b2  ldarg.0
0x255b3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x255b8  ldstr    aButtonLabelClo// "Button_Label_Close"
0x255bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x255c2  ldstr    aClosewindow// "closeWindow();"
0x255c7  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x255cc  ldc.i4.1
0x255cd  newarr   [mscorlib]System.Char
0x255d2  dup
0x255d3  ldc.i4.0
0x255d4  ldc.i4.s 0x2F
0x255d6  stelem.i2
0x255d7  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x255dc  ldstr    aImgsIco16Close// "/_imgs/ico/16_close.gif"
0x255e1  call     string [mscorlib]System.String::Concat(string, string)
0x255e6  ldarg.0
0x255e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x255ec  ldstr    aMenuitemLabelC// "MenuItem_Label_Close"
0x255f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x255f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x255fb  pop
0x255fc  ldarg.0
0x255fd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x25602  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x25607  ldarg.0
0x25608  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x2560d  ldarg.0
0x2560e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x25613  ldstr    aMenuLabelShowc// "Menu_Label_ShowComments"
0x25618  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2561d  ldstr    aShowcomments// "ShowComments();"
0x25622  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x25627  ldc.i4.1
0x25628  newarr   [mscorlib]System.Char
0x2562d  dup
0x2562e  ldc.i4.0
0x2562f  ldc.i4.s 0x2F
0x25631  stelem.i2
0x25632  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x25637  ldstr    aImgsIco161082G// "/_imgs/ico_16_1082.gif"
0x2563c  call     string [mscorlib]System.String::Concat(string, string)
0x25641  ldarg.0
0x25642  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x25647  ldstr    aMenuLabelShowc// "Menu_Label_ShowComments"
0x2564c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25651  ldstr    aBtnshowcomment// "btnShowComments"
0x25656  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x2565b  pop
0x2565c  ldarg.0
0x2565d  call     instance bool Microsoft.Crm.Application.Menus.AppViewerMenuBar::get_ShowEmailButton()
0x25662  brfalse.s loc_256C4
0x25664  ldarg.0
0x25665  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x2566a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x2566f  ldarg.0
0x25670  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::get_ToolBar()
0x25675  ldarg.0
0x25676  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2567b  ldstr    aMenuLabelEmail// "Menu_Label_EmailKB"
0x25680  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x25685  ldstr    aEmailarticle// "EmailArticle();"
0x2568a  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x2568f  ldc.i4.1
0x25690  newarr   [mscorlib]System.Char
0x25695  dup
0x25696  ldc.i4.0
0x25697  ldc.i4.s 0x2F
0x25699  stelem.i2
0x2569a  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x2569f  ldstr    aImgsIco16138Gi// "/_imgs/ico_16_138.gif"
0x256a4  call     string [mscorlib]System.String::Concat(string, string)
0x256a9  ldarg.0
0x256aa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x256af  ldstr    aMenuLabelEmail// "Menu_Label_EmailKB"
0x256b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x256b9  ldstr    aBtnemailarticl// "btnEmailArticle"
0x256be  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x256c3  pop
0x256c4  ldarg.0
0x256c5  ldfld    bool Microsoft.Crm.Application.Menus.AppViewerMenuBar::_isRestrictedMode
0x256ca  brtrue.s loc_256D2
0x256cc  ldarg.0
0x256cd  call     instance void Microsoft.Crm.Application.Menus.AppMenuBar::BuildHelpMenu()
0x256d2  ret
```
