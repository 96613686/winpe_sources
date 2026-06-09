# Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::SetTitle

- ea: `0x1710`
- end: `0x17aa`
- name: `Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::SetTitle`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x12f0`

## callees

- `0x1710`

## pseudocode

```c

```

## disassembly

```asm
0x1710  ldarg.1
0x1711  ldstr    aAdd// "add"
0x1716  call     bool [mscorlib]System.String::op_Equality(string, string)
0x171b  brtrue.s loc_1739
0x171d  ldarg.1
0x171e  ldstr    aEditroot// "editroot"
0x1723  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1728  brtrue.s loc_1766
0x172a  ldarg.1
0x172b  ldstr    aEditnested// "editnested"
0x1730  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1735  brtrue.s loc_1766
0x1737  br.s     loc_1793
0x1739  ldarg.0
0x173a  ldarg.0
0x173b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1740  ldstr    aDialogAddResou// "Dialog_Add_Resource_Selection_Title"
0x1745  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x174a  stfld    string Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::dialogTitle
0x174f  ldarg.0
0x1750  ldarg.0
0x1751  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1756  ldstr    aDialogAddResou_0// "Dialog_Add_Resource_Selection_Descripti"...
0x175b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1760  stfld    string Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::dialogDescription
0x1765  ret
0x1766  ldarg.0
0x1767  ldarg.0
0x1768  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x176d  ldstr    aDialogEditReso_0// "Dialog_Edit_Resource_Selection_Title"
0x1772  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1777  stfld    string Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::dialogTitle
0x177c  ldarg.0
0x177d  ldarg.0
0x177e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1783  ldstr    aDialogEditReso_1// "Dialog_Edit_Resource_Selection_Descript"...
0x1788  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x178d  stfld    string Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::dialogDescription
0x1792  ret
0x1793  ldarg.0
0x1794  ldarg.0
0x1795  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x179a  ldstr    aDialogInvalidR// "Dialog_Invalid_Resource_Selection_Title"
0x179f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x17a4  stfld    string Microsoft.Crm.Service.SM.ResourceSpecifications.ResourceRulePage::dialogTitle
0x17a9  ret
```
