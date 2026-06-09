# Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigurePage

- ea: `0x53df0`
- end: `0x5413a`
- name: `Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigurePage`
- size: `842`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x53df0`
- `0x54140`
- `0x54210`
- `0x54390`
- `0x54680`
- `0x546f0`
- `0x54790`
- `0x54850`
- `0x548f0`
- `0x54940`
- `0x549c0`
- `0x54a60`
- `0x54ad0`
- `0x54b30`
- `0x54b90`
- `0xd6830`

## string_xrefs

- `0x53e9a`: `/_common/styles/Dialogs.css.aspx`
- `0x53ebb`: `/_static/_controls/SolutionComponentFilter/SolutionComponentFilter.js`
- `0x53e1d`: `selectedComponentType`
- `0x53f1f`: `ProcessControl.Configurator.ErrorBackButtonText`

## pseudocode

```c

```

## disassembly

```asm
0x53df0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::LoadMetadataCache()
0x53df5  stloc.0
0x53df6  ldarg.0
0x53df7  ldarg.0
0x53df8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53dfd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53e02  ldstr    aEntityid// "entityid"
0x53e07  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53e0c  stfld    string Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityId
0x53e11  ldarg.0
0x53e12  ldarg.0
0x53e13  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53e18  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53e1d  ldstr    aSelectedcompon// "selectedComponentType"
0x53e22  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53e27  call     int32 [mscorlib]System.Int32::Parse(string)
0x53e2c  stfld    int32 Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::selectedComponentType
0x53e31  ldarg.0
0x53e32  ldarg.0
0x53e33  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53e38  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53e3d  ldstr    aTotalentitypag// "totalEntityPageCount"
0x53e42  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53e47  call     int32 [mscorlib]System.Int32::Parse(string)
0x53e4c  stfld    int32 Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::totalEntityPageCount
0x53e51  ldarg.0
0x53e52  ldarg.0
0x53e53  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53e58  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53e5d  ldstr    aEntitypageinde// "entityPageIndex"
0x53e62  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53e67  call     int32 [mscorlib]System.Int32::Parse(string)
0x53e6c  stfld    int32 Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::entityPageIndex
0x53e71  ldarg.0
0x53e72  ldloc.0
0x53e73  ldarg.0
0x53e74  ldfld    string Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityId
0x53e79  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x53e7e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x53e83  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityMD
0x53e88  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x53e8d  stloc.1
0x53e8e  ldarg.0
0x53e8f  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x53e94  ldarg.0
0x53e95  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x53e9a  ldstr    aCommonStylesDi_0// "/_common/styles/Dialogs.css.aspx"
0x53e9f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x53ea4  ldarg.0
0x53ea5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x53eaa  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x53eaf  ldnull
0x53eb0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x53eb5  ldarg.0
0x53eb6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x53ebb  ldstr    aStaticControls_19// "/_static/_controls/SolutionComponentFil"...
0x53ec0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x53ec5  ldarg.0
0x53ec6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53ecb  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53ed0  ldstr    aShownextbutton// "showNextButton"
0x53ed5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53eda  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53edf  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x53ee4  stloc.2
0x53ee5  ldarg.0
0x53ee6  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x53eeb  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x53ef0  stloc.3
0x53ef1  ldloc.3
0x53ef2  ldc.i4.0
0x53ef3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x53ef8  ldarg.0
0x53ef9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x53efe  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x53f03  ldstr    aShowbackbutton// "showBackButton"
0x53f08  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x53f0d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x53f12  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x53f17  brfalse.s loc_53F2F
0x53f19  ldloc.3
0x53f1a  ldstr    aButback// "butBack"
0x53f1f  ldstr    aProcesscontrol// "ProcessControl.Configurator.ErrorBackBu"...
0x53f24  ldstr    aIfMscrmUtiliti_2// "if(!Mscrm.Utilities.resetValidationFail"...
0x53f29  ldc.i4.0
0x53f2a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool)
0x53f2f  ldloc.3
0x53f30  ldstr    aButbegin// "butBegin"
0x53f35  ldloc.2
0x53f36  brtrue.s loc_53F3F
0x53f38  ldstr    aWizardButtonTe// "Wizard_Button_Text_Tooltip_Finish"
0x53f3d  br.s     loc_53F44
0x53f3f  ldstr    aWebNavtourNext// "Web.NavTour.NextButton"
0x53f44  ldstr    aIfMscrmUtiliti_3// "if(!Mscrm.Utilities.resetValidationFail"...
0x53f49  ldc.i4.0
0x53f4a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool)
0x53f4f  ldloc.3
0x53f50  ldstr    aCmddialogcance// "cmdDialogCancel"
0x53f55  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x53f5a  ldstr    aCancel// "cancel();"
0x53f5f  ldc.i4.0
0x53f60  ldc.i4.2
0x53f61  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x53f66  ldarg.0
0x53f67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x53f6c  ldstr    aLocidEntityId// "LOCID_ENTITY_ID"
0x53f71  ldarg.0
0x53f72  ldfld    string Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityId
0x53f77  ldc.i4.0
0x53f78  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53f7d  ldarg.0
0x53f7e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x53f83  ldarg.0
0x53f84  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x53f89  ldc.i4.0
0x53f8a  call     void Microsoft.Crm.Application.Pages.tools.SystemCustomization.Common.SegmentationUtility::SetSegmentationHeaders(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header currentHeader, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager currentResourceManager, [opt] bool skipSubcomponentTypes)
0x53f8f  ldarg.0
0x53f90  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x53f95  ldstr    aLocidTotalEnti// "LOCID_TOTAL_ENTITY_PAGE_COUNT"
0x53f9a  ldarg.0
0x53f9b  ldflda   int32 Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::totalEntityPageCount
0x53fa0  call     instance string [mscorlib]System.Int32::ToString()
0x53fa5  ldc.i4.0
0x53fa6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x53fab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x53fb0  ldstr    aSolutionsegmen// "SolutionSegmentation.EntitySelectedCoun"...
0x53fb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x53fba  ldarg.0
0x53fbb  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityMD
0x53fc0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0x53fc5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x53fca  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x53fcf  ldloc.1
0x53fd0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x53fd5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x53fda  ldarg.0
0x53fdb  ldflda   int32 Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::entityPageIndex
0x53fe0  call     instance string [mscorlib]System.Int32::ToString()
0x53fe5  ldarg.0
0x53fe6  ldflda   int32 Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::totalEntityPageCount
0x53feb  call     instance string [mscorlib]System.Int32::ToString()
0x53ff0  call     string [mscorlib]System.String::Format(string, object, object, object)
0x53ff5  stloc.s  4
0x53ff7  ldarg.0
0x53ff8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x53ffd  ldstr    aLocidTitleDial// "LOCID_TITLE_DIALOG"
0x54002  ldloc.s  4
0x54004  ldc.i4.0
0x54005  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x5400a  ldarg.0
0x5400b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityMD
0x54010  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsManaged()
0x54015  ldc.i4.0
0x54016  ceq
0x54018  stloc.s  5
0x5401a  ldarg.0
0x5401b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x54020  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x54025  ldstr    aSolutionid_0// "solutionId"
0x5402a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5402f  stloc.s  6
0x54031  ldarg.0
0x54032  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::chkSelectEntityMetadata
0x54037  ldc.i4.1
0x54038  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::set_Checked(bool)
0x5403d  ldloc.s  6
0x5403f  ldarg.0
0x54040  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityMD
0x54045  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x5404a  stloc.s  7
0x5404c  ldloca.s 7
0x5404e  constrained. [mscorlib]System.Guid
0x54054  callvirt instance string [mscorlib]System.Object::ToString()
0x54059  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::VerifyComponentExist(string, string)
0x5405e  brfalse.s loc_540D3
0x54060  ldc.i4.0
0x54061  stloc.s  5
0x54063  ldarg.0
0x54064  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::chkSelectAllAssets
0x54069  ldc.i4.1
0x5406a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x5406f  ldarg.0
0x54070  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentSolutionContext()
0x54075  ldarg.0
0x54076  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityMD
0x5407b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x54080  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::AreSubcomponentsAddedSeperately(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SolutionApplicationContext, valuetype [mscorlib]System.Guid)
0x54085  brtrue.s loc_540A4
0x54087  ldarg.0
0x54088  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::chkSelectEntityMetadata
0x5408d  ldc.i4.1
0x5408e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x54093  ldarg.0
0x54094  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::chkSelectAllAssets
0x54099  ldc.i4.1
0x5409a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::set_Checked(bool)
0x5409f  ldc.i4.1
0x540a0  stloc.s  5
0x540a2  br.s     loc_540D3
0x540a4  ldloc.s  6
0x540a6  ldarg.0
0x540a7  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::_entityMD
0x540ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Id()
0x540b1  stloc.s  7
0x540b3  ldloca.s 7
0x540b5  constrained. [mscorlib]System.Guid
0x540bb  callvirt instance string [mscorlib]System.Object::ToString()
0x540c0  call     bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Utility.SolutionUtil::DoesRootHasIncludeSelfAndSelectedSubcomponents(string, string)
0x540c5  brtrue.s loc_540D3
0x540c7  ldarg.0
0x540c8  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::chkSelectEntityMetadata
0x540cd  ldc.i4.0
0x540ce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::set_Checked(bool)
0x540d3  ldarg.0
0x540d4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x540d9  ldstr    aDisableselecti// "disableSelectionInGrid"
0x540de  ldloc.s  5
0x540e0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x540e5  ldarg.0
0x540e6  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureFilters()
0x540eb  ldarg.0
0x540ec  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureFormsGrid()
0x540f1  ldarg.0
0x540f2  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureAttributeGrid()
0x540f7  ldarg.0
0x540f8  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureBpfGrid()
0x540fd  ldarg.0
0x540fe  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureVisualizationsGrid()
0x54103  ldarg.0
0x54104  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureOneToManyRelationshipGrid()
0x54109  ldarg.0
0x5410a  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureManyToOneRelationshipGrid()
0x5410f  ldarg.0
0x54110  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureManyToManyRelationshipGrid()
0x54115  ldarg.0
0x54116  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureViewGrid()
0x5411b  ldarg.0
0x5411c  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureMessageGrid()
0x54121  ldarg.0
0x54122  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureAlternateKeysGrid()
0x54127  ldarg.0
0x54128  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureHierarchyRulesGrid()
0x5412d  ldarg.0
0x5412e  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureDashboardsGrid()
0x54133  ldarg.0
0x54134  call     instance void Microsoft.Crm.Web.Tools.Solution.AddSubcomponentDialog::ConfigureTabs()
0x54139  ret
```
