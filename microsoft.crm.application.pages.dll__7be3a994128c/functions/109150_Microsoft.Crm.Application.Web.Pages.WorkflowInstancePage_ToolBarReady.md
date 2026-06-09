# Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::ToolBarReady

- ea: `0x109150`
- end: `0x109536`
- name: `Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::ToolBarReady`
- size: `998`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x109150`
- `0x109540`

## string_xrefs

- `0x1091af`: `Ready`
- `0x1091db`: `Menu_Label_Completed_AsyncOperation`
- `0x109215`: `Menu_Label_Completed_AsyncOperation`
- `0x109334`: `Menu_Label_Completed_AsyncOperation`
- `0x10936e`: `Menu_Label_Completed_AsyncOperation`
- `0x10943f`: `Menu_Label_Completed_AsyncOperation`
- `0x109479`: `Menu_Label_Completed_AsyncOperation`
- `0x109231`: `Menu_Label_Ready_AsyncOperation`
- `0x10926b`: `Menu_Label_Ready_AsyncOperation`

## pseudocode

```c

```

## disassembly

```asm
0x109150  ldc.i4   0x125C
0x109155  ldc.i4.2
0x109156  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x10915b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x109160  brtrue.s loc_109163
0x109162  ret
0x109163  ldarg.0
0x109164  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x109169  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x10916e  ldc.i4.2
0x10916f  bne.un   loc_109535
0x109174  ldarg.2
0x109175  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x10917a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x10917f  ldarg.0
0x109180  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x109185  ldstr    aStatuscode// "statuscode"
0x10918a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x10918f  unbox.any [mscorlib]System.Int32
0x109194  stloc.0
0x109195  ldarg.0
0x109196  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x10919b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_State()
0x1091a0  stloc.1
0x1091a1  ldloc.1
0x1091a2  ldstr    aSuspended// "Suspended"
0x1091a7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1091ac  brtrue.s loc_1091CF
0x1091ae  ldloc.1
0x1091af  ldstr    aReady// "Ready"
0x1091b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1091b9  brtrue   loc_109328
0x1091be  ldloc.1
0x1091bf  ldstr    aLocked// "Locked"
0x1091c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1091c9  brtrue   loc_10942B
0x1091ce  ret
0x1091cf  ldarg.2
0x1091d0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x1091d5  ldarg.0
0x1091d6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1091db  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x1091e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1091e5  ldarg.0
0x1091e6  ldstr    aAsyncoperation_4// "asyncOperationCancel"
0x1091eb  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x1091f0  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1091f5  ldc.i4.1
0x1091f6  newarr   [mscorlib]System.Char
0x1091fb  dup
0x1091fc  ldc.i4.0
0x1091fd  ldc.i4.s 0x2F
0x1091ff  stelem.i2
0x109200  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x109205  ldstr    aImgsIco16Cance// "/_imgs/ico/16_cancelsystemjob.gif"
0x10920a  call     string [mscorlib]System.String::Concat(string, string)
0x10920f  ldarg.0
0x109210  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109215  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x10921a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10921f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x109224  pop
0x109225  ldarg.2
0x109226  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x10922b  ldarg.0
0x10922c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109231  ldstr    aMenuLabelReady// "Menu_Label_Ready_AsyncOperation"
0x109236  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10923b  ldarg.0
0x10923c  ldstr    aAsyncoperation_5// "asyncOperationResume"
0x109241  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x109246  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x10924b  ldc.i4.1
0x10924c  newarr   [mscorlib]System.Char
0x109251  dup
0x109252  ldc.i4.0
0x109253  ldc.i4.s 0x2F
0x109255  stelem.i2
0x109256  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x10925b  ldstr    aImgsIco16Resum// "/_imgs/ico/16_resumesystemjob.gif"
0x109260  call     string [mscorlib]System.String::Concat(string, string)
0x109265  ldarg.0
0x109266  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10926b  ldstr    aMenuLabelReady// "Menu_Label_Ready_AsyncOperation"
0x109270  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109275  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x10927a  pop
0x10927b  ldarg.2
0x10927c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x109281  ldarg.0
0x109282  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109287  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x10928c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109291  ldarg.0
0x109292  ldstr    aAsyncoperation_6// "asyncOperationPostpone"
0x109297  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x10929c  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1092a1  ldc.i4.1
0x1092a2  newarr   [mscorlib]System.Char
0x1092a7  dup
0x1092a8  ldc.i4.0
0x1092a9  ldc.i4.s 0x2F
0x1092ab  stelem.i2
0x1092ac  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1092b1  ldstr    aImgsIco16Postp// "/_imgs/ico/16_postponesystemjob.gif"
0x1092b6  call     string [mscorlib]System.String::Concat(string, string)
0x1092bb  ldarg.0
0x1092bc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1092c1  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x1092c6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1092cb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x1092d0  pop
0x1092d1  ldarg.2
0x1092d2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x1092d7  ldarg.0
0x1092d8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1092dd  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x1092e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1092e7  ldarg.0
0x1092e8  ldstr    aAsyncoperation_7// "asyncOperationPause"
0x1092ed  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x1092f2  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1092f7  ldc.i4.1
0x1092f8  newarr   [mscorlib]System.Char
0x1092fd  dup
0x1092fe  ldc.i4.0
0x1092ff  ldc.i4.s 0x2F
0x109301  stelem.i2
0x109302  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x109307  ldstr    aImgsIco16Pause// "/_imgs/ico/16_pausesystemjob.gif"
0x10930c  call     string [mscorlib]System.String::Concat(string, string)
0x109311  ldarg.0
0x109312  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109317  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x10931c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109321  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x109326  pop
0x109327  ret
0x109328  ldarg.2
0x109329  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x10932e  ldarg.0
0x10932f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109334  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x109339  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10933e  ldarg.0
0x10933f  ldstr    aAsyncoperation_4// "asyncOperationCancel"
0x109344  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x109349  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x10934e  ldc.i4.1
0x10934f  newarr   [mscorlib]System.Char
0x109354  dup
0x109355  ldc.i4.0
0x109356  ldc.i4.s 0x2F
0x109358  stelem.i2
0x109359  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x10935e  ldstr    aImgsIco16Cance// "/_imgs/ico/16_cancelsystemjob.gif"
0x109363  call     string [mscorlib]System.String::Concat(string, string)
0x109368  ldarg.0
0x109369  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10936e  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x109373  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109378  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x10937d  pop
0x10937e  ldarg.2
0x10937f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x109384  ldarg.0
0x109385  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10938a  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x10938f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109394  ldarg.0
0x109395  ldstr    aAsyncoperation_6// "asyncOperationPostpone"
0x10939a  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x10939f  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1093a4  ldc.i4.1
0x1093a5  newarr   [mscorlib]System.Char
0x1093aa  dup
0x1093ab  ldc.i4.0
0x1093ac  ldc.i4.s 0x2F
0x1093ae  stelem.i2
0x1093af  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1093b4  ldstr    aImgsIco16Postp// "/_imgs/ico/16_postponesystemjob.gif"
0x1093b9  call     string [mscorlib]System.String::Concat(string, string)
0x1093be  ldarg.0
0x1093bf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1093c4  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x1093c9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1093ce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x1093d3  pop
0x1093d4  ldarg.2
0x1093d5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x1093da  ldarg.0
0x1093db  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1093e0  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x1093e5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1093ea  ldarg.0
0x1093eb  ldstr    aAsyncoperation_7// "asyncOperationPause"
0x1093f0  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x1093f5  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1093fa  ldc.i4.1
0x1093fb  newarr   [mscorlib]System.Char
0x109400  dup
0x109401  ldc.i4.0
0x109402  ldc.i4.s 0x2F
0x109404  stelem.i2
0x109405  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x10940a  ldstr    aImgsIco16Pause// "/_imgs/ico/16_pausesystemjob.gif"
0x10940f  call     string [mscorlib]System.String::Concat(string, string)
0x109414  ldarg.0
0x109415  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10941a  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x10941f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109424  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x109429  pop
0x10942a  ret
0x10942b  ldloc.0
0x10942c  ldc.i4.s 0x14
0x10942e  bne.un   loc_109535
0x109433  ldarg.2
0x109434  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x109439  ldarg.0
0x10943a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10943f  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x109444  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109449  ldarg.0
0x10944a  ldstr    aAsyncoperation_4// "asyncOperationCancel"
0x10944f  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x109454  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x109459  ldc.i4.1
0x10945a  newarr   [mscorlib]System.Char
0x10945f  dup
0x109460  ldc.i4.0
0x109461  ldc.i4.s 0x2F
0x109463  stelem.i2
0x109464  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x109469  ldstr    aImgsIco16Cance// "/_imgs/ico/16_cancelsystemjob.gif"
0x10946e  call     string [mscorlib]System.String::Concat(string, string)
0x109473  ldarg.0
0x109474  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109479  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x10947e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x109483  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x109488  pop
0x109489  ldarg.2
0x10948a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x10948f  ldarg.0
0x109490  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109495  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x10949a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10949f  ldarg.0
0x1094a0  ldstr    aAsyncoperation_6// "asyncOperationPostpone"
0x1094a5  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x1094aa  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1094af  ldc.i4.1
0x1094b0  newarr   [mscorlib]System.Char
0x1094b5  dup
0x1094b6  ldc.i4.0
0x1094b7  ldc.i4.s 0x2F
0x1094b9  stelem.i2
0x1094ba  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1094bf  ldstr    aImgsIco16Postp// "/_imgs/ico/16_postponesystemjob.gif"
0x1094c4  call     string [mscorlib]System.String::Concat(string, string)
0x1094c9  ldarg.0
0x1094ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1094cf  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x1094d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1094d9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x1094de  pop
0x1094df  ldarg.2
0x1094e0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuBar()
0x1094e5  ldarg.0
0x1094e6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1094eb  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x1094f0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1094f5  ldarg.0
0x1094f6  ldstr    aAsyncoperation_7// "asyncOperationPause"
0x1094fb  call     instance string Microsoft.Crm.Application.Web.Pages.WorkflowInstancePage::WorkflowAction(string action)
0x109500  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x109505  ldc.i4.1
0x109506  newarr   [mscorlib]System.Char
0x10950b  dup
0x10950c  ldc.i4.0
0x10950d  ldc.i4.s 0x2F
0x10950f  stelem.i2
0x109510  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x109515  ldstr    aImgsIco16Pause// "/_imgs/ico/16_pausesystemjob.gif"
0x10951a  call     string [mscorlib]System.String::Concat(string, string)
0x10951f  ldarg.0
0x109520  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x109525  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x10952a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10952f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string)
0x109534  pop
0x109535  ret
```
