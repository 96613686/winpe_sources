# Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::SetPageHeader

- ea: `0xb6890`
- end: `0xb71f5`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::SetPageHeader`
- size: `2405`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xb6460`

## callees

- `0xb6890`
- `0xb7200`
- `0xb7220`
- `0xb7270`
- `0xb72e0`
- `0xb7360`
- `0xb76d0`
- `0xba6d0`
- `0xbaed0`
- `0x10f4c0`

## string_xrefs

- `0xb6926`: `/_static/_common/styles/AutoToolTip.js`
- `0xb68c6`: `/_static/_common/scripts/jquery1.7.2.min.js`
- `0xb6a57`: `ImportWizard.EntityMapPage.Select.CreateNew`
- `0xb6b9c`: `_bCreate`
- `0xb6a9f`: `AttributeUtil.Messages.CannotDeleteSystemAttribute`
- `0xb6acc`: `AttributeUtil.Messages.ConfirmAttributeDelete`
- `0xb6aea`: `AttributeUtil.Messages.ConfirmAttributeDeletePhonetic`
- `0xb6a4c`: `LOCID_CREATE_NEW`
- `0xb6e67`: `_linkedAttributeRequired`
- `0xb7022`: `_linkedAttributeRequired`
- `0xb6eb5`: `LOCID_UPDATELINKTOATTRIBUTE`
- `0xb6ec0`: `ManageAttributePage.DataPropagationSection.Messages.UpdateLinkToAttribute`
- `0xb6f29`: `ManageAttributePage.DataPropagationSection.Messages.UpdateLinkToAttribute`
- `0xb6f1e`: `LOCID_UPDATE`
- `0xb6f54`: `LOCID_UPDATELINKEDATTRIBUTE`
- `0xb6f5f`: `ManageAttributePage.DataPropagationSection.Messages.UpdateLinkedAttribute`
- `0xb6f8a`: `_sLinkedAttributeId`
- `0xb6fd8`: `_sLinkedAttributeName`
- `0xb703b`: `_attributexml`
- `0xb70a0`: `rdFieldSecurityLabel`

## pseudocode

```c

```

## disassembly

