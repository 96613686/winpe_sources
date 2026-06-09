# Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::ConfigureMenus

- ea: `0xc9570`
- end: `0xc97ee`
- name: `Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::ConfigureMenus`
- size: `638`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xc9570`

## string_xrefs

- `0xc95bf`: `TaskBox_Title_CommonTasks`
- `0xc96b6`: `Task_Config_Sort`
- `0xc96d0`: `Tooltip_Config_Sort`
- `0xc9597`: `CustomReporting.AdHocWizard.TableLayoutPage.MoveRight`
- `0xc95ad`: `CustomReporting.AdHocWizard.TableLayoutPage.MoveRight`
- `0xc959e`: `CustomReporting.AdHocWizard.TableLayoutPage.MoveLeft`
- `0xc95a6`: `CustomReporting.AdHocWizard.TableLayoutPage.MoveLeft`
- `0xc95d5`: `<table style="text-align: center; padding-top: 5px;" align="center"><col width="23" /><col width="23" /><col width="23" /><tr><td colspan="3"><a href="javascript:move(DIRECTION_UP)">`
- `0xc95e1`: `<img id="moveUp" src="/_imgs/btn_off_up.gif" onmouseover="src='/_imgs/btn_on_up.gif';" onmouseout="src='/_imgs/btn_off_up.gif';" alt="{0}" style="cursor: pointer;"/>`
- `0xc95ec`: `CustomReporting.AdHocWizard.TableLayoutPage.MoveUp`
- `0xc9602`: `</a></td></tr><tr><td><a href="javascript:move(DIRECTION_LEFT)">`
- `0xc960e`: `<img id="moveLeft" src="/_imgs/btn_off_left.gif" onmouseover="src='/_imgs/btn_on_left.gif';" onmouseout="src='/_imgs/btn_off_left.gif';" alt="{0}" style="cursor: pointer;{1}">`
- `0xc962c`: `</a></td><td /><td><a href="javascript:move(DIRECTION_RIGHT)">`
- `0xc9638`: `<img id="moveRight" src="/_imgs/btn_off_right.gif" onmouseover="src='/_imgs/btn_on_right.gif';" onmouseout="src='/_imgs/btn_off_right.gif';" alt="{0}" style="cursor: pointer;{1}"/>`
- `0xc9656`: `</a></td></tr><tr><td colspan="3"><a href="javascript:move(DIRECTION_DOWN)">`
- `0xc9662`: `<img id="moveDown" src="/_imgs/btn_off_down.gif" onmouseover="src='/_imgs/btn_on_down.gif';" onmouseout="src='/_imgs/btn_off_down.gif';" alt="{0}" style="cursor: pointer;"/>`
- `0xc966d`: `CustomReporting.AdHocWizard.TableLayoutPage.MoveDown`
- `0xc96c0`: `<img alt="" id="configureSorting" src="/_imgs/vieweditor/16_sort.gif">`
- `0xc96da`: `setSortTask`
- `0xc971f`: `addColumnOrGroupingTask`
- `0xc9764`: `editPropertiesTask`
- `0xc977a`: `CustomReporting.AdHocWizard.TableLayoutPage.RemoveColumnOrGrouping`
- `0xc9784`: `<img alt="" src="/_imgs/vieweditor/16_colremove.gif">`
- `0xc9789`: `removeColumnOrGrouping();`
- `0xc9794`: `CustomReporting.AdHocWizard.TableLayoutPage.RemoveColumnOrGrouping.Tooltip`
- `0xc979e`: `removeTask`
- `0xc97e3`: `setFilterTask`

## pseudocode

```c

