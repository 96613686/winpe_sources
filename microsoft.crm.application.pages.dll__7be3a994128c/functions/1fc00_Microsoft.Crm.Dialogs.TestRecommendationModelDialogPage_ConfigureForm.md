# Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::ConfigureForm

- ea: `0x1fc00`
- end: `0x1fdaa`
- name: `Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::ConfigureForm`
- size: `426`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1fdb0`

## string_xrefs

- `0x1fc1e`: `Web._grid.cmds.dlg_testrecommendationmodel.aspx_Title`
- `0x1fc44`: `Web._grid.cmds.dlg_testrecommendationmodel.aspx_Description`
- `0x1fca2`: `Web._grid.cmds.dlg_testrecommendationmodel.aspx_Product`
- `0x1fce2`: `Web._grid.cmds.dlg_testrecommendationmodel.aspx_ModelVersion1`
- `0x1fd22`: `Web._grid.cmds.dlg_testrecommendationmodel.aspx_ModelVersion2`
- `0x1fd62`: `Web._grid.cmds.dlg_testrecommendationmodel.aspx_ModelVersion3`
- `0x1fd77`: `Web._grid.cmds.dlg_testrecommendationmodel.aspx_EmptyGridMessage`

## pseudocode

```c

```

## disassembly

```asm
0x1fc00  ldarg.0
0x1fc01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1fc06  ldarg.0
0x1fc07  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1fc0c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1fc11  stloc.0
0x1fc12  ldloc.0
0x1fc13  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1fc18  ldarg.0
0x1fc19  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fc1e  ldstr    aWebGridCmdsDlg_100// "Web._grid.cmds.dlg_testrecommendationmo"...
0x1fc23  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fc28  ldc.i4.0
0x1fc29  newarr   [mscorlib]System.Object
0x1fc2e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1fc33  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x1fc38  ldloc.0
0x1fc39  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1fc3e  ldarg.0
0x1fc3f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fc44  ldstr    aWebGridCmdsDlg_101// "Web._grid.cmds.dlg_testrecommendationmo"...
0x1fc49  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fc4e  ldc.i4.0
0x1fc4f  newarr   [mscorlib]System.Object
0x1fc54  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1fc59  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x1fc5e  ldloc.0
0x1fc5f  ldc.i4.0
0x1fc60  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x1fc65  ldloc.0
0x1fc66  ldc.i4.1
0x1fc67  ldstr    aButtonLabelSho// "Button_Label_ShowResults"
0x1fc6c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x1fc71  ldloc.0
0x1fc72  ldc.i4.2
0x1fc73  ldstr    aButtonLabelClo// "Button_Label_Close"
0x1fc78  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x1fc7d  ldarg.0
0x1fc7e  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::productLookup
0x1fc83  ldc.i4.1
0x1fc84  newarr   [mscorlib]System.Int32
0x1fc89  dup
0x1fc8a  ldc.i4.0
0x1fc8b  ldc.i4   0x400
0x1fc90  stelem.i4
0x1fc91  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1fc96  ldarg.0
0x1fc97  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::productLookup
0x1fc9c  ldarg.0
0x1fc9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fca2  ldstr    aWebGridCmdsDlg_102// "Web._grid.cmds.dlg_testrecommendationmo"...
0x1fca7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fcac  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_AccessibilityLabel(string)
0x1fcb1  ldarg.0
0x1fcb2  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion1
0x1fcb7  ldc.i4.1
0x1fcb8  newarr   [mscorlib]System.Int32
0x1fcbd  dup
0x1fcbe  ldc.i4.0
0x1fcbf  ldc.i4   0x26CF
0x1fcc4  stelem.i4
0x1fcc5  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1fcca  ldarg.0
0x1fccb  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion1
0x1fcd0  ldc.i4.1
0x1fcd1  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DisableViewPicker(bool)
0x1fcd6  ldarg.0
0x1fcd7  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion1
0x1fcdc  ldarg.0
0x1fcdd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fce2  ldstr    aWebGridCmdsDlg_103// "Web._grid.cmds.dlg_testrecommendationmo"...
0x1fce7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fcec  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_AccessibilityLabel(string)
0x1fcf1  ldarg.0
0x1fcf2  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion2
0x1fcf7  ldc.i4.1
0x1fcf8  newarr   [mscorlib]System.Int32
0x1fcfd  dup
0x1fcfe  ldc.i4.0
0x1fcff  ldc.i4   0x26CF
0x1fd04  stelem.i4
0x1fd05  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1fd0a  ldarg.0
0x1fd0b  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion2
0x1fd10  ldc.i4.1
0x1fd11  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DisableViewPicker(bool)
0x1fd16  ldarg.0
0x1fd17  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion2
0x1fd1c  ldarg.0
0x1fd1d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fd22  ldstr    aWebGridCmdsDlg_104// "Web._grid.cmds.dlg_testrecommendationmo"...
0x1fd27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fd2c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_AccessibilityLabel(string)
0x1fd31  ldarg.0
0x1fd32  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion3
0x1fd37  ldc.i4.1
0x1fd38  newarr   [mscorlib]System.Int32
0x1fd3d  dup
0x1fd3e  ldc.i4.0
0x1fd3f  ldc.i4   0x26CF
0x1fd44  stelem.i4
0x1fd45  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1fd4a  ldarg.0
0x1fd4b  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion3
0x1fd50  ldc.i4.1
0x1fd51  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DisableViewPicker(bool)
0x1fd56  ldarg.0
0x1fd57  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::lookupModelVersion3
0x1fd5c  ldarg.0
0x1fd5d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fd62  ldstr    aWebGridCmdsDlg_105// "Web._grid.cmds.dlg_testrecommendationmo"...
0x1fd67  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fd6c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_AccessibilityLabel(string)
0x1fd71  ldarg.0
0x1fd72  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1fd77  ldstr    aWebGridCmdsDlg_106// "Web._grid.cmds.dlg_testrecommendationmo"...
0x1fd7c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1fd81  stloc.1
0x1fd82  ldarg.0
0x1fd83  ldarg.0
0x1fd84  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::recommendationModelGrid1
0x1fd89  ldloc.1
0x1fd8a  call     instance void Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::ConfigureGrid(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid gridControl, string emptyGridMessage)
0x1fd8f  ldarg.0
0x1fd90  ldarg.0
0x1fd91  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::recommendationModelGrid2
0x1fd96  ldloc.1
0x1fd97  call     instance void Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::ConfigureGrid(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid gridControl, string emptyGridMessage)
0x1fd9c  ldarg.0
0x1fd9d  ldarg.0
0x1fd9e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::recommendationModelGrid3
0x1fda3  ldloc.1
0x1fda4  call     instance void Microsoft.Crm.Dialogs.TestRecommendationModelDialogPage::ConfigureGrid(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid gridControl, string emptyGridMessage)
0x1fda9  ret
```
