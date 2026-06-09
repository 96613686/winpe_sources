# Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::ConfigurePage

- ea: `0x84470`
- end: `0x84dd8`
- name: `Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::ConfigurePage`
- size: `2408`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x84470`
- `0x84de0`
- `0x84e60`
- `0x85090`
- `0x851c0`
- `0x851e0`
- `0x85320`
- `0x85360`

## string_xrefs

- `0x8449c`: `/_static/_common/styles/AutoToolTip.js`
- `0x8447c`: `/_common/styles/select.css.aspx`
- `0x84639`: `/Tools/AutoNumbering/cmds/cmd_update.aspx`
- `0x84ac3`: `_autoNumberTemplate`
- `0x84ae3`: `_autoNumberTemplateSuffix`

## pseudocode

```c

```

## disassembly

```asm
0x84470  ldarg.0
0x84471  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x84476  ldarg.0
0x84477  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8447c  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0x84481  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x84486  ldarg.0
0x84487  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8448c  ldstr    aStaticToolsSys_1// "/_static/tools/systemcustomization/scri"...
0x84491  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x84496  ldarg.0
0x84497  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8449c  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x844a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x844a6  ldarg.0
0x844a7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x844ac  ldstr    aLocidSyscustCa// "LOCID_SYSCUST_CANTBEBLANK"
0x844b1  ldarg.0
0x844b2  ldstr    aValidationErro// "Validation.Errors.CannotBeBlank"
0x844b7  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetSCString(string name)
0x844bc  ldc.i4.0
0x844bd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x844c2  ldarg.0
0x844c3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x844c8  ldstr    aLocidSyscustIn// "LOCID_SYSCUST_INVALCHARS"
0x844cd  ldarg.0
0x844ce  ldstr    aValidationErro_0// "Validation.Errors.CannotHaveInvalidChar"...
0x844d3  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetSCString(string name)
0x844d8  ldc.i4.0
0x844d9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x844de  ldarg.0
0x844df  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x844e4  ldstr    aLocidSyscustAl// "LOCID_SYSCUST_ALPHANUMSONLY"
0x844e9  ldarg.0
0x844ea  ldstr    aValidationErro_1// "Validation.Errors.CanOnlyHaveAlphaNumer"...
0x844ef  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetSCString(string name)
0x844f4  ldc.i4.0
0x844f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x844fa  ldarg.0
0x844fb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84500  ldstr    aLocidSelectbox// "LOCID_SELECTBOX_BUTTON_ALT"
0x84505  ldarg.0
0x84506  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8450b  ldstr    aSelectButtonAl// "Select.Button.AltTag"
0x84510  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84515  ldc.i4.0
0x84516  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8451b  ldarg.0
0x8451c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84521  ldstr    aLocidAutonumCn// "LOCID_AUTONUM_CNTPFXLBL"
0x84526  ldarg.0
0x84527  ldstr    a163// "163"
0x8452c  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x84531  ldc.i4.0
0x84532  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x84537  ldarg.0
0x84538  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8453d  ldstr    aLocidAutonumCs// "LOCID_AUTONUM_CSPFXLBL"
0x84542  ldarg.0
0x84543  ldstr    a186// "186"
0x84548  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x8454d  ldc.i4.0
0x8454e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x84553  ldarg.0
0x84554  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84559  ldstr    aLocidAutonumKb// "LOCID_AUTONUM_KBAPFXLBL"
0x8455e  ldarg.0
0x8455f  ldstr    a222// "222"
0x84564  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x84569  ldc.i4.0
0x8456a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8456f  ldarg.0
0x84570  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84575  ldstr    aLocidAutonumKa// "LOCID_AUTONUM_KAPFXLBL"
0x8457a  ldarg.0
0x8457b  ldstr    a345// "345"
0x84580  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x84585  ldc.i4.0
0x84586  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x8458b  ldarg.0
0x8458c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84591  ldstr    aLocidAutonumQt// "LOCID_AUTONUM_QTPFXLBL"
0x84596  ldarg.0
0x84597  ldstr    a246// "246"
0x8459c  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x845a1  ldc.i4.0
0x845a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x845a7  ldarg.0
0x845a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x845ad  ldstr    aLocidAutonumOr// "LOCID_AUTONUM_ORDPFXLBL"
0x845b2  ldarg.0
0x845b3  ldstr    a282// "282"
0x845b8  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x845bd  ldc.i4.0
0x845be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x845c3  ldarg.0
0x845c4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x845c9  ldstr    aLocidAutonumIn// "LOCID_AUTONUM_INVPFXLBL"
0x845ce  ldarg.0
0x845cf  ldstr    a318// "318"
0x845d4  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x845d9  ldc.i4.0
0x845da  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x845df  ldarg.0
0x845e0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x845e5  ldstr    aLocidAutonumCm// "LOCID_AUTONUM_CMPPFXLBL"
0x845ea  ldarg.0
0x845eb  ldstr    a163// "163"
0x845f0  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x845f5  ldc.i4.0
0x845f6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x845fb  ldarg.0
0x845fc  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84601  ldstr    aLocidAutonumCa// "LOCID_AUTONUM_CAFXLBL"
0x84606  ldarg.0
0x84607  ldstr    a420// "420"
0x8460c  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x84611  ldc.i4.0
0x84612  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x84617  ldarg.0
0x84618  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8461d  ldstr    aLocidAutonumCn_0// "LOCID_AUTONUM_CNFRMDROPSFX"
0x84622  ldarg.0
0x84623  ldstr    a84// "84"
0x84628  call     instance string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::GetString(string name)
0x8462d  ldc.i4.0
0x8462e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x84633  ldarg.0
0x84634  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84639  ldstr    aToolsAutonumbe// "/Tools/AutoNumbering/cmds/cmd_update.as"...
0x8463e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x84643  ldarg.0
0x84644  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsCRMOrganization()
0x84649  stfld    bool Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::isCRMOrg
0x8464e  ldarg.0
0x8464f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x84654  ldstr    aIscrmorg// "isCRMOrg"
0x84659  ldarg.0
0x8465a  ldfld    bool Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::isCRMOrg
0x8465f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x84664  ldarg.0
0x84665  call     instance void Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::InitDefaultValues()
0x8466a  ldstr    aOrganization_0// "organization"
0x8466f  ldarg.0
0x84670  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentUser()
0x84675  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x8467a  ldc.i4.0
0x8467b  newarr   [mscorlib]System.String
0x84680  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x84685  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8468a  stloc.0
0x8468b  ldarg.0
0x8468c  ldloc.0
0x8468d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x84692  call     instance void Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::InitValues(string dataXml)
0x84697  ldarg.0
0x84698  ldfld    bool Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::isCRMOrg
0x8469d  brfalse  loc_8478F
0x846a2  ldarg.0
0x846a3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x846a8  ldc.i4   0x3F2
0x846ad  ldc.i4.2
0x846ae  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x846b3  ldstr    aTab0// "tab0"
0x846b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x846bd  ldarg.0
0x846be  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x846c3  ldc.i4.s 0x70
0x846c5  ldc.i4.2
0x846c6  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x846cb  ldstr    aTab1// "tab1"
0x846d0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x846d5  ldarg.0
0x846d6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x846db  ldc.i4   0x43C
0x846e0  ldc.i4.2
0x846e1  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x846e6  ldstr    aTab3// "tab3"
0x846eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x846f0  ldarg.0
0x846f1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x846f6  ldc.i4   0x440
0x846fb  ldc.i4.2
0x846fc  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x84701  ldstr    aTab4// "tab4"
0x84706  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x8470b  ldarg.0
0x8470c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x84711  ldc.i4   0x442
0x84716  ldc.i4.2
0x84717  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x8471c  ldstr    aTab5// "tab5"
0x84721  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x84726  ldarg.0
0x84727  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x8472c  ldc.i4   0x1130
0x84731  ldc.i4.2
0x84732  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x84737  ldstr    aTab6// "tab6"
0x8473c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x84741  ldarg.0
0x84742  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x84747  ldc.i4.s 0x7F
0x84749  ldc.i4.2
0x8474a  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x8474f  ldstr    aTab2// "tab2"
0x84754  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x84759  ldarg.0
0x8475a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x8475f  ldc.i4   0x26E7
0x84764  ldc.i4.2
0x84765  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x8476a  ldstr    aTab7// "tab7"
0x8476f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x84774  ldarg.0
0x84775  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppTabBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmTabBar
0x8477a  ldc.i4   0x26E1
0x8477f  ldc.i4.2
0x84780  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x84785  ldstr    aTab8// "tab8"
0x8478a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.TabBar::AddTab(string, string)
0x8478f  ldarg.0
0x84790  ldfld    bool Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::isCRMOrg
0x84795  brfalse  loc_84A40
0x8479a  ldarg.0
0x8479b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::ContractsLengthSuffix
0x847a0  ldarg.0
0x847a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x847a6  ldstr    aPicklistAutonu// "PickList_AutoNumberSuffixLength_Value_4"
0x847ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x847b0  ldstr    a4// "4"
0x847b5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x847ba  ldarg.0
0x847bb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::ContractsLengthSuffix
0x847c0  ldarg.0
0x847c1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x847c6  ldstr    aPicklistAutonu_0// "PickList_AutoNumberSuffixLength_Value_5"
0x847cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x847d0  ldstr    a5// "5"
0x847d5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x847da  ldarg.0
0x847db  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::ContractsLengthSuffix
0x847e0  ldarg.0
0x847e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x847e6  ldstr    aPicklistAutonu_1// "PickList_AutoNumberSuffixLength_Value_6"
0x847eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x847f0  ldstr    a6_0// "6"
0x847f5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x847fa  ldarg.0
0x847fb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::ContractsLengthSuffix
0x84800  ldarg.0
0x84801  ldfld    string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::_suffixLength
0x84806  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x8480b  ldarg.0
0x8480c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::CasesLengthSuffix
0x84811  ldarg.0
0x84812  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x84817  ldstr    aPicklistAutonu// "PickList_AutoNumberSuffixLength_Value_4"
0x8481c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84821  ldstr    a4// "4"
0x84826  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x8482b  ldarg.0
0x8482c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::CasesLengthSuffix
0x84831  ldarg.0
0x84832  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x84837  ldstr    aPicklistAutonu_0// "PickList_AutoNumberSuffixLength_Value_5"
0x8483c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84841  ldstr    a5// "5"
0x84846  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x8484b  ldarg.0
0x8484c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::CasesLengthSuffix
0x84851  ldarg.0
0x84852  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x84857  ldstr    aPicklistAutonu_1// "PickList_AutoNumberSuffixLength_Value_6"
0x8485c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84861  ldstr    a6_0// "6"
0x84866  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x8486b  ldarg.0
0x8486c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::CasesLengthSuffix
0x84871  ldarg.0
0x84872  ldfld    string Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::_suffixLength
0x84877  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x8487c  ldarg.0
0x8487d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::QuotesLengthSuffix
0x84882  ldarg.0
0x84883  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x84888  ldstr    aPicklistAutonu// "PickList_AutoNumberSuffixLength_Value_4"
0x8488d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84892  ldstr    a4// "4"
0x84897  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x8489c  ldarg.0
0x8489d  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::QuotesLengthSuffix
0x848a2  ldarg.0
0x848a3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x848a8  ldstr    aPicklistAutonu_0// "PickList_AutoNumberSuffixLength_Value_5"
0x848ad  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x848b2  ldstr    a5// "5"
0x848b7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x848bc  ldarg.0
0x848bd  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Web.Tools.AutoNumbering.AutoNumberingPage::QuotesLengthSuffix
  ... truncated ...
```