```

## disassembly

```asm
0xc9570  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xc9575  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xc957a  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xc957f  dup
0xc9580  brtrue.s loc_C9589
0xc9582  ldsfld   string [mscorlib]System.String::Empty
0xc9587  br.s     loc_C9593
0xc9589  ldstr    aH// "h"
0xc958e  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string)
0xc9593  stloc.0
0xc9594  dup
0xc9595  brtrue.s loc_C959E
0xc9597  ldstr    aCustomreportin_68// "CustomReporting.AdHocWizard.TableLayout"...
0xc959c  br.s     loc_C95A3
0xc959e  ldstr    aCustomreportin_69// "CustomReporting.AdHocWizard.TableLayout"...
0xc95a3  stloc.1
0xc95a4  brtrue.s loc_C95AD
0xc95a6  ldstr    aCustomreportin_69// "CustomReporting.AdHocWizard.TableLayout"...
0xc95ab  br.s     loc_C95B2
0xc95ad  ldstr    aCustomreportin_68// "CustomReporting.AdHocWizard.TableLayout"...
0xc95b2  stloc.2
0xc95b3  ldarg.0
0xc95b4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc95b9  ldarg.0
0xc95ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc95bf  ldstr    aTaskboxTitleCo// "TaskBox_Title_CommonTasks"
0xc95c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc95c9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::set_Title(string)
0xc95ce  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xc95d3  stloc.3
0xc95d4  ldloc.3
0xc95d5  ldstr    aTableStyleText// "<table style=\"text-align: center; padd"...
0xc95da  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc95df  pop
0xc95e0  ldloc.3
0xc95e1  ldstr    aImgIdMoveupSrc// "<img id=\"moveUp\" src=\"/_imgs/btn_off"...
0xc95e6  ldarg.0
0xc95e7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc95ec  ldstr    aCustomreportin_70// "CustomReporting.AdHocWizard.TableLayout"...
0xc95f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc95f6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc95fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xc9600  pop
0xc9601  ldloc.3
0xc9602  ldstr    aATdTrTrTdAHref// "</a></td></tr><tr><td><a href=\"javascr"...
0xc9607  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc960c  pop
0xc960d  ldloc.3
0xc960e  ldstr    aImgIdMoveleftS// "<img id=\"moveLeft\" src=\"/_imgs/btn_o"...
0xc9613  ldarg.0
0xc9614  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9619  ldloc.2
0xc961a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc961f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc9624  ldloc.0
0xc9625  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0xc962a  pop
0xc962b  ldloc.3
0xc962c  ldstr    aATdTdTdAHrefJa// "</a></td><td /><td><a href=\"javascript"...
0xc9631  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc9636  pop
0xc9637  ldloc.3
0xc9638  ldstr    aImgIdMoveright// "<img id=\"moveRight\" src=\"/_imgs/btn_"...
0xc963d  ldarg.0
0xc963e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9643  ldloc.1
0xc9644  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9649  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc964e  ldloc.0
0xc964f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0xc9654  pop
0xc9655  ldloc.3
0xc9656  ldstr    aATdTrTrTdColsp_0// "</a></td></tr><tr><td colspan=\"3\"><a "...
0xc965b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc9660  pop
0xc9661  ldloc.3
0xc9662  ldstr    aImgIdMovedownS// "<img id=\"moveDown\" src=\"/_imgs/btn_o"...
0xc9667  ldarg.0
0xc9668  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc966d  ldstr    aCustomreportin_71// "CustomReporting.AdHocWizard.TableLayout"...
0xc9672  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9677  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0xc967c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0xc9681  pop
0xc9682  ldloc.3
0xc9683  ldstr    aATdTrTable// "</a></td></tr></table>"
0xc9688  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xc968d  pop
0xc968e  ldarg.0
0xc968f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc9694  ldloc.3
0xc9695  callvirt instance string [mscorlib]System.Object::ToString()
0xc969a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopHtml(string)
0xc969f  ldarg.0
0xc96a0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc96a5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddSpacer()
0xc96aa  ldarg.0
0xc96ab  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc96b0  ldarg.0
0xc96b1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc96b6  ldstr    aTaskConfigSort// "Task_Config_Sort"
0xc96bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc96c0  ldstr    aImgAltIdConfig// "<img alt=\"\" id=\"configureSorting\" s"...
0xc96c5  ldstr    aSetsort_0// "setSort();"
0xc96ca  ldarg.0
0xc96cb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc96d0  ldstr    aTooltipConfigS// "Tooltip_Config_Sort"
0xc96d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc96da  ldstr    aSetsorttask// "setSortTask"
0xc96df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xc96e4  ldarg.0
0xc96e5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc96ea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddSpacer()
0xc96ef  ldarg.0
0xc96f0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc96f5  ldarg.0
0xc96f6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc96fb  ldstr    aCustomreportin_72// "CustomReporting.AdHocWizard.TableLayout"...
0xc9700  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9705  ldstr    aImgAltSrcImgsV// "<img alt=\"\" src=\"/_imgs/vieweditor/1"...
0xc970a  ldstr    aAddcolumnorgro// "addColumnOrGrouping();"
0xc970f  ldarg.0
0xc9710  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9715  ldstr    aCustomreportin_73// "CustomReporting.AdHocWizard.TableLayout"...
0xc971a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc971f  ldstr    aAddcolumnorgro_0// "addColumnOrGroupingTask"
0xc9724  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xc9729  ldarg.0
0xc972a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc972f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddSpacer()
0xc9734  ldarg.0
0xc9735  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc973a  ldarg.0
0xc973b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9740  ldstr    aCustomreportin_74// "CustomReporting.AdHocWizard.TableLayout"...
0xc9745  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc974a  ldstr    aImgAltSrcImgsV_0// "<img alt=\"\" src=\"/_imgs/vieweditor/1"...
0xc974f  ldstr    aEditproperties// "editProperties();"
0xc9754  ldarg.0
0xc9755  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc975a  ldstr    aCustomreportin_75// "CustomReporting.AdHocWizard.TableLayout"...
0xc975f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9764  ldstr    aEditproperties_0// "editPropertiesTask"
0xc9769  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xc976e  ldarg.0
0xc976f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc9774  ldarg.0
0xc9775  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc977a  ldstr    aCustomreportin_76// "CustomReporting.AdHocWizard.TableLayout"...
0xc977f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc9784  ldstr    aImgAltSrcImgsV_1// "<img alt=\"\" src=\"/_imgs/vieweditor/1"...
0xc9789  ldstr    aRemovecolumnor// "removeColumnOrGrouping();"
0xc978e  ldarg.0
0xc978f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc9794  ldstr    aCustomreportin_77// "CustomReporting.AdHocWizard.TableLayout"...
0xc9799  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc979e  ldstr    aRemovetask// "removeTask"
0xc97a3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xc97a8  ldarg.0
0xc97a9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc97ae  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddSpacer()
0xc97b3  ldarg.0
0xc97b4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox Microsoft.Crm.Web.Reporting.AdHocWizard.TableLayoutPage::taskBox
0xc97b9  ldarg.0
0xc97ba  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc97bf  ldstr    aCustomreportin_78// "CustomReporting.AdHocWizard.TableLayout"...
0xc97c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc97c9  ldstr    aImgAltSrcImgsR// "<img alt=\"\" src=\"/_imgs/reportwizard"...
0xc97ce  ldstr    aSetfilter// "setFilter();"
0xc97d3  ldarg.0
0xc97d4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xc97d9  ldstr    aCustomreportin_79// "CustomReporting.AdHocWizard.TableLayout"...
0xc97de  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc97e3  ldstr    aSetfiltertask// "setFilterTask"
0xc97e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TaskBox::AddTopTask(string, string, string, string, string)
0xc97ed  ret
```
