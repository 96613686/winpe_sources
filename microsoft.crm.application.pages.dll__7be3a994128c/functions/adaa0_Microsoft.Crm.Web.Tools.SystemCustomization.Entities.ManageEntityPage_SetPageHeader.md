# Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::SetPageHeader

- ea: `0xadaa0`
- end: `0xae094`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::SetPageHeader`
- size: `1524`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xad890`

## callees

- `0xadaa0`
- `0xae0a0`
- `0xae0c0`
- `0xb08c0`
- `0xb08e0`

## string_xrefs

- `0xadb93`: `/_static/_common/scripts/details.js`
- `0xadbb3`: `/_static/tools/solution/scripts/solutionComponentList.js`
- `0xadd8c`: `EntityUtil.Messages.CannotUpdateSystemEntityIcons`
- `0xadda8`: `EntityUtil.Messages.CannotDeleteSystemEntity`
- `0xadde0`: `EntityUtil.Messages.ConfirmEntityDelete`

## pseudocode

```c

```

## disassembly

```asm
0xadaa0  ldarg.0
0xadaa1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadaa6  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xadaab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xadab0  ldarg.0
0xadab1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadab6  ldstr    aNavNavCssAspx// "/_nav/nav.css.aspx"
0xadabb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xadac0  ldarg.0
0xadac1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadac6  ldstr    aStaticToolsSys_25// "/_static/tools/systemcustomization/enti"...
0xadacb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xadad0  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xadad5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xadada  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlMobile()
0xadadf  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xadae4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xadae9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xadaee  brfalse.s loc_ADB3D
0xadaf0  ldarg.0
0xadaf1  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xadaf6  brfalse.s loc_ADB3D
0xadaf8  ldarg.0
0xadaf9  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xadafe  ldc.i4.2
0xadaff  beq.s    loc_ADB3D
0xadb01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xadb06  ldstr    aStaticCss0Cust// "/_static/css/{0}/CustomControls.css"
0xadb0b  ldc.i4.1
0xadb0c  newarr   [mscorlib]System.Object
0xadb11  dup
0xadb12  ldc.i4.0
0xadb13  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xadb18  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xadb1d  stloc.1
0xadb1e  ldloca.s 1
0xadb20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xadb25  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xadb2a  stelem.ref
0xadb2b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xadb30  stloc.0
0xadb31  ldarg.0
0xadb32  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadb37  ldloc.0
0xadb38  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xadb3d  ldarg.0
0xadb3e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadb43  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0xadb48  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadb4d  ldarg.0
0xadb4e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadb53  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0xadb58  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadb5d  ldarg.0
0xadb5e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadb63  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0xadb68  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadb6d  ldarg.0
0xadb6e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadb73  ldstr    aStaticToolsSys_26// "/_static/tools/SystemCustomization/Enti"...
0xadb78  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadb7d  ldarg.0
0xadb7e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadb83  ldstr    aStaticToolsSys_27// "/_static/tools/systemcustomization/enti"...
0xadb88  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadb8d  ldarg.0
0xadb8e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadb93  ldstr    aStaticCommonSc_24// "/_static/_common/scripts/details.js"
0xadb98  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadb9d  ldarg.0
0xadb9e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadba3  ldstr    aStaticToolsSys_28// "/_static/tools/systemcustomization/enti"...
0xadba8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadbad  ldarg.0
0xadbae  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadbb3  ldstr    aStaticToolsSol_0// "/_static/tools/solution/scripts/solutio"...
0xadbb8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadbbd  ldarg.0
0xadbbe  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadbc3  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0xadbc8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadbcd  ldarg.0
0xadbce  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadbd3  ldstr    aStaticControls_18// "/_static/_controls/TreeNav/treenavcontr"...
0xadbd8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadbdd  ldarg.0
0xadbde  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadbe3  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0xadbe8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadbed  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xadbf2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xadbf7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlMobile()
0xadbfc  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::get_Name()
0xadc01  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xadc06  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xadc0b  brfalse.s loc_ADC4F
0xadc0d  ldarg.0
0xadc0e  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xadc13  brfalse.s loc_ADC4F
0xadc15  ldarg.0
0xadc16  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::_mode
0xadc1b  ldc.i4.2
0xadc1c  beq.s    loc_ADC4F
0xadc1e  ldarg.0
0xadc1f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadc24  ldstr    aStaticControls_27// "/_static/_controls/CustomControls/Custo"...
0xadc29  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xadc2e  ldarg.0
0xadc2f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadc34  ldstr    aLocidCustomcon// "LOCID_CUSTOMCONTROLS_VIEWSTART"
0xadc39  ldarg.0
0xadc3a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadc3f  ldstr    aCustomcontrols// "CustomControls_ViewStart"
0xadc44  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadc49  ldc.i4.0
0xadc4a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadc4f  ldarg.0
0xadc50  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadc55  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0xadc5a  ldarg.0
0xadc5b  ldstr    aValidationErro// "Validation.Errors.CannotBeBlank"
0xadc60  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xadc65  ldc.i4.0
0xadc66  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadc6b  ldarg.0
0xadc6c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadc71  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0xadc76  ldarg.0
0xadc77  ldstr    aValidationErro_0// "Validation.Errors.CannotHaveInvalidChar"...
0xadc7c  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xadc81  ldc.i4.0
0xadc82  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadc87  ldarg.0
0xadc88  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadc8d  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0xadc92  ldarg.0
0xadc93  ldstr    aValidationErro_1// "Validation.Errors.CanOnlyHaveAlphaNumer"...
0xadc98  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xadc9d  ldc.i4.0
0xadc9e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadca3  ldarg.0
0xadca4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadca9  ldstr    aLocidManentPub// "LOCID_MANENT_PUBLISHALERT"
0xadcae  ldarg.0
0xadcaf  ldstr    aMessagesPublis// "Messages.PublishAlert"
0xadcb4  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetString(string name)
0xadcb9  ldc.i4.0
0xadcba  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadcbf  ldarg.0
0xadcc0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadcc5  ldstr    aLocidTreePlus// "LOCID_TREE_PLUS"
0xadcca  ldarg.0
0xadccb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadcd0  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0xadcd5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadcda  ldc.i4.0
0xadcdb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadce0  ldarg.0
0xadce1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadce6  ldstr    aLocidTreeMinus// "LOCID_TREE_MINUS"
0xadceb  ldarg.0
0xadcec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadcf1  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0xadcf6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadcfb  ldc.i4.0
0xadcfc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadd01  ldarg.0
0xadd02  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadd07  ldstr    aLocidSyscustCo// "LOCID_SYSCUST_COLLECTIONAME"
0xadd0c  ldarg.0
0xadd0d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadd12  ldstr    aSystemcustomiz_422// "SystemCustomization.ManageEntityPage.Er"...
0xadd17  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadd1c  ldc.i4.0
0xadd1d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadd22  ldarg.0
0xadd23  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadd28  ldstr    aLocidSyscustIn_0// "LOCID_SYSCUST_INVALIDCOLORVALUE"
0xadd2d  ldarg.0
0xadd2e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadd33  ldstr    aSystemcustomiz_34// "SystemCustomization.ManageEntityPage.Er"...
0xadd38  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadd3d  ldc.i4.0
0xadd3e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadd43  ldarg.0
0xadd44  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadd49  ldstr    aLocidSyscustCa_0// "LOCID_SYSCUST_CANTSETONENOTEINT"
0xadd4e  ldarg.0
0xadd4f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadd54  ldstr    aSystemcustomiz_35// "SystemCustomization.ManageEntityPage.Er"...
0xadd59  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadd5e  ldc.i4.0
0xadd5f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadd64  ldarg.0
0xadd65  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadd6a  ldstr    aLocidConfirmAc_0// "LOCID_CONFIRM_ACTIVITY_DISPLAY"
0xadd6f  ldarg.0
0xadd70  ldstr    aEntityutilMess// "EntityUtil.Messages.ConfirmActivityHidi"...
0xadd75  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xadd7a  ldc.i4.0
0xadd7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadd80  ldarg.0
0xadd81  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadd86  ldstr    aLocidEntutlCan// "LOCID_ENTUTL_CANTUPDSYSENTICN"
0xadd8b  ldarg.0
0xadd8c  ldstr    aEntityutilMess_0// "EntityUtil.Messages.CannotUpdateSystemE"...
0xadd91  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xadd96  ldc.i4.0
0xadd97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadd9c  ldarg.0
0xadd9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadda2  ldstr    aLocidEntutlCan_0// "LOCID_ENTUTL_CANTDELSYSENT"
0xadda7  ldarg.0
0xadda8  ldstr    aEntityutilMess_1// "EntityUtil.Messages.CannotDeleteSystemE"...
0xaddad  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xaddb2  ldc.i4.0
0xaddb3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaddb8  ldarg.0
0xaddb9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaddbe  ldstr    aLocidEntutlCan_1// "LOCID_ENTUTL_CANTPUBLISHENT"
0xaddc3  ldarg.0
0xaddc4  ldstr    aEntityutilMess_2// "EntityUtil.Messages.CannotPublishEntity"
0xaddc9  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xaddce  ldc.i4.0
0xaddcf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaddd4  ldarg.0
0xaddd5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaddda  ldstr    aLocidEntutlCon// "LOCID_ENTUTL_CONFIRMDEL"
0xadddf  ldarg.0
0xadde0  ldstr    aEntityutilMess_3// "EntityUtil.Messages.ConfirmEntityDelete"
0xadde5  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xaddea  ldc.i4.0
0xaddeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xaddf0  ldarg.0
0xaddf1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xaddf6  ldstr    aLocidEntutlCre// "LOCID_ENTUTL_CREATINGENT"
0xaddfb  ldarg.0
0xaddfc  ldstr    aEntityutilMess_4// "EntityUtil.Messages.CreatingEntity"
0xade01  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xade06  ldc.i4.0
0xade07  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xade0c  ldarg.0
0xade0d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xade12  ldstr    aLocidEntutlUpd// "LOCID_ENTUTL_UPDATINGENT"
0xade17  ldarg.0
0xade18  ldstr    aEntityutilMess_5// "EntityUtil.Messages.UpdatingEntity"
0xade1d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xade22  ldc.i4.0
0xade23  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xade28  ldarg.0
0xade29  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xade2e  ldstr    aLocidEntutlDel// "LOCID_ENTUTL_DELETINGENT"
0xade33  ldarg.0
0xade34  ldstr    aEntityutilMess_6// "EntityUtil.Messages.DeletingEntity"
0xade39  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xade3e  ldc.i4.0
0xade3f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xade44  ldarg.0
0xade45  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xade4a  ldstr    aLocidEntutlPub// "LOCID_ENTUTL_PUBLISHINGENT"
0xade4f  ldarg.0
0xade50  ldstr    aEntityutilMess_7// "EntityUtil.Messages.PublishingEntity"
0xade55  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xade5a  ldc.i4.0
0xade5b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xade60  ldarg.0
0xade61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xade66  ldstr    aLocidMessagePu// "LOCID_MESSAGE_PUBLISHUNSAVED"
0xade6b  ldarg.0
0xade6c  ldstr    aMessagesPublis_0// "Messages.PublishingUnsavedChanges"
0xade71  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xade76  ldc.i4.0
0xade77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xade7c  ldarg.0
0xade7d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xade82  ldstr    aLocidConfirmAu// "LOCID_CONFIRM_AUDIT_DISABLE"
0xade87  ldarg.0
0xade88  ldstr    aSystemsettings_9// "SystemSettingsDialog.AuditTab.MainSecti"...
0xade8d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Entities.ManageEntityPage::GetSCString(string name)
0xade92  ldc.i4.0
0xade93  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xade98  ldarg.0
0xade99  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xade9e  ldstr    aLocidSyscustUn// "LOCID_SYSCUST_UNCHECK_OFFLINE"
0xadea3  ldarg.0
0xadea4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadea9  ldstr    aSystemcustomiz_423// "SystemCustomization.Messages.CannotDisa"...
0xadeae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xadeb3  ldc.i4.0
0xadeb4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadeb9  ldarg.0
0xadeba  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xadebf  ldstr    aLocidSyscustCh// "LOCID_SYSCUST_CHANGETRACKING"
0xadec4  ldarg.0
0xadec5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xadeca  ldstr    aSystemcustomiz_424// "SystemCustomization.Messages.CannotDisa"...
0xadecf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaded4  ldc.i4.0
0xaded5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xadeda  ldarg.0
  ... truncated ...
```
