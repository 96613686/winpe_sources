# Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::ConfigureHeader

- ea: `0xbba60`
- end: `0xbbe28`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::ConfigureHeader`
- size: `968`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0xbba60`
- `0xbc8b0`
- `0xbc8d0`

## string_xrefs

- `0xbbab6`: `/_static/_common/styles/AutoToolTip.js`
- `0xbbd6d`: `_bCreate`
- `0xbbd35`: `LOCID_KEYSUTL_REMOVEKEYS`
- `0xbbd3b`: `AlternateKeys.Button.Remove`

## pseudocode

```c

```

## disassembly

```asm
0xbba60  ldarg.0
0xbba61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbba66  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xbba6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xbba70  ldarg.0
0xbba71  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbba76  ldstr    aNavNavCssAspx// "/_nav/nav.css.aspx"
0xbba7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xbba80  ldarg.0
0xbba81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbba86  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0xbba8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbba90  ldarg.0
0xbba91  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbba96  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0xbba9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbaa0  ldarg.0
0xbbaa1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbaa6  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0xbbaab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbab0  ldarg.0
0xbbab1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbab6  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xbbabb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbac0  ldarg.0
0xbbac1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbac6  ldstr    aStaticToolsSol_5// "/_static/tools/Solution/Scripts/Managed"...
0xbbacb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbad0  ldarg.0
0xbbad1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbad6  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0xbbadb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbae0  ldarg.0
0xbbae1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbae6  ldstr    aStaticToolsSys_35// "/_static/tools/systemcustomization/enti"...
0xbbaeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbaf0  ldarg.0
0xbbaf1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbaf6  ldstr    aStaticToolsSys_36// "/_static/tools/systemcustomization/enti"...
0xbbafb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbb00  ldarg.0
0xbbb01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbb06  ldstr    aStaticToolsSys_34// "/_static/tools/systemcustomization/enti"...
0xbbb0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbb10  ldarg.0
0xbbb11  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbb16  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0xbbb1b  ldarg.0
0xbbb1c  ldstr    aValidationErro// "Validation.Errors.CannotBeBlank"
0xbbb21  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbb26  ldc.i4.0
0xbbb27  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbb2c  ldarg.0
0xbbb2d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbb32  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0xbbb37  ldarg.0
0xbbb38  ldstr    aValidationErro_0// "Validation.Errors.CannotHaveInvalidChar"...
0xbbb3d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbb42  ldc.i4.0
0xbbb43  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbb48  ldarg.0
0xbbb49  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbb4e  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0xbbb53  ldarg.0
0xbbb54  ldstr    aValidationErro_1// "Validation.Errors.CanOnlyHaveAlphaNumer"...
0xbbb59  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbb5e  ldc.i4.0
0xbbb5f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbb64  ldarg.0
0xbbb65  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbb6a  ldstr    aLocidWarningNo_0// "LOCID_WARNING_NOKEYDISPLAYNAME"
0xbbb6f  ldarg.0
0xbbb70  ldstr    aManagealternat// "ManageAlternateKeySettingPage.NoDisplay"...
0xbbb75  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbb7a  ldc.i4.0
0xbbb7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbb80  ldarg.0
0xbbb81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbb86  ldstr    aLocidWarningNo_1// "LOCID_WARNING_NOKEYNAME"
0xbbb8b  ldarg.0
0xbbb8c  ldstr    aManagealternat_0// "ManageAlternateKeySettingPage.NoName"
0xbbb91  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbb96  ldc.i4.0
0xbbb97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbb9c  ldarg.0
0xbbb9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbba2  ldstr    aLocidWarningTo// "LOCID_WARNING_TOOMANYCOLUMNS"
0xbbba7  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xbbbac  ldarg.0
0xbbbad  ldstr    aManagealternat_1// "ManageAlternateKeySettingPage.SelectedK"...
0xbbbb2  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbbb7  ldc.i4.1
0xbbbb8  newarr   [mscorlib]System.Object
0xbbbbd  dup
0xbbbbe  ldc.i4.0
0xbbbbf  call     int32 Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetMaximumAttributesAllowedPerEntityKey()
0xbbbc4  box      [mscorlib]System.Int32
0xbbbc9  stelem.ref
0xbbbca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbbbcf  ldc.i4.0
0xbbbd0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbbd5  ldarg.0
0xbbbd6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbbdb  ldstr    aLocidWarningNo_2// "LOCID_WARNING_NOCOLUMNS"
0xbbbe0  ldarg.0
0xbbbe1  ldstr    aManagealternat_2// "ManageAlternateKeySettingPage.SelectedK"...
0xbbbe6  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbbeb  ldc.i4.0
0xbbbec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbbf1  ldarg.0
0xbbbf2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbbf7  ldstr    aToolsFieldsele// "/_tools/fieldselect/fieldselect.css.asp"...
0xbbbfc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xbbc01  ldarg.0
0xbbc02  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc07  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0xbbc0c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbc11  ldarg.0
0xbbc12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc17  ldstr    aStaticToolsFor_0// "/_static/tools/formeditor/scripts/field"...
0xbbc1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbc21  ldarg.0
0xbbc22  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc27  ldstr    aStaticToolsFie// "/_static/_tools/fieldselect/fieldselect"...
0xbbc2c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbc31  ldarg.0
0xbbc32  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc37  ldstr    aStaticToolsVie_2// "/_static/tools/vieweditor/scripts/selec"...
0xbbc3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbc41  ldarg.0
0xbbc42  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc47  ldstr    aStaticToolsSol_7// "/_static/tools/Solution/Scripts/EntityK"...
0xbbc4c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbc51  ldarg.0
0xbbc52  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc57  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0xbbc5c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xbbc61  ldarg.0
0xbbc62  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc67  ldstr    aLocidSelvalsTi// "LOCID_SELVALS_TITLE_AVAILVALS"
0xbbc6c  ldarg.0
0xbbc6d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbbc72  ldstr    aWebToolsAltern// "Web.Tools.AlternateKeys.Editor.Dialogs."...
0xbbc77  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbbc7c  ldc.i4.0
0xbbc7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbc82  ldarg.0
0xbbc83  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbc88  ldstr    aLocidSelvalsTi_0// "LOCID_SELVALS_TITLE_SELTDVALS"
0xbbc8d  ldarg.0
0xbbc8e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbbc93  ldstr    aWebToolsAltern_0// "Web.Tools.AlternateKeys.Editor.Dialogs."...
0xbbc98  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbbc9d  ldc.i4.0
0xbbc9e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbca3  ldarg.0
0xbbca4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbca9  ldstr    aLocidKeysutlCo// "LOCID_KEYSUTL_CONFIRMDELKEYS"
0xbbcae  ldarg.0
0xbbcaf  ldstr    aManageentityke// "ManageEntityKey.Messages.ConfirmAttribu"...
0xbbcb4  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbcb9  ldc.i4.0
0xbbcba  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbcbf  ldarg.0
0xbbcc0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbcc5  ldstr    aLocidKeysutlCr// "LOCID_KEYSUTL_CREATINGKEYS"
0xbbcca  ldarg.0
0xbbccb  ldstr    aManageentityke_0// "ManageEntityKey.Messages.CreatingEntity"...
0xbbcd0  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbcd5  ldc.i4.0
0xbbcd6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbcdb  ldarg.0
0xbbcdc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbce1  ldstr    aLocidKeysutlRe// "LOCID_KEYSUTL_REACTIVATEKEY"
0xbbce6  ldarg.0
0xbbce7  ldstr    aManageentityke_1// "ManageEntityKey.Messages.ReactivatingEn"...
0xbbcec  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbcf1  ldc.i4.0
0xbbcf2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbcf7  ldarg.0
0xbbcf8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbcfd  ldstr    aLocidKeysutlDe// "LOCID_KEYSUTL_DELETINGKEYS"
0xbbd02  ldarg.0
0xbbd03  ldstr    aManageentityke_2// "ManageEntityKey.Messages.DeletingEntity"...
0xbbd08  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbd0d  ldc.i4.0
0xbbd0e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbd13  ldarg.0
0xbbd14  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbd19  ldstr    aLocidKeysutlAd// "LOCID_KEYSUTL_ADDKEYS"
0xbbd1e  ldarg.0
0xbbd1f  ldstr    aAlternatekeysB// "AlternateKeys.Button.Add"
0xbbd24  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbd29  ldc.i4.0
0xbbd2a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbd2f  ldarg.0
0xbbd30  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbd35  ldstr    aLocidKeysutlRe_0// "LOCID_KEYSUTL_REMOVEKEYS"
0xbbd3a  ldarg.0
0xbbd3b  ldstr    aAlternatekeysB_0// "AlternateKeys.Button.Remove"
0xbbd40  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbd45  ldc.i4.0
0xbbd46  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbd4b  ldarg.0
0xbbd4c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbd51  ldstr    aLocidKeysutlOk// "LOCID_KEYSUTL_OKKEYS"
0xbbd56  ldarg.0
0xbbd57  ldstr    aAlternatekeysB_1// "AlternateKeys.Button.OK"
0xbbd5c  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetSCString(string name)
0xbbd61  ldc.i4.0
0xbbd62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xbbd67  ldarg.0
0xbbd68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbd6d  ldstr    aBcreate// "_bCreate"
0xbbd72  ldarg.0
0xbbd73  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_mode
0xbbd78  ldc.i4.0
0xbbd79  ceq
0xbbd7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xbbd80  ldarg.0
0xbbd81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbd86  ldstr    aBview// "_bView"
0xbbd8b  ldarg.0
0xbbd8c  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_mode
0xbbd91  ldc.i4.1
0xbbd92  ceq
0xbbd94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xbbd99  ldarg.0
0xbbd9a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbd9f  ldstr    aSentityid// "_sEntityId"
0xbbda4  ldarg.0
0xbbda5  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_entityMD
0xbbdaa  brtrue.s loc_BBDB3
0xbbdac  ldsfld   string [mscorlib]System.String::Empty
0xbbdb1  br.s     loc_BBDC3
0xbbdb3  ldarg.0
0xbbdb4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_entityMD
0xbbdb9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0xbbdbe  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xbbdc3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbbdc8  ldarg.0
0xbbdc9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbdce  ldstr    aSentitytypecod// "_sEntityTypeCode"
0xbbdd3  ldarg.0
0xbbdd4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_entityMD
0xbbdd9  brtrue.s loc_BBDDE
0xbbddb  ldc.i4.0
0xbbddc  br.s     loc_BBDE9
0xbbdde  ldarg.0
0xbbddf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_entityMD
0xbbde4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xbbde9  conv.i8
0xbbdea  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xbbdef  ldarg.0
0xbbdf0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbdf5  ldstr    aSalternatekeyi// "_sAlternateKeyId"
0xbbdfa  ldarg.0
0xbbdfb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_alternateKeyId
0xbbe00  pop
0xbbe01  ldarg.0
0xbbe02  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::_alternateKeyId
0xbbe07  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xbbe0c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xbbe11  ldarg.0
0xbbe12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xbbe17  ldstr    aMaxattributesa// "_maxAttributesAllowedPerEntityKey"
0xbbe1c  call     int32 Microsoft.Crm.Web.Tools.SystemCustomization.AlternateKeys.ManageAlternateKeyPage::GetMaximumAttributesAllowedPerEntityKey()
0xbbe21  conv.i8
0xbbe22  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xbbe27  ret
```
