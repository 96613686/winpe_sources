# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.ManageBusinessRuleView::SetResourceVars

- ea: `0xeff30`
- end: `0xf047f`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.ManageBusinessRuleView::SetResourceVars`
- size: `1359`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xe3a60`
- `0xe42e0`

## string_xrefs

- `0xf00e6`: `SystemCustomization.BusinessRules.SetDisplayModeReadOnly`
- `0xf00c6`: `SystemCustomization.BusinessRules.SetDisplayModeReadWrite`
- `0xf0226`: `SystemCustomization.BusinessRules.SetDefaultValueReadFormat`
- `0xf0066`: `SystemCustomization.BusinessRules.ActionSetReadWrite`
- `0xf005c`: `LOCID_EDITORACTION_SETREADWRITE`
- `0xf009c`: `LOCID_BUSINESSRULE_SETREADWRITE`
- `0xf00a6`: `SystemCustomization.BusinessRules.SetDisplayModeSetReadWrite`
- `0xf00bc`: `LOCID_BUSINESSRULE_READWRITE`
- `0xf00dc`: `LOCID_BUSINESSRULE_READ_ONLY`
- `0xf0464`: `LOCID_BUSINESSRULE_STAGEDELETED`
- `0xf046e`: `SystemCustomization.BusinessRules.SaveError.StageDeleted`

## pseudocode

```c

```

## disassembly

