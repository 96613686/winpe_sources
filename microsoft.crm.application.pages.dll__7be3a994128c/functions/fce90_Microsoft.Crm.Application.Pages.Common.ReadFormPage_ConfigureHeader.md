# Microsoft.Crm.Application.Pages.Common.ReadFormPage::ConfigureHeader

- ea: `0xfce90`
- end: `0xfd57a`
- name: `Microsoft.Crm.Application.Pages.Common.ReadFormPage::ConfigureHeader`
- size: `1770`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0xffef0`

## callees

- `0xcaf50`
- `0xcb3f0`
- `0xfc340`
- `0xfc360`
- `0xfc810`
- `0xfcc20`
- `0xfce80`
- `0xfce90`
- `0xfd580`
- `0xfd660`
- `0xfd680`
- `0xfd6a0`
- `0xfd790`
- `0xfd830`
- `0xfd900`
- `0xfd920`
- `0xfdac0`
- `0xfdbb0`
- `0xfdd40`

## string_xrefs

- `0xfcf54`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xfcfb4`: `/_static/_common/scripts/jquery_ui_1.8.21.min.js`
- `0xfd56f`: `/_static/_common/scripts/CommandBarActions.js`
- `0xfcef6`: `/_static/_common/scripts/Performance.js`
- `0xfd024`: `ProductFamilyQuickCreate.DisplayName`
- `0xfd55f`: `/_static/_common/scripts/RibbonActions.js`
- `0xfd260`: `_CreateFromId`
- `0xfcf34`: `/_controls/CompositeControl/CompositeControl.css.aspx`
- `0xfced6`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xfcf44`: `/_static/_common/scripts/SalesCommonImported.js`
- `0xfcec6`: `/_static/_controls/ReadForm/ReadFormUtilities.js`
- `0xfcf17`: `/_forms/styles/read.css.aspx`
- `0xfd11f`: `ReadForm_UnSupported_Action_Message`
- `0xfd135`: `_readFormTitleMask`
- `0xfd154`: `_readForm`
- `0xfd206`: `CreateChildCase.DisplayName`
- `0xfd391`: `_globalQuickCreate`
- `0xfd4f8`: `Mscrm.Utilities.initializeReadForm();`

## pseudocode

```c