```asm
0xb6890  ldarg.0
0xb6891  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6896  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xb689b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb68a0  ldarg.0
0xb68a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb68a6  ldstr    aNavNavCssAspx// "/_nav/nav.css.aspx"
0xb68ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb68b0  ldarg.0
0xb68b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb68b6  ldstr    aStaticToolsSys_31// "/_static/tools/systemcustomization/attr"...
0xb68bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xb68c0  ldarg.0
0xb68c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb68c6  ldstr    aStaticCommonSc_3// "/_static/_common/scripts/jquery1.7.2.mi"...
0xb68cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb68d0  ldarg.0
0xb68d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb68d6  ldstr    aStaticGridCmds// "/_static/_grid/cmds/util.js"
0xb68db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb68e0  ldarg.0
0xb68e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb68e6  ldstr    aStaticToolsSys_0// "/_static/tools/systemcustomization/scri"...
0xb68eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb68f0  ldarg.0
0xb68f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb68f6  ldstr    aStaticToolsDep// "/_static/tools/dependency/scripts/depen"...
0xb68fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb6900  ldarg.0
0xb6901  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6906  ldstr    aStaticToolsSol// "/_static/tools/solution/scripts/Managed"...
0xb690b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb6910  ldarg.0
0xb6911  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6916  ldstr    aStaticToolsSol_6// "/_static/tools/solution/scripts/StatusR"...
0xb691b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb6920  ldarg.0
0xb6921  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6926  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xb692b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb6930  ldarg.0
0xb6931  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6936  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0xb693b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb6940  ldarg.0
0xb6941  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6946  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0xb694b  ldarg.0
0xb694c  ldstr    aValidationErro// "Validation.Errors.CannotBeBlank"
0xb6951  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6956  ldc.i4.0
0xb6957  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb695c  ldarg.0
0xb695d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6962  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0xb6967  ldarg.0
0xb6968  ldstr    aValidationErro_0// "Validation.Errors.CannotHaveInvalidChar"...
0xb696d  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6972  ldc.i4.0
0xb6973  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6978  ldarg.0
0xb6979  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb697e  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0xb6983  ldarg.0
0xb6984  ldstr    aValidationErro_1// "Validation.Errors.CanOnlyHaveAlphaNumer"...
0xb6989  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb698e  ldc.i4.0
0xb698f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6994  ldarg.0
0xb6995  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb699a  ldstr    aLocidTreePlus// "LOCID_TREE_PLUS"
0xb699f  ldarg.0
0xb69a0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb69a5  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0xb69aa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb69af  ldc.i4.0
0xb69b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb69b5  ldarg.0
0xb69b6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb69bb  ldstr    aLocidTreeMinus// "LOCID_TREE_MINUS"
0xb69c0  ldarg.0
0xb69c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb69c6  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0xb69cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb69d0  ldc.i4.0
0xb69d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb69d6  ldarg.0
0xb69d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb69dc  ldstr    aLocidValidates// "LOCID_VALIDATESUCCESS"
0xb69e1  ldarg.0
0xb69e2  ldstr    aManageattribut// "ManageAttributePage.DataPropagationSect"...
0xb69e7  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb69ec  ldc.i4.0
0xb69ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb69f2  ldarg.0
0xb69f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb69f8  ldstr    aLocidValidatef// "LOCID_VALIDATEFAILURE"
0xb69fd  ldarg.0
0xb69fe  ldstr    aManageattribut_0// "ManageAttributePage.DataPropagationSect"...
0xb6a03  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6a08  ldc.i4.0
0xb6a09  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6a0e  ldarg.0
0xb6a0f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6a14  ldstr    aLocidSavewoval// "LOCID_SAVEWOVALIDATE"
0xb6a19  ldarg.0
0xb6a1a  ldstr    aManageattribut_1// "ManageAttributePage.DataPropagationSect"...
0xb6a1f  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6a24  ldc.i4.0
0xb6a25  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6a2a  ldarg.0
0xb6a2b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6a30  ldstr    aLocidConfirmAu// "LOCID_CONFIRM_AUDIT_DISABLE"
0xb6a35  ldarg.0
0xb6a36  ldstr    aSystemsettings_9// "SystemSettingsDialog.AuditTab.MainSecti"...
0xb6a3b  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6a40  ldc.i4.0
0xb6a41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6a46  ldarg.0
0xb6a47  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6a4c  ldstr    aLocidCreateNew// "LOCID_CREATE_NEW"
0xb6a51  ldarg.0
0xb6a52  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xb6a57  ldstr    aImportwizardEn_16// "ImportWizard.EntityMapPage.Select.Creat"...
0xb6a5c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xb6a61  ldc.i4.0
0xb6a62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6a67  ldarg.0
0xb6a68  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6a6d  ldstr    aLocidConfirmBe// "LOCID_CONFIRM_BEHAVIORCHANGE"
0xb6a72  ldarg.0
0xb6a73  ldstr    aManageattribut_2// "ManageAttributePage.TypeSection.Alert.B"...
0xb6a78  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6a7d  ldc.i4.0
0xb6a7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6a83  ldarg.0
0xb6a84  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6a89  ldstr    aStaticToolsSys_19// "/_static/tools/systemcustomization/attr"...
0xb6a8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb6a93  ldarg.0
0xb6a94  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6a99  ldstr    aLocidAttrutlCa// "LOCID_ATTRUTL_CANTDELSYSATTR"
0xb6a9e  ldarg.0
0xb6a9f  ldstr    aAttributeutilM// "AttributeUtil.Messages.CannotDeleteSyst"...
0xb6aa4  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6aa9  ldc.i4.0
0xb6aaa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6aaf  ldstr    aPhoneticbaseds// "PhoneticBasedSearch"
0xb6ab4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb6ab9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb6abe  brtrue.s loc_B6ADE
0xb6ac0  ldarg.0
0xb6ac1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6ac6  ldstr    aLocidAttrutlCo// "LOCID_ATTRUTL_CONFIRMDELATTR"
0xb6acb  ldarg.0
0xb6acc  ldstr    aAttributeutilM_0// "AttributeUtil.Messages.ConfirmAttribute"...
0xb6ad1  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6ad6  ldc.i4.0
0xb6ad7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6adc  br.s     loc_B6AFA
0xb6ade  ldarg.0
0xb6adf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6ae4  ldstr    aLocidAttrutlCo// "LOCID_ATTRUTL_CONFIRMDELATTR"
0xb6ae9  ldarg.0
0xb6aea  ldstr    aAttributeutilM_1// "AttributeUtil.Messages.ConfirmAttribute"...
0xb6aef  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6af4  ldc.i4.0
0xb6af5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6afa  ldarg.0
0xb6afb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6b00  ldstr    aLocidAttrutlCr// "LOCID_ATTRUTL_CREATINGATTR"
0xb6b05  ldarg.0
0xb6b06  ldstr    aAttributeutilM_2// "AttributeUtil.Messages.CreatingAttribut"...
0xb6b0b  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6b10  ldc.i4.0
0xb6b11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6b16  ldarg.0
0xb6b17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6b1c  ldstr    aLocidAttrutlDe// "LOCID_ATTRUTL_DELETINGATTR"
0xb6b21  ldarg.0
0xb6b22  ldstr    aAttributeutilM_3// "AttributeUtil.Messages.DeletingAttribut"...
0xb6b27  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6b2c  ldc.i4.0
0xb6b2d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6b32  ldarg.0
0xb6b33  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6b38  ldstr    aLocidAttrutlUp// "LOCID_ATTRUTL_UPDATINGATTR"
0xb6b3d  ldarg.0
0xb6b3e  ldstr    aAttributeutilM_4// "AttributeUtil.Messages.UpdatingAttribut"...
0xb6b43  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6b48  ldc.i4.0
0xb6b49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6b4e  ldarg.0
0xb6b4f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6b54  ldstr    aLocidAttrutlEm// "LOCID_ATTRUTL_EMPTYSTATUS"
0xb6b59  ldarg.0
0xb6b5a  ldstr    aAttributeutilE// "AttributeUtil.Errors.EmptyStatusReason"
0xb6b5f  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6b64  ldc.i4.0
0xb6b65  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6b6a  ldarg.0
0xb6b6b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6b70  ldstr    aStaticToolsSys_32// "/_static/tools/systemcustomization/attr"...
0xb6b75  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xb6b7a  ldarg.0
0xb6b7b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6b80  ldstr    aLocidManattrRe// "LOCID_MANATTR_REVERSEDMINMAX"
0xb6b85  ldarg.0
0xb6b86  ldstr    aManageattribut_3// "ManageAttributePage.Errors.ReversedMinM"...
0xb6b8b  call     instance string Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::GetSCString(string name)
0xb6b90  ldc.i4.0
0xb6b91  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xb6b96  ldarg.0
0xb6b97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6b9c  ldstr    aBcreate// "_bCreate"
0xb6ba1  ldarg.0
0xb6ba2  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_mode
0xb6ba7  ldc.i4.0
0xb6ba8  ceq
0xb6baa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xb6baf  ldarg.0
0xb6bb0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6bb5  ldstr    aBisattribute// "_bIsAttribute"
0xb6bba  ldc.i4.1
0xb6bbb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xb6bc0  ldarg.0
0xb6bc1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6bc6  ldstr    aBiscustomattri// "_bIsCustomAttribute"
0xb6bcb  ldarg.0
0xb6bcc  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb6bd1  brtrue.s loc_B6BDA
0xb6bd3  ldstr    aTrue_0// "true"
0xb6bd8  br.s     loc_B6BEE
0xb6bda  ldarg.0
0xb6bdb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb6be0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsCustomField()
0xb6be5  stloc.s  4
0xb6be7  ldloca.s 4
0xb6be9  call     instance string [mscorlib]System.Boolean::ToString()
0xb6bee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xb6bf3  ldarg.0
0xb6bf4  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xb6bf9  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xb6bfe  ldstr    aEntityid_1// "entityId"
0xb6c03  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xb6c08  stloc.0
0xb6c09  ldarg.0
0xb6c0a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6c0f  ldstr    aEntityid_1// "entityId"
0xb6c14  ldloc.0
0xb6c15  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xb6c1a  ldarg.0
0xb6c1b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6c20  ldstr    aIsvirtualentit// "_isVirtualEntity"
0xb6c25  ldarg.0
0xb6c26  ldfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_isVirtualEntity
0xb6c2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xb6c30  ldarg.0
0xb6c31  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6c36  ldstr    aIsdatasourceen// "_isDataSourceEntity"
0xb6c3b  ldarg.0
0xb6c3c  ldfld    bool Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_isDataSourceEntity
0xb6c41  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xb6c46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xb6c4b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xb6c50  stloc.1
0xb6c51  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0xb6c56  ldloc.1
0xb6c57  ldloc.1
0xb6c58  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xb6c5d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0xb6c62  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_PricingDecimalPrecision()
0xb6c67  stloc.2
0xb6c68  ldarg.0
0xb6c69  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6c6e  ldstr    aPricingdecimal_0// "_pricingDecimalPrecision"
0xb6c73  ldloc.2
0xb6c74  conv.i8
0xb6c75  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xb6c7a  ldarg.0
0xb6c7b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6c80  ldstr    aBview// "_bView"
0xb6c85  ldarg.0
0xb6c86  ldfld    valuetype Mode Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_mode
0xb6c8b  ldc.i4.2
0xb6c8c  ceq
0xb6c8e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xb6c93  ldarg.0
0xb6c94  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xb6c99  ldstr    aSattributeid// "_sAttributeId"
0xb6c9e  ldarg.0
0xb6c9f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb6ca4  brtrue.s loc_B6CAD
0xb6ca6  ldsfld   string [mscorlib]System.String::Empty
0xb6cab  br.s     loc_B6CBD
0xb6cad  ldarg.0
0xb6cae  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Web.Tools.SystemCustomization.Attributes.ManageAttributePage::_attributeMD
0xb6cb3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0xb6cb8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0xb6cbd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
  ... truncated ...
```