```asm
0xeff30  ldarg.0
0xeff31  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::SetResourceVars()
0xeff36  ldarg.0
0xeff37  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xeff3c  ldstr    aLocidBusinessr_12// "LOCID_BUSINESSRULE_NAMESTRING"
0xeff41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xeff46  ldstr    aSystemcustomiz_177// "SystemCustomization.BusinessRules.Busin"...
0xeff4b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeff50  ldc.i4.0
0xeff51  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeff56  ldarg.0
0xeff57  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xeff5c  ldstr    aLocidBusinessr_13// "LOCID_BUSINESSRULE_NAMEWATERMRK"
0xeff61  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xeff66  ldstr    aSystemcustomiz_167// "SystemCustomization.BusinessRules.Busin"...
0xeff6b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeff70  ldc.i4.0
0xeff71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeff76  ldarg.0
0xeff77  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xeff7c  ldstr    aLocidBusinessr_14// "LOCID_BUSINESSRULE_DESCRIPTION"
0xeff81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xeff86  ldstr    aSystemcustomiz_168// "SystemCustomization.BusinessRules.Secti"...
0xeff8b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeff90  ldc.i4.0
0xeff91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeff96  ldarg.0
0xeff97  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xeff9c  ldstr    aLocidBrRulenam// "LOCID_BR_RULENAME_PLACEHOLDER"
0xeffa1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xeffa6  ldstr    aSystemcustomiz_204// "SystemCustomization.BusinessRules.Busin"...
0xeffab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeffb0  ldc.i4.0
0xeffb1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeffb6  ldarg.0
0xeffb7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xeffbc  ldstr    aLocidBrDescrip// "LOCID_BR_DESCRIPTION_PLACEHOLDER"
0xeffc1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xeffc6  ldstr    aSystemcustomiz_205// "SystemCustomization.BusinessRules.Busin"...
0xeffcb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xeffd0  ldc.i4.0
0xeffd1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xeffd6  ldarg.0
0xeffd7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xeffdc  ldstr    aLocidEditoract// "LOCID_EDITORACTION_SHOWMESSAGE"
0xeffe1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xeffe6  ldstr    aSystemcustomiz_180// "SystemCustomization.BusinessRules.Actio"...
0xeffeb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xefff0  ldc.i4.0
0xefff1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xefff6  ldarg.0
0xefff7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xefffc  ldstr    aLocidEditoract_0// "LOCID_EDITORACTION_SETFIELD"
0xf0001  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0006  ldstr    aSystemcustomiz_182// "SystemCustomization.BusinessRules.Actio"...
0xf000b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0010  ldc.i4.0
0xf0011  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0016  ldarg.0
0xf0017  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf001c  ldstr    aLocidEditoract_1// "LOCID_EDITORACTION_SETBUSINESS"
0xf0021  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0026  ldstr    aSystemcustomiz_184// "SystemCustomization.BusinessRules.Actio"...
0xf002b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0030  ldc.i4.0
0xf0031  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0036  ldarg.0
0xf0037  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf003c  ldstr    aLocidEditoract_2// "LOCID_EDITORACTION_SETVISIBILITY"
0xf0041  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0046  ldstr    aSystemcustomiz_186// "SystemCustomization.BusinessRules.Actio"...
0xf004b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0050  ldc.i4.0
0xf0051  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0056  ldarg.0
0xf0057  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf005c  ldstr    aLocidEditoract_3// "LOCID_EDITORACTION_SETREADWRITE"
0xf0061  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0066  ldstr    aSystemcustomiz_190// "SystemCustomization.BusinessRules.Actio"...
0xf006b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0070  ldc.i4.0
0xf0071  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0076  ldarg.0
0xf0077  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf007c  ldstr    aLocidEditoract_4// "LOCID_EDITORACTION_SETDFLTVAL"
0xf0081  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0086  ldstr    aSystemcustomiz_188// "SystemCustomization.BusinessRules.Actio"...
0xf008b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0090  ldc.i4.0
0xf0091  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0096  ldarg.0
0xf0097  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf009c  ldstr    aLocidBusinessr_15// "LOCID_BUSINESSRULE_SETREADWRITE"
0xf00a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf00a6  ldstr    aSystemcustomiz_206// "SystemCustomization.BusinessRules.SetDi"...
0xf00ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf00b0  ldc.i4.0
0xf00b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf00b6  ldarg.0
0xf00b7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf00bc  ldstr    aLocidBusinessr_16// "LOCID_BUSINESSRULE_READWRITE"
0xf00c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf00c6  ldstr    aSystemcustomiz_155// "SystemCustomization.BusinessRules.SetDi"...
0xf00cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf00d0  ldc.i4.0
0xf00d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf00d6  ldarg.0
0xf00d7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf00dc  ldstr    aLocidBusinessr_17// "LOCID_BUSINESSRULE_READ_ONLY"
0xf00e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf00e6  ldstr    aSystemcustomiz_154// "SystemCustomization.BusinessRules.SetDi"...
0xf00eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf00f0  ldc.i4.0
0xf00f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf00f6  ldarg.0
0xf00f7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf00fc  ldstr    aLocidBusinessr_18// "LOCID_BUSINESSRULE_SETTO"
0xf0101  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0106  ldstr    aSystemcustomiz_169// "SystemCustomization.BusinessRules.SetDi"...
0xf010b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0110  ldc.i4.0
0xf0111  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0116  ldarg.0
0xf0117  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf011c  ldstr    aLocidBusinessr_19// "LOCID_BUSINESSRULE_SETSHOWHIDE"
0xf0121  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0126  ldstr    aSystemcustomiz_207// "SystemCustomization.BusinessRules.SetVi"...
0xf012b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0130  ldc.i4.0
0xf0131  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0136  ldarg.0
0xf0137  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf013c  ldstr    aLocidBusinessr_20// "LOCID_BUSINESSRULE_SHOW"
0xf0141  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0146  ldstr    aSystemcustomiz_156// "SystemCustomization.BusinessRules.SetVi"...
0xf014b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0150  ldc.i4.0
0xf0151  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0156  ldarg.0
0xf0157  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf015c  ldstr    aLocidBusinessr_21// "LOCID_BUSINESSRULE_HIDE"
0xf0161  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0166  ldstr    aSystemcustomiz_157// "SystemCustomization.BusinessRules.SetVi"...
0xf016b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0170  ldc.i4.0
0xf0171  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0176  ldarg.0
0xf0177  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf017c  ldstr    aLocidBusinessr_22// "LOCID_BUSINESSRULE_SETTOVISIBLE"
0xf0181  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0186  ldstr    aSystemcustomiz_173// "SystemCustomization.BusinessRules.SetVi"...
0xf018b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0190  ldc.i4.0
0xf0191  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0196  ldarg.0
0xf0197  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf019c  ldstr    aLocidBusinessr_23// "LOCID_BUSINESSRULE_BIZREQUIRED"
0xf01a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf01a6  ldstr    aSystemcustomiz_158// "SystemCustomization.BusinessRules.SetFi"...
0xf01ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf01b0  ldc.i4.0
0xf01b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf01b6  ldarg.0
0xf01b7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf01bc  ldstr    aLocidBusinessr_24// "LOCID_BUSINESSRULE_NOBIZREQUIRED"
0xf01c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf01c6  ldstr    aSystemcustomiz_159// "SystemCustomization.BusinessRules.SetFi"...
0xf01cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf01d0  ldc.i4.0
0xf01d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf01d6  ldarg.0
0xf01d7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf01dc  ldstr    aLocidBusinessr_25// "LOCID_BUSINESSRULE_SETAS"
0xf01e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf01e6  ldstr    aSystemcustomiz_172// "SystemCustomization.BusinessRules.SetFi"...
0xf01eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf01f0  ldc.i4.0
0xf01f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf01f6  ldarg.0
0xf01f7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf01fc  ldstr    aLocidBusinessr_26// "LOCID_BUSINESSRULE_SETREQUIRED"
0xf0201  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0206  ldstr    aSystemcustomiz_208// "SystemCustomization.BusinessRules.SetDi"...
0xf020b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0210  ldc.i4.0
0xf0211  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0216  ldarg.0
0xf0217  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf021c  ldstr    aLocidBusinessr_27// "LOCID_BUSINESSRULE_SETDFLTVALUE"
0xf0221  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0226  ldstr    aSystemcustomiz_174// "SystemCustomization.BusinessRules.SetDe"...
0xf022b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0230  ldc.i4.0
0xf0231  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0236  ldarg.0
0xf0237  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf023c  ldstr    aLocidBusinessr_28// "LOCID_BUSINESSRULE_SETDFLTHEADER"
0xf0241  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0246  ldstr    aSystemcustomiz_209// "SystemCustomization.BusinessRules.SetDe"...
0xf024b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0250  ldc.i4.0
0xf0251  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0256  ldarg.0
0xf0257  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf025c  ldstr    aLocidBusinessr_29// "LOCID_BUSINESSRULE_SETMESSAGE"
0xf0261  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0266  ldstr    aSystemcustomiz_210// "SystemCustomization.BusinessRules.SetMe"...
0xf026b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0270  ldc.i4.0
0xf0271  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0276  ldarg.0
0xf0277  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf027c  ldstr    aLocidBusinessr_30// "LOCID_BUSINESSRULE_MESSAGE"
0xf0281  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf0286  ldstr    aSystemcustomiz_211// "SystemCustomization.BusinessRules.Messa"...
0xf028b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0290  ldc.i4.0
0xf0291  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf0296  ldarg.0
0xf0297  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf029c  ldstr    aLocidBusinessr_31// "LOCID_BUSINESSRULE_SETORGLCID"
0xf02a1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xf02a6  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xf02ab  stloc.0
0xf02ac  ldloca.s 0
0xf02ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf02b3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf02b8  ldc.i4.0
0xf02b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf02be  ldarg.0
0xf02bf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf02c4  ldstr    aLocidBusinessr_32// "LOCID_BUSINESSRULE_SETDISPLAYMSG"
0xf02c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf02ce  ldstr    aSystemcustomiz_170// "SystemCustomization.BusinessRules.SetMe"...
0xf02d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf02d8  ldc.i4.0
0xf02d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf02de  ldarg.0
0xf02df  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf02e4  ldstr    aLocidBusinessr_33// "LOCID_BUSINESSRULE_SCRIPTMESSAGE"
0xf02e9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf02ee  ldstr    aSystemcustomiz_171// "SystemCustomization.BusinessRules.RunSc"...
0xf02f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf02f8  ldc.i4.0
0xf02f9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf02fe  ldarg.0
0xf02ff  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf0304  ldstr    aLocidBusinessr_34// "LOCID_BUSINESSRULE_SCRIPTSOURCE"
0xf0309  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf030e  ldstr    aSystemcustomiz_212// "SystemCustomization.BusinessRules.RunSc"...
0xf0313  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0318  ldc.i4.0
0xf0319  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf031e  ldarg.0
0xf031f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf0324  ldstr    aLocidBusinessr_35// "LOCID_BUSINESSRULE_MULTIPLEELSE"
0xf0329  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf032e  ldstr    aSystemcustomiz_213// "SystemCustomization.BusinessRules.SaveE"...
0xf0333  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0338  ldc.i4.0
0xf0339  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf033e  ldarg.0
0xf033f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf0344  ldstr    aLocidSelectBpf// "LOCID_SELECT_BPF_PROCESS_FIRST"
0xf0349  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf034e  ldstr    aSelectbpfproce// "SelectBPFProcessFirst"
0xf0353  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0358  ldc.i4.0
0xf0359  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf035e  ldarg.0
0xf035f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf0364  ldstr    aLocidWhereClau// "LOCID_WHERE_CLAUSE"
0xf0369  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf036e  ldstr    aWhereclause_0// "WhereClause"
0xf0373  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0378  ldc.i4.0
0xf0379  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf037e  ldarg.0
0xf037f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf0384  ldstr    aLocidNoProcess// "LOCID_NO_PROCESSES_DEFINED"
0xf0389  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf038e  ldstr    aNoProcessesDef// "No_Processes_Defined"
0xf0393  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf0398  ldc.i4.0
0xf0399  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf039e  ldarg.0
0xf039f  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf03a4  ldstr    aLocidBusinessP// "LOCID_BUSINESS_PROCESS"
0xf03a9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf03ae  ldstr    aBusinessProces// "Business_Process"
0xf03b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf03b8  ldc.i4.0
0xf03b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xf03be  ldarg.0
0xf03bf  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xf03c4  ldstr    aLocidActiveSta// "LOCID_ACTIVE_STAGE"
0xf03c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xf03ce  ldstr    aActiveStage// "Active_Stage"
0xf03d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xf03d8  ldc.i4.0
  ... truncated ...
```
