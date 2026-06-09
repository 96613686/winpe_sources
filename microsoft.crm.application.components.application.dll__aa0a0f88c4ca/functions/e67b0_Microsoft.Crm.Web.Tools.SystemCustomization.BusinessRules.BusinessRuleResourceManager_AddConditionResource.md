# Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRuleResourceManager::AddConditionResource

- ea: `0xe67b0`
- end: `0xe6b11`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.BusinessRuleResourceManager::AddConditionResource`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4b9c0`

## string_xrefs

- `0xe6893`: `Web._controls.listedit.buttons.Delete`
- `0xe67b1`: `LOCID_PBLCONFIRM_DELETE`
- `0xe67bb`: `SystemCustomization.BusinessRules.Confirm.DeleteSectionTitle`
- `0xe6802`: `LOCID_PBLCONFIRM_DELETEBODY`
- `0xe680c`: `SystemCustomization.BusinessRules.Confirm.DeleteSectionBody`
- `0xe6889`: `LOCID_DELETE_BUTTON`
- `0xe6aa5`: `LOCID_PBLEXPRESSION_COMMA`
- `0xe6aaf`: `SystemCustomization.BusinessRules.Comma.Separator`
- `0xe67cc`: `LOCID_PBL_DELETE_ERROR_MESSAGE`
- `0xe67d6`: `Dlg_Delete_Branching_Rule`

## pseudocode

```c

```

## disassembly