```

## disassembly

```asm
0xfce90  ldarg.0
0xfce91  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfce96  ldc.i4.1
0xfce97  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQuery(bool)
0xfce9c  ldarg.0
0xfce9d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcea2  ldc.i4.1
0xfcea3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJQueryTemplate(bool)
0xfcea8  ldarg.0
0xfcea9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfceae  ldc.i4.1
0xfceaf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadRefreshFormInit(bool)
0xfceb4  ldarg.0
0xfceb5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfceba  ldc.i4.1
0xfcebb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_LoadJSRender(bool)
0xfcec0  ldarg.0
0xfcec1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcec6  ldstr    aStaticControls_35// "/_static/_controls/ReadForm/ReadFormUti"...
0xfcecb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfced0  ldarg.0
0xfced1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfced6  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0xfcedb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfcee0  ldarg.0
0xfcee1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcee6  ldstr    aStaticFormsFor_0// "/_static/_forms/Form.js"
0xfceeb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfcef0  ldarg.0
0xfcef1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xfcef6  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/Performance.js"
0xfcefb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfcf00  ldarg.0
0xfcf01  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder Microsoft.Crm.Application.Pages.Common.ReadFormPage::_dataBuilder
0xfcf06  brtrue.s loc_FCF09
0xfcf08  ret
0xfcf09  ldarg.0
0xfcf0a  call     instance bool Microsoft.Crm.Application.Pages.Common.ReadFormPage::get_IsMobileForm()
0xfcf0f  brtrue.s loc_FCF76
0xfcf11  ldarg.0
0xfcf12  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcf17  ldstr    aFormsStylesRea// "/_forms/styles/read.css.aspx"
0xfcf1c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xfcf21  ldarg.0
0xfcf22  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder Microsoft.Crm.Application.Pages.Common.ReadFormPage::_dataBuilder
0xfcf27  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_ShowGlobalQuickCreate()
0xfcf2c  brtrue.s loc_FCF60
0xfcf2e  ldarg.0
0xfcf2f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcf34  ldstr    aControlsCompos// "/_controls/CompositeControl/CompositeCo"...
0xfcf39  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xfcf3e  ldarg.0
0xfcf3f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcf44  ldstr    aStaticCommonSc_29// "/_static/_common/scripts/SalesCommonImp"...
0xfcf49  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfcf4e  ldarg.0
0xfcf4f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcf54  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xfcf59  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfcf5e  br.s     loc_FCF70
0xfcf60  ldarg.0
0xfcf61  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcf66  ldstr    aControlsRefres_0// "/_controls/RefreshForm/flyoutdialog.css"...
0xfcf6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xfcf70  ldarg.0
0xfcf71  call     instance void Microsoft.Crm.Application.Pages.Common.ReadFormPage::ConfigureActivityFeedsHeader()
0xfcf76  ldarg.0
0xfcf77  ldarg.0
0xfcf78  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder Microsoft.Crm.Application.Pages.Common.ReadFormPage::_dataBuilder
0xfcf7d  callvirt instance class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity> [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_CurrentEntity()
0xfcf82  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Value()
0xfcf87  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xfcf8c  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xfcf91  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfcf96  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsRefreshEnabledForEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xfcf9b  stfld    bool Microsoft.Crm.Application.Pages.Common.ReadFormPage::_isFormModeRefresh
0xfcfa0  ldarg.0
0xfcfa1  call     instance void Microsoft.Crm.Application.Pages.Common.ReadFormPage::AddPreloadedStylesToHeader()
0xfcfa6  ldarg.0
0xfcfa7  ldfld    bool Microsoft.Crm.Application.Pages.Common.ReadFormPage::_isFormModeRefresh
0xfcfac  brfalse.s loc_FCFD4
0xfcfae  ldarg.0
0xfcfaf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcfb4  ldstr    aStaticCommonSc_1// "/_static/_common/scripts/jquery_ui_1.8."...
0xfcfb9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xfcfbe  ldarg.0
0xfcfbf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcfc4  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xfcfc9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xfcfce  ldarg.0
0xfcfcf  call     instance void Microsoft.Crm.Application.Pages.Common.ReadFormPage::ConfigureProcessControlHeader()
0xfcfd4  ldarg.0
0xfcfd5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0xfcfda  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xfcfdf  callvirt instance string [mscorlib]System.Object::ToString()
0xfcfe4  ldstr    aProduct_0// "Product"
0xfcfe9  ldc.i4.5
0xfcfea  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0xfcfef  brfalse  loc_FD0B4
0xfcff4  ldarg.0
0xfcff5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfcffa  ldstr    aLocidProductBu// "LOCID_PRODUCT_BUNDLE_FORM_TITLE"
0xfcfff  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd004  ldstr    aProductBundleF// "Product_Bundle_Form_Title"
0xfd009  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd00e  ldc.i4.0
0xfd00f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xfd014  ldarg.0
0xfd015  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd01a  ldstr    aLocidProductfa// "LOCID_PRODUCTFAMILY_TITLE"
0xfd01f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd024  ldstr    aProductfamilyq// "ProductFamilyQuickCreate.DisplayName"
0xfd029  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd02e  ldc.i4.0
0xfd02f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xfd034  ldarg.0
0xfd035  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd03a  ldstr    aLocidProductfa_0// "LOCID_PRODUCTFAMILY_TITLE_PREFIX"
0xfd03f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd044  ldstr    aObjectSingular// "Object_Singular_Product_Family"
0xfd049  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd04e  ldc.i4.0
0xfd04f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xfd054  ldarg.0
0xfd055  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd05a  ldstr    aLocidProductbu// "LOCID_PRODUCTBUNDLE_TITLE_PREFIX"
0xfd05f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd064  ldstr    aObjectSingular_1// "Object_Singular_Bundle"
0xfd069  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd06e  ldc.i4.0
0xfd06f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xfd074  ldarg.0
0xfd075  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd07a  ldstr    aLocidProductTi// "LOCID_PRODUCT_TITLE_PREFIX"
0xfd07f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd084  ldstr    aObjectSingular_0// "Object_Singular_Product"
0xfd089  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd08e  ldc.i4.0
0xfd08f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xfd094  ldarg.0
0xfd095  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd09a  ldstr    aLocidKitTitleP// "LOCID_KIT_TITLE_PREFIX"
0xfd09f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd0a4  ldstr    aObjectSingular_8// "Object_Singular_Kit"
0xfd0a9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd0ae  ldc.i4.0
0xfd0af  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xfd0b4  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.HelpUtility::GetHelpServerUri()
0xfd0b9  stloc.0
0xfd0ba  ldarg.0
0xfd0bb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd0c0  ldstr    aHelpServerUrl// "HELP_SERVER_URL"
0xfd0c5  ldloc.0
0xfd0c6  ldnull
0xfd0c7  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0xfd0cc  brtrue.s loc_FD0D5
0xfd0ce  ldsfld   string [mscorlib]System.String::Empty
0xfd0d3  br.s     loc_FD0DB
0xfd0d5  ldloc.0
0xfd0d6  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xfd0db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xfd0e0  ldarg.0
0xfd0e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd0e6  ldstr    aHelpRedirectAv// "HELP_REDIRECT_AVAILABLE"
0xfd0eb  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.HelpUtility::get_IsHelpRedirectAvailable()
0xfd0f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xfd0f5  ldarg.0
0xfd0f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd0fb  ldstr    aApplicationFul// "APPLICATION_FULL_VERSION"
0xfd100  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0xfd105  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_FullVersion()
0xfd10a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xfd10f  ldarg.0
0xfd110  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd115  ldstr    aLocidRoUnsuppo// "LOCID_RO_UNSUPPORTED_ACTION"
0xfd11a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd11f  ldstr    aReadformUnsupp// "ReadForm_UnSupported_Action_Message"
0xfd124  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd129  ldc.i4.0
0xfd12a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xfd12f  ldarg.0
0xfd130  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd135  ldstr    aReadformtitlem// "_readFormTitleMask"
0xfd13a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd13f  ldstr    aFormTitleMask// "Form_Title_Mask"
0xfd144  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd149  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xfd14e  ldarg.0
0xfd14f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd154  ldstr    aReadform_1// "_readForm"
0xfd159  ldc.i4.1
0xfd15a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xfd15f  ldarg.0
0xfd160  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd165  ldstr    aIspreviewform// "_isPreviewForm"
0xfd16a  ldarg.0
0xfd16b  ldfld    bool Microsoft.Crm.Application.Pages.Common.ReadFormPage::_isPreviewForm
0xfd170  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xfd175  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0xfd17a  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xfd17f  callvirt instance int32 [mscorlib]System.Globalization.NumberFormatInfo::get_CurrencyPositivePattern()
0xfd184  stloc.1
0xfd185  ldarg.0
0xfd186  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd18b  ldstr    aSymbolpoistion// "SYMBOLPOISTION_CURRENCY"
0xfd190  ldloc.1
0xfd191  brfalse.s loc_FD199
0xfd193  ldloc.1
0xfd194  ldc.i4.2
0xfd195  ceq
0xfd197  br.s     loc_FD19A
0xfd199  ldc.i4.1
0xfd19a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xfd19f  ldarg.0
0xfd1a0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd1a5  ldstr    aUserGuid// "USER_GUID"
0xfd1aa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0xfd1af  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_CurrentUserInformation()
0xfd1b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0xfd1b9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, valuetype [mscorlib]System.Guid)
0xfd1be  ldarg.0
0xfd1bf  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd1c4  ldstr    aUserName// "USER_NAME"
0xfd1c9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0xfd1ce  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UserName()
0xfd1d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xfd1d8  ldarg.0
0xfd1d9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder Microsoft.Crm.Application.Pages.Common.ReadFormPage::_dataBuilder
0xfd1de  callvirt instance class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity> [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::get_CurrentEntity()
0xfd1e3  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Value()
0xfd1e8  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0xfd1ed  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xfd1f2  ldc.i4.s 0x70
0xfd1f4  bne.un.s loc_FD215
0xfd1f6  ldarg.0
0xfd1f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd1fc  ldstr    aIncidentDispla// "INCIDENT_DISPLAYNAME"
0xfd201  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xfd206  ldstr    aCreatechildcas// "CreateChildCase.DisplayName"
0xfd20b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xfd210  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xfd215  ldarg.0
0xfd216  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder Microsoft.Crm.Application.Pages.Common.ReadFormPage::_dataBuilder
0xfd21b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xfd220  ldarg.0
0xfd221  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfd226  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfd22b  newobj   instance void Microsoft.Crm.Application.Pages.Common.EntityDataHelper::.ctor(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder dataBuilder, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext, class [System]System.Collections.Specialized.NameValueCollection pageParameters)
0xfd230  stloc.2
0xfd231  ldarg.0
0xfd232  ldfld    bool Microsoft.Crm.Application.Pages.Common.ReadFormPage::_isPreviewForm
0xfd237  brtrue.s loc_FD28D
0xfd239  ldarg.0
0xfd23a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfd23f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfd244  ldstr    aId// "id"
0xfd249  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfd24e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xfd253  brfalse.s loc_FD28D
0xfd255  ldarg.0
0xfd256  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfd25b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfd260  ldstr    aCreatefromid// "_CreateFromId"
0xfd265  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfd26a  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xfd26f  brfalse.s loc_FD28D
0xfd271  ldarg.0
0xfd272  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xfd277  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xfd27c  ldstr    aSearchtext// "_searchText"
0xfd281  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xfd286  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xfd28b  brtrue.s loc_FD29B
0xfd28d  ldloc.2
0xfd28e  ldarg.0
0xfd28f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd294  callvirt instance void Microsoft.Crm.Application.Pages.Common.EntityDataHelper::SetClientVars(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager headerControl)
0xfd299  br.s     loc_FD2C7
0xfd29b  ldarg.0
0xfd29c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd2a1  ldstr    aShouldrequeste// "ShouldRequestEntityData"
0xfd2a6  ldc.i4.1
0xfd2a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xfd2ac  ldarg.0
0xfd2ad  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd2b2  ldstr    aEntitydataurl// "EntityDataUrl"
0xfd2b7  ldloc.2
0xfd2b8  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Pages.Common.EntityDataHelper::GetEntityDataUri()
0xfd2bd  callvirt instance string [mscorlib]System.Object::ToString()
0xfd2c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xfd2c7  ldarg.0
0xfd2c8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd2cd  ldstr    aSubjectlookupd// "_subjectLookupData"
0xfd2d2  ldarg.0
0xfd2d3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder Microsoft.Crm.Application.Pages.Common.ReadFormPage::_dataBuilder
0xfd2d8  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.ReadFormDataBuilder::CheckForSubjectLookup()
0xfd2dd  brtrue.s loc_FD2E6
0xfd2df  ldstr    asc_11EF2A// ""
0xfd2e4  br.s     loc_FD2F5
0xfd2e6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.IServiceLookupAttributeMetadataFormatter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.MetadataHelper::get_ServiceLookupAttributeMetadataFormatter()
  ... truncated ...
```
