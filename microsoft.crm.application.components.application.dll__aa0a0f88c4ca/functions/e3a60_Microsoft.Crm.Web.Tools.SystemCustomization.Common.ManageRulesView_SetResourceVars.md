# Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::SetResourceVars

- ea: `0xe3a60`
- end: `0xe3f79`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::SetResourceVars`
- size: `1305`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0xe3940`
- `0xe5f60`
- `0xeff30`

## callees

- `0xe3ff0`
- `0xe4010`
- `0xe4080`
- `0xe4270`
- `0xe42e0`

## string_xrefs

- `0xe3aec`: `LOCID_PBLCONFIRM_DELETE`
- `0xe3af6`: `SystemCustomization.BusinessRules.Confirm.DeleteSectionTitle`
- `0xe3b0c`: `LOCID_PBLCONFIRM_DELETEBODY`
- `0xe3b16`: `SystemCustomization.BusinessRules.Confirm.DeleteSectionBody`
- `0xe3c6c`: `LOCID_PBLELSE_DELETETOOLTIP`
- `0xe3c76`: `SystemCustomization.BusinessRules.Section.Else.Delete`
- `0xe3c96`: `SystemCustomization.BusinessRules.SetAttributeValueReadFormat`
- `0xe3cb6`: `SystemCustomization.BusinessRules.ClearAttributeValueReadFormat`
- `0xe3cf6`: `SystemCustomization.BusinessRules.SetNullOperandAttributeValReadFormat`
- `0xe3eac`: `LOCID_PBLCONFIRM_DELETEELSE`
- `0xe3eb6`: `SystemCustomization.BusinessRules.Confirm.DeleteElseExpression`
- `0xe3f2c`: `LOCID_CF_ERR_NOCOMPATIBLEFIELD`
- `0xe3f36`: `SystemCustomization.CalculatedFields.Errors.NoCompatibleFieldAvailable`

## pseudocode

```c

```

## disassembly

