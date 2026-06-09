# Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigurePrivacyDisclaimerLabel

- ea: `0xe10`
- end: `0xed2`
- name: `Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::ConfigurePrivacyDisclaimerLabel`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xee0`

## callees

- `0xe10`

## string_xrefs

- `0xe6c`: `Web.Tools.KnowledgeManagement.SettingsPage.PrivacyDisclaimerHereLink`

## pseudocode

```c

```

## disassembly

```asm
0xe10  ldarg.1
0xe11  ldstr    a0// "0"
0xe16  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe1b  brtrue.s loc_E2A
0xe1d  ldarg.1
0xe1e  ldstr    a100// "100"
0xe23  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe28  brfalse.s loc_E97
0xe2a  ldarg.0
0xe2b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimer
0xe30  ldarg.0
0xe31  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe36  ldstr    aWebToolsKnowle_15// "Web.Tools.KnowledgeManagement.SettingsP"...
0xe3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe40  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xe45  ldarg.0
0xe46  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimerConsultText
0xe4b  ldarg.0
0xe4c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe51  ldstr    aWebToolsKnowle_16// "Web.Tools.KnowledgeManagement.SettingsP"...
0xe56  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xe60  ldarg.0
0xe61  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimerHereLink
0xe66  ldarg.0
0xe67  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe6c  ldstr    aWebToolsKnowle_17// "Web.Tools.KnowledgeManagement.SettingsP"...
0xe71  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe76  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xe7b  ldarg.0
0xe7c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimerMoreInfo
0xe81  ldarg.0
0xe82  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xe87  ldstr    aWebToolsKnowle_18// "Web.Tools.KnowledgeManagement.SettingsP"...
0xe8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xe96  ret
0xe97  ldarg.0
0xe98  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimer
0xe9d  ldarg.0
0xe9e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimerConsultText
0xea3  ldarg.0
0xea4  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimerHereLink
0xea9  ldarg.0
0xeaa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI Microsoft.Crm.Web.Tools.KnowledgeManagement.SettingsFinalize::lblPrivacyDisclaimerMoreInfo
0xeaf  ldsfld   string [mscorlib]System.String::Empty
0xeb4  dup
0xeb5  stloc.2
0xeb6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xebb  ldloc.2
0xebc  dup
0xebd  stloc.1
0xebe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xec3  ldloc.1
0xec4  dup
0xec5  stloc.0
0xec6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xecb  ldloc.0
0xecc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.LabelUI::set_Text(string)
0xed1  ret
```
