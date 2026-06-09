# Microsoft.Crm.Web.Tools.Views.FormEditorPage::ConfigureHeader

- ea: `0x7eeb0`
- end: `0x7f0be`
- name: `Microsoft.Crm.Web.Tools.Views.FormEditorPage::ConfigureHeader`
- size: `526`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x81050`
- `0x81670`

## string_xrefs

- `0x7efc5`: `MenuItem_Create_Form`
- `0x7efdb`: `MenuItem_Update_Form`
- `0x7eff1`: `MenuItem_Read_Only_Form`
- `0x7f01c`: `_createTitle`
- `0x7f032`: `_updateTitle`
- `0x7f048`: `_readOnlyTitle`
- `0x7f05e`: `_isAirUpdated`

## pseudocode

```c

```

## disassembly

```asm
0x7eeb0  ldarg.0
0x7eeb1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::ConfigureHeader()
0x7eeb6  ldarg.0
0x7eeb7  ldarg.0
0x7eeb8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7eebd  ldstr    aFieldExplorerC// "Field_Explorer_Caption"
0x7eec2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7eec7  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::fieldExplorerCaption
0x7eecc  ldarg.0
0x7eecd  ldarg.0
0x7eece  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7eed3  ldstr    aRelationshipEx// "Relationship_Explorer_Caption"
0x7eed8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7eedd  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::relationshipExplorerCaption
0x7eee2  ldarg.0
0x7eee3  ldarg.0
0x7eee4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7eee9  ldstr    aBusinessrulesE// "BusinessRules_Explorer_Caption"
0x7eeee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7eef3  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::businessRulesExplorerCaption
0x7eef8  ldarg.0
0x7eef9  ldarg.0
0x7eefa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7eeff  ldstr    aFormeditorFiel// "Formeditor_FieldExplorer_Image_AltText"
0x7ef04  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ef09  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::fieldExplorerAltText
0x7ef0e  ldarg.0
0x7ef0f  ldarg.0
0x7ef10  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ef15  ldstr    aFormeditorRela// "Formeditor_RelationshipExplorer_Image_A"...
0x7ef1a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ef1f  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::relationshipExplorerAltText
0x7ef24  ldarg.0
0x7ef25  ldarg.0
0x7ef26  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ef2b  ldstr    aNewheaderCapti// "NewHeader_Caption"
0x7ef30  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ef35  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::newHeaderCaption
0x7ef3a  ldarg.0
0x7ef3b  ldarg.0
0x7ef3c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ef41  ldstr    aNewfooterCapti// "NewFooter_Caption"
0x7ef46  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ef4b  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::newFooterCaption
0x7ef50  ldarg.0
0x7ef51  ldarg.0
0x7ef52  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ef57  ldstr    aInvalidformtyp// "InvalidFormTypeSelected_Caption"
0x7ef5c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ef61  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::invalidFormTypeSelectedCaption
0x7ef66  ldarg.0
0x7ef67  ldarg.0
0x7ef68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ef6d  ldstr    aInvalidformpre// "InvalidFormPresentationSelected_Caption"
0x7ef72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ef77  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::invalidFormPresentationSelectedCaption
0x7ef7c  ldarg.0
0x7ef7d  ldarg.0
0x7ef7e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ef83  ldstr    aFieldexplorerB// "FieldExplorer_Bottom_Legend"
0x7ef88  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ef8d  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::fieldExplorerLegend
0x7ef92  ldarg.0
0x7ef93  ldarg.0
0x7ef94  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7ef99  ldstr    aLookupImageDes// "Lookup_Image_Description"
0x7ef9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7efa3  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::lookupImageCaption
0x7efa8  ldarg.0
0x7efa9  ldarg.0
0x7efaa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7efaf  ldstr    aPicklistImageD// "Picklist_Image_Description"
0x7efb4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7efb9  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::picklistImageCaption
0x7efbe  ldarg.0
0x7efbf  ldarg.0
0x7efc0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7efc5  ldstr    aMenuitemCreate// "MenuItem_Create_Form"
0x7efca  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7efcf  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::createFormTitle
0x7efd4  ldarg.0
0x7efd5  ldarg.0
0x7efd6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7efdb  ldstr    aMenuitemUpdate// "MenuItem_Update_Form"
0x7efe0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7efe5  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::updateFormTitle
0x7efea  ldarg.0
0x7efeb  ldarg.0
0x7efec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7eff1  ldstr    aMenuitemReadOn// "MenuItem_Read_Only_Form"
0x7eff6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7effb  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::readOnlyFormTitle
0x7f000  ldarg.0
0x7f001  ldarg.0
0x7f002  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7f007  ldstr    aWebToolsFormed_0// "Web.Tools.FormEditor.Dialogs.fldExp.asp"...
0x7f00c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7f011  stfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::fieldExpNewButton
0x7f016  ldarg.0
0x7f017  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7f01c  ldstr    aCreatetitle// "_createTitle"
0x7f021  ldarg.0
0x7f022  ldfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::createFormTitle
0x7f027  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7f02c  ldarg.0
0x7f02d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7f032  ldstr    aUpdatetitle// "_updateTitle"
0x7f037  ldarg.0
0x7f038  ldfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::updateFormTitle
0x7f03d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7f042  ldarg.0
0x7f043  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7f048  ldstr    aReadonlytitle// "_readOnlyTitle"
0x7f04d  ldarg.0
0x7f04e  ldfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::readOnlyFormTitle
0x7f053  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7f058  ldarg.0
0x7f059  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7f05e  ldstr    aIsairupdated// "_isAirUpdated"
0x7f063  ldarg.0
0x7f064  ldfld    string Microsoft.Crm.Web.Tools.Views.FormEditorPage::objectCode
0x7f069  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7f06e  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x7f073  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7f078  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsRefreshEnabledForEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7f07d  stloc.0
0x7f07e  ldloca.s 0
0x7f080  call     instance string [mscorlib]System.Boolean::ToString()
0x7f085  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7f08a  ldarg.0
0x7f08b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7f090  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader
0x7f095  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader::get_RibbonDataControl()
0x7f09a  ldarg.0
0x7f09b  ldarg.0
0x7f09c  ldfld    valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase/FormType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase::formTypeCode
0x7f0a1  call     instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.FormType Microsoft.Crm.Web.Tools.Views.FormEditorPage::ConvertFormTypeToRibbonFormType(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.FormEditorBase/FormType formType)
0x7f0a6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Ribbon.RibbonData::RegisterFormType(valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.FormType)
0x7f0ab  ldarg.0
0x7f0ac  call     instance void Microsoft.Crm.Web.Tools.Views.FormEditorPage::InitializeExplorerFilterResources()
0x7f0b1  ldarg.0
0x7f0b2  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox Microsoft.Crm.Web.Tools.Views.FormEditorPage::unusedFilter
0x7f0b7  ldc.i4.1
0x7f0b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CheckBox::set_Checked(bool)
0x7f0bd  ret
```