```asm
0xe3a60  ldarg.0
0xe3a61  call     instance void Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::SetResourceForExpression()
0xe3a66  ldarg.0
0xe3a67  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3a6c  ldstr    aLocidBusinessr// "LOCID_BUSINESSRULE_FIELDLABEL"
0xe3a71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3a76  ldstr    aBusinessruleEd// "BusinessRule.Editor.Field"
0xe3a7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3a80  ldc.i4.0
0xe3a81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3a86  ldarg.0
0xe3a87  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3a8c  ldstr    aLocidBusinessr_0// "LOCID_BUSINESSRULE_SHOWFIELDS"
0xe3a91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3a96  ldstr    aBusinessruleEd_0// "BusinessRule.Editor.ShowFields"
0xe3a9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3aa0  ldc.i4.0
0xe3aa1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3aa6  ldarg.0
0xe3aa7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3aac  ldstr    aLocidBusinessr_1// "LOCID_BUSINESSRULE_FIELD"
0xe3ab1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3ab6  ldstr    aSystemcustomiz_22// "SystemCustomization.BusinessRules.Field"
0xe3abb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ac0  ldc.i4.0
0xe3ac1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ac6  ldarg.0
0xe3ac7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3acc  ldstr    aLocidBusinessr_2// "LOCID_BUSINESSRULE_STATUS"
0xe3ad1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3ad6  ldstr    aSystemcustomiz_41// "SystemCustomization.BusinessRules.Statu"...
0xe3adb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ae0  ldc.i4.0
0xe3ae1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ae6  ldarg.0
0xe3ae7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3aec  ldstr    aLocidPblconfir// "LOCID_PBLCONFIRM_DELETE"
0xe3af1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3af6  ldstr    aSystemcustomiz_42// "SystemCustomization.BusinessRules.Confi"...
0xe3afb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3b00  ldc.i4.0
0xe3b01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3b06  ldarg.0
0xe3b07  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3b0c  ldstr    aLocidPblconfir_0// "LOCID_PBLCONFIRM_DELETEBODY"
0xe3b11  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3b16  ldstr    aSystemcustomiz_43// "SystemCustomization.BusinessRules.Confi"...
0xe3b1b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3b20  ldc.i4.0
0xe3b21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3b26  ldarg.0
0xe3b27  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3b2c  ldstr    aLocidPblerrorT// "LOCID_PBLERROR_TITLE"
0xe3b31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3b36  ldstr    aSystemcustomiz_44// "SystemCustomization.BusinessRules.Error"...
0xe3b3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3b40  ldc.i4.0
0xe3b41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3b46  ldarg.0
0xe3b47  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3b4c  ldstr    aLocidPblerrorG// "LOCID_PBLERROR_GENERIC"
0xe3b51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3b56  ldstr    aErrorMessageGe// "Error_Message_Generic"
0xe3b5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3b60  ldc.i4.0
0xe3b61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3b66  ldarg.0
0xe3b67  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3b6c  ldstr    aLocidProcessin// "LOCID_PROCESSING"
0xe3b71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3b76  ldstr    aInlineeditform// "InlineEditForm_Processing"
0xe3b7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3b80  ldc.i4.0
0xe3b81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3b86  ldarg.0
0xe3b87  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3b8c  ldstr    aLocidFlyoutClo// "LOCID_FLYOUT_CLOSE"
0xe3b91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3b96  ldstr    aInlineeditFlyo// "InlineEdit.FlyOut.Close"
0xe3b9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ba0  ldc.i4.0
0xe3ba1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ba6  ldarg.0
0xe3ba7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3bac  ldstr    aLocidSaveasNam// "LOCID_SAVEAS_NAMEFORMAT"
0xe3bb1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3bb6  ldstr    aSystemcustomiz_45// "SystemCustomization.BusinessRules.SaveA"...
0xe3bbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3bc0  ldc.i4.0
0xe3bc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3bc6  ldarg.0
0xe3bc7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3bcc  ldstr    aLocidSaveerror// "LOCID_SAVEERROR_ZEROACTION"
0xe3bd1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3bd6  ldstr    aSystemcustomiz_46// "SystemCustomization.BusinessRules.SaveE"...
0xe3bdb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3be0  ldc.i4.0
0xe3be1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3be6  ldarg.0
0xe3be7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3bec  ldstr    aLocidSaveerror_0// "LOCID_SAVEERROR_VALIDOPERATOR"
0xe3bf1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3bf6  ldstr    aSystemcustomiz_47// "SystemCustomization.BusinessRules.SaveE"...
0xe3bfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3c00  ldc.i4.0
0xe3c01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3c06  ldarg.0
0xe3c07  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3c0c  ldstr    aLocidBusinessr_3// "LOCID_BUSINESSRULE_NAMELENOVR"
0xe3c11  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3c16  ldstr    aWebFormsStyles_0// "Web._forms.styles.TEXTAREA.htc_11_0"
0xe3c1b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3c20  ldc.i4.0
0xe3c21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3c26  ldarg.0
0xe3c27  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3c2c  ldstr    aLocidBusinessr_4// "LOCID_BUSINESSRULE_DONETOOLTIP"
0xe3c31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3c36  ldstr    aSystemcustomiz_48// "SystemCustomization.BusinessRules.DoneB"...
0xe3c3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3c40  ldc.i4.0
0xe3c41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3c46  ldarg.0
0xe3c47  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3c4c  ldstr    aLocidBusinessr_5// "LOCID_BUSINESSRULE_DISCRDTOOLTIP"
0xe3c51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3c56  ldstr    aSystemcustomiz_49// "SystemCustomization.BusinessRules.Disca"...
0xe3c5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3c60  ldc.i4.0
0xe3c61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3c66  ldarg.0
0xe3c67  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3c6c  ldstr    aLocidPblelseDe// "LOCID_PBLELSE_DELETETOOLTIP"
0xe3c71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3c76  ldstr    aSystemcustomiz_50// "SystemCustomization.BusinessRules.Secti"...
0xe3c7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3c80  ldc.i4.0
0xe3c81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3c86  ldarg.0
0xe3c87  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3c8c  ldstr    aLocidBusinessr_6// "LOCID_BUSINESSRULE_SETATTRVALUE"
0xe3c91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3c96  ldstr    aSystemcustomiz_51// "SystemCustomization.BusinessRules.SetAt"...
0xe3c9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ca0  ldc.i4.0
0xe3ca1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ca6  ldarg.0
0xe3ca7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3cac  ldstr    aLocidBusinessr_7// "LOCID_BUSINESSRULE_CLRATTRVALUE"
0xe3cb1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3cb6  ldstr    aSystemcustomiz_52// "SystemCustomization.BusinessRules.Clear"...
0xe3cbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3cc0  ldc.i4.0
0xe3cc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3cc6  ldarg.0
0xe3cc7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3ccc  ldstr    aLocidBusinessr_8// "LOCID_BUSINESSRULE_SETATTRHEADER"
0xe3cd1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3cd6  ldstr    aSystemcustomiz_53// "SystemCustomization.BusinessRules.SetVa"...
0xe3cdb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ce0  ldc.i4.0
0xe3ce1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ce6  ldarg.0
0xe3ce7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3cec  ldstr    aLocidBusinessr_9// "LOCID_BUSINESSRULE_SETATTRNULLOP"
0xe3cf1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3cf6  ldstr    aSystemcustomiz_54// "SystemCustomization.BusinessRules.SetNu"...
0xe3cfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3d00  ldc.i4.0
0xe3d01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3d06  ldarg.0
0xe3d07  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3d0c  ldstr    aLocidPbldialog// "LOCID_PBLDIALOG_OK"
0xe3d11  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3d16  ldstr    aButtonLabelOk// "Button_Label_OK"
0xe3d1b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3d20  ldc.i4.0
0xe3d21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3d26  ldarg.0
0xe3d27  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3d2c  ldstr    aLocidPbldialog_0// "LOCID_PBLDIALOG_CANCEL"
0xe3d31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3d36  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xe3d3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3d40  ldc.i4.0
0xe3d41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3d46  ldarg.0
0xe3d47  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3d4c  ldstr    aLocidCalculate// "LOCID_CALCULATEDFIELD_ELSE"
0xe3d51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3d56  ldstr    aSystemcustomiz_55// "SystemCustomization.CalculatedFields.Se"...
0xe3d5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3d60  ldc.i4.0
0xe3d61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3d66  ldarg.0
0xe3d67  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3d6c  ldstr    aLocidCalculate_0// "LOCID_CALCULATEDFIELD_ELSEIF"
0xe3d71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3d76  ldstr    aSystemcustomiz_56// "SystemCustomization.CalculatedFields.Se"...
0xe3d7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3d80  ldc.i4.0
0xe3d81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3d86  ldarg.0
0xe3d87  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3d8c  ldstr    aLocidCalculate_1// "LOCID_CALCULATEDFIELD_EXPRESSION"
0xe3d91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3d96  ldstr    aSystemcustomiz_57// "SystemCustomization.CalculatedFields.Se"...
0xe3d9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3da0  ldc.i4.0
0xe3da1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3da6  ldarg.0
0xe3da7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3dac  ldstr    aLocidCalculate_2// "LOCID_CALCULATEDFIELD_ACTION"
0xe3db1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3db6  ldstr    aSystemcustomiz_58// "SystemCustomization.BusinessRules.Secti"...
0xe3dbb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3dc0  ldc.i4.0
0xe3dc1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3dc6  ldarg.0
0xe3dc7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3dcc  ldstr    aLocidCalculate_3// "LOCID_CALCULATEDFIELD_CONDITION"
0xe3dd1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3dd6  ldstr    aSystemcustomiz_59// "SystemCustomization.BusinessRules.Secti"...
0xe3ddb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3de0  ldc.i4.0
0xe3de1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3de6  ldarg.0
0xe3de7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3dec  ldstr    aLocidCalcfield// "LOCID_CALCFIELD_ADD_CONDITION"
0xe3df1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3df6  ldstr    aSystemcustomiz_60// "SystemCustomization.CalculatedFields.Ad"...
0xe3dfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3e00  ldc.i4.0
0xe3e01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3e06  ldarg.0
0xe3e07  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3e0c  ldstr    aLocidCalcfield_0// "LOCID_CALCFIELD_ADD_ACTION"
0xe3e11  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3e16  ldstr    aSystemcustomiz_61// "SystemCustomization.CalculatedFields.Ad"...
0xe3e1b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3e20  ldc.i4.0
0xe3e21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3e26  ldarg.0
0xe3e27  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3e2c  ldstr    aLocidCalcfield_1// "LOCID_CALCFIELD_ADD_EXPRESSION"
0xe3e31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3e36  ldstr    aSystemcustomiz_62// "SystemCustomization.CalculatedFields.Ad"...
0xe3e3b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3e40  ldc.i4.0
0xe3e41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3e46  ldarg.0
0xe3e47  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3e4c  ldstr    aLocidCalcfield_2// "LOCID_CALCFIELD_CONDITION_TIP"
0xe3e51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3e56  ldstr    aSystemcustomiz_63// "SystemCustomization.BusinessRules.AddCo"...
0xe3e5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3e60  ldc.i4.0
0xe3e61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3e66  ldarg.0
0xe3e67  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3e6c  ldstr    aLocidCalcfield_3// "LOCID_CALCFIELD_ACTION_TIP"
0xe3e71  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3e76  ldstr    aSystemcustomiz_64// "SystemCustomization.BusinessRules.AddAc"...
0xe3e7b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3e80  ldc.i4.0
0xe3e81  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3e86  ldarg.0
0xe3e87  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3e8c  ldstr    aLocidCalcfield_4// "LOCID_CALCFIELD_EXPRESSION_TIP"
0xe3e91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3e96  ldstr    aSystemcustomiz_65// "SystemCustomization.CalculatedFields.Ad"...
0xe3e9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ea0  ldc.i4.0
0xe3ea1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ea6  ldarg.0
0xe3ea7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3eac  ldstr    aLocidPblconfir_1// "LOCID_PBLCONFIRM_DELETEELSE"
0xe3eb1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3eb6  ldstr    aSystemcustomiz_66// "SystemCustomization.BusinessRules.Confi"...
0xe3ebb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ec0  ldc.i4.0
0xe3ec1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ec6  ldarg.0
0xe3ec7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3ecc  ldstr    aLocidBusinessr_10// "LOCID_BUSINESSRULE_HELPTOOLTIP"
0xe3ed1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3ed6  ldstr    aSystemcustomiz_67// "SystemCustomization.BusinessRules.HelpT"...
0xe3edb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3ee0  ldc.i4.0
0xe3ee1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3ee6  ldarg.0
0xe3ee7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
0xe3eec  ldstr    aLocidFieldedit// "LOCID_FIELDEDITOR_OPTIONAL"
0xe3ef1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xe3ef6  ldstr    aSystemcustomiz_68// "SystemCustomization.FieldEditor.Section"...
0xe3efb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xe3f00  ldc.i4.0
0xe3f01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xe3f06  ldarg.0
0xe3f07  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header Microsoft.Crm.Web.Tools.SystemCustomization.Common.ManageRulesView::get_AppPageHeader()
  ... truncated ...
```