```asm
0xe67b0  ldarg.0
0xe67b1  ldstr    aLocidPblconfir// "LOCID_PBLCONFIRM_DELETE"
0xe67b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe67bb  ldstr    aSystemcustomiz_42// "SystemCustomization.BusinessRules.Confi"...
0xe67c0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe67c5  ldc.i4.0
0xe67c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe67cb  ldarg.0
0xe67cc  ldstr    aLocidPblDelete// "LOCID_PBL_DELETE_ERROR_MESSAGE"
0xe67d1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe67d6  ldstr    aDlgDeleteBranc// "Dlg_Delete_Branching_Rule"
0xe67db  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe67e0  ldc.i4.0
0xe67e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe67e6  ldarg.0
0xe67e7  ldstr    aLocidPblConvtT// "LOCID_PBL_CONVT_TO_ELSE_BRANCH"
0xe67ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe67f1  ldstr    aDlgConvertToEl// "Dlg_convert_to_else_Branch_Rule"
0xe67f6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe67fb  ldc.i4.0
0xe67fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6801  ldarg.0
0xe6802  ldstr    aLocidPblconfir_0// "LOCID_PBLCONFIRM_DELETEBODY"
0xe6807  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe680c  ldstr    aSystemcustomiz_43// "SystemCustomization.BusinessRules.Confi"...
0xe6811  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6816  ldc.i4.0
0xe6817  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe681c  ldarg.0
0xe681d  ldstr    aLocidPbldialog// "LOCID_PBLDIALOG_OK"
0xe6822  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6827  ldstr    aButtonLabelOk// "Button_Label_OK"
0xe682c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6831  ldc.i4.0
0xe6832  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6837  ldarg.0
0xe6838  ldstr    aLocidPblerrorT// "LOCID_PBLERROR_TITLE"
0xe683d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6842  ldstr    aSystemcustomiz_44// "SystemCustomization.BusinessRules.Error"...
0xe6847  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe684c  ldc.i4.0
0xe684d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6852  ldarg.0
0xe6853  ldstr    aLocidPbldialog_0// "LOCID_PBLDIALOG_CANCEL"
0xe6858  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe685d  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xe6862  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6867  ldc.i4.0
0xe6868  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe686d  ldarg.0
0xe686e  ldstr    aLocidCalcfield_2// "LOCID_CALCFIELD_CONDITION_TIP"
0xe6873  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6878  ldstr    aSystemcustomiz_63// "SystemCustomization.BusinessRules.AddCo"...
0xe687d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6882  ldc.i4.0
0xe6883  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6888  ldarg.0
0xe6889  ldstr    aLocidDeleteBut// "LOCID_DELETE_BUTTON"
0xe688e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6893  ldstr    aWebControlsLis_3// "Web._controls.listedit.buttons.Delete"
0xe6898  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe689d  ldc.i4.0
0xe689e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe68a3  ldarg.0
0xe68a4  ldstr    aLocidPblexpres// "LOCID_PBLEXPRESSION_OPERATOR"
0xe68a9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe68ae  ldstr    aSystemcustomiz_75// "SystemCustomization.BusinessRules.Expre"...
0xe68b3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe68b8  ldc.i4.0
0xe68b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe68be  ldarg.0
0xe68bf  ldstr    aLocidPblexpres_0// "LOCID_PBLEXPRESSION_TYPE"
0xe68c4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe68c9  ldstr    aSystemcustomiz_76// "SystemCustomization.BusinessRules.Expre"...
0xe68ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe68d3  ldc.i4.0
0xe68d4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe68d9  ldarg.0
0xe68da  ldstr    aLocidPblexpres_1// "LOCID_PBLEXPRESSION_ALLOPERATOR"
0xe68df  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe68e4  ldstr    aSystemcustomiz_77// "SystemCustomization.BusinessRules.Expre"...
0xe68e9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe68ee  ldc.i4.0
0xe68ef  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe68f4  ldarg.0
0xe68f5  ldstr    aLocidPblexpres_2// "LOCID_PBLEXPRESSION_ALLTYPE"
0xe68fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe68ff  ldstr    aSystemcustomiz_78// "SystemCustomization.BusinessRules.Expre"...
0xe6904  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6909  ldc.i4.0
0xe690a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe690f  ldarg.0
0xe6910  ldstr    aLocidPblexpres_3// "LOCID_PBLEXPRESSION_OPERANDLABEL"
0xe6915  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe691a  ldstr    aSystemcustomiz_79// "SystemCustomization.BusinessRules.Expre"...
0xe691f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6924  ldc.i4.0
0xe6925  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe692a  ldarg.0
0xe692b  ldstr    aLocidPblexpres_4// "LOCID_PBLEXPRESSION_ARITFORMAT"
0xe6930  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6935  ldstr    aSystemcustomiz_80// "SystemCustomization.BusinessRules.Arith"...
0xe693a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe693f  ldc.i4.0
0xe6940  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6945  ldarg.0
0xe6946  ldstr    aLocidPblexpres_5// "LOCID_PBLEXPRESSION_IF"
0xe694b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6950  ldstr    aSystemcustomiz_81// "SystemCustomization.BusinessRules.Expre"...
0xe6955  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe695a  ldc.i4.0
0xe695b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6960  ldarg.0
0xe6961  ldstr    aLocidPblexpres_14// "LOCID_PBLEXPRESSION_ELSEIF"
0xe6966  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe696b  ldstr    aSystemcustomiz_149// "SystemCustomization.BusinessRules.Expre"...
0xe6970  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6975  ldc.i4.0
0xe6976  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe697b  ldarg.0
0xe697c  ldstr    aLocidPblexpres_15// "LOCID_PBLEXPRESSION_ELSE"
0xe6981  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6986  ldstr    aSystemcustomiz_150// "SystemCustomization.BusinessRules.Expre"...
0xe698b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6990  ldc.i4.0
0xe6991  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6996  ldarg.0
0xe6997  ldstr    aLocidPblexpres_16// "LOCID_PBLEXPRESSION_ELSEDISPLAY"
0xe699c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe69a1  ldstr    aSystemcustomiz_151// "SystemCustomization.BusinessRules.Expre"...
0xe69a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe69ab  ldc.i4.0
0xe69ac  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe69b1  ldarg.0
0xe69b2  ldstr    aLocidPblexpres_6// "LOCID_PBLEXPRESSION_AND"
0xe69b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe69bc  ldstr    aSystemcustomiz_82// "SystemCustomization.BusinessRules.Expre"...
0xe69c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe69c6  ldc.i4.0
0xe69c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe69cc  ldarg.0
0xe69cd  ldstr    aLocidPblexpres_7// "LOCID_PBLEXPRESSION_OR"
0xe69d2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe69d7  ldstr    aSystemcustomiz_83// "SystemCustomization.BusinessRules.Expre"...
0xe69dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe69e1  ldc.i4.0
0xe69e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe69e7  ldarg.0
0xe69e8  ldstr    aLocidPblexpres_8// "LOCID_PBLEXPRESSION_ANDOR"
0xe69ed  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe69f2  ldstr    aSystemcustomiz_84// "SystemCustomization.BusinessRules.Expre"...
0xe69f7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe69fc  ldc.i4.0
0xe69fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6a02  ldarg.0
0xe6a03  ldstr    aLocidPblexpres_9// "LOCID_PBLEXPRESSION_FIELDTYPE"
0xe6a08  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6a0d  ldstr    aSystemcustomiz_85// "SystemCustomization.BusinessRules.Opera"...
0xe6a12  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6a17  ldc.i4.0
0xe6a18  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6a1d  ldarg.0
0xe6a1e  ldstr    aLocidPblexpres_10// "LOCID_PBLEXPRESSION_VALUETYPE"
0xe6a23  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6a28  ldstr    aSystemcustomiz_86// "SystemCustomization.BusinessRules.Opera"...
0xe6a2d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6a32  ldc.i4.0
0xe6a33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6a38  ldarg.0
0xe6a39  ldstr    aLocidPblexpres_11// "LOCID_PBLEXPRESSION_DAYSVALUE"
0xe6a3e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6a43  ldstr    aSystemcustomiz_87// "SystemCustomization.BusinessRules.Expre"...
0xe6a48  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6a4d  ldc.i4.0
0xe6a4e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6a53  ldarg.0
0xe6a54  ldstr    aLocidBusinessr_5// "LOCID_BUSINESSRULE_DISCRDTOOLTIP"
0xe6a59  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6a5e  ldstr    aSystemcustomiz_49// "SystemCustomization.BusinessRules.Disca"...
0xe6a63  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6a68  ldc.i4.0
0xe6a69  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6a6e  ldarg.0
0xe6a6f  ldstr    aLocidBusinessr_4// "LOCID_BUSINESSRULE_DONETOOLTIP"
0xe6a74  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6a79  ldstr    aSystemcustomiz_48// "SystemCustomization.BusinessRules.DoneB"...
0xe6a7e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6a83  ldc.i4.0
0xe6a84  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6a89  ldarg.0
0xe6a8a  ldstr    aLocidPblexpres_17// "LOCID_PBLEXPRESSION_INVALID"
0xe6a8f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6a94  ldstr    aSystemcustomiz_152// "SystemCustomization.BusinessRules.Expre"...
0xe6a99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6a9e  ldc.i4.0
0xe6a9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6aa4  ldarg.0
0xe6aa5  ldstr    aLocidPblexpres_13// "LOCID_PBLEXPRESSION_COMMA"
0xe6aaa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6aaf  ldstr    aSystemcustomiz_89// "SystemCustomization.BusinessRules.Comma"...
0xe6ab4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6ab9  ldc.i4.0
0xe6aba  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6abf  ldarg.0
0xe6ac0  ldstr    aLocidBusinessr// "LOCID_BUSINESSRULE_FIELDLABEL"
0xe6ac5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6aca  ldstr    aBusinessruleEd// "BusinessRule.Editor.Field"
0xe6acf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6ad4  ldc.i4.0
0xe6ad5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6ada  ldarg.0
0xe6adb  ldstr    aLocidBusinessr_11// "LOCID_BUSINESSRULE_SOURCELABEL"
0xe6ae0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6ae5  ldstr    aSystemcustomiz_71// "SystemCustomization.BusinessRules.Sourc"...
0xe6aea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6aef  ldc.i4.0
0xe6af0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6af5  ldarg.0
0xe6af6  ldstr    aLocidSaveerror_0// "LOCID_SAVEERROR_VALIDOPERATOR"
0xe6afb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe6b00  ldstr    aSystemcustomiz_47// "SystemCustomization.BusinessRules.SaveE"...
0xe6b05  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe6b0a  ldc.i4.0
0xe6b0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe6b10  ret
```
