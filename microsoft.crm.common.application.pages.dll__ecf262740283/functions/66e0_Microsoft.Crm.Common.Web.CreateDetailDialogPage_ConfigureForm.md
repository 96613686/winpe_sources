# Microsoft.Crm.Common.Web.CreateDetailDialogPage::ConfigureForm

- ea: `0x66e0`
- end: `0x6932`
- name: `Microsoft.Crm.Common.Web.CreateDetailDialogPage::ConfigureForm`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x66e0`

## string_xrefs

- `0x66ec`: `/_static/_common/styles/AutoToolTip.js`
- `0x6852`: `Dialog_Create_Title`

## pseudocode

```c

```

## disassembly

```asm
0x66e0  ldarg.0
0x66e1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x66e6  ldarg.0
0x66e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x66ec  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x66f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x66f6  ldarg.0
0x66f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x66fc  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x6701  ldstr    aNameC// "name_c"
0x6706  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x670b  ldarg.0
0x670c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x6711  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x6716  stloc.0
0x6717  ldarg.0
0x6718  ldarg.0
0x6719  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x671e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6723  ldstr    aObjtype// "ObjType"
0x6728  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x672d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6732  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x6737  stfld    int32 Microsoft.Crm.Common.Web.CreateDetailDialogPage::_ObjType
0x673c  ldarg.0
0x673d  ldarg.0
0x673e  ldfld    int32 Microsoft.Crm.Common.Web.CreateDetailDialogPage::_ObjType
0x6743  ldc.i4.1
0x6744  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x6749  stfld    string Microsoft.Crm.Common.Web.CreateDetailDialogPage::_ObjName
0x674e  ldarg.0
0x674f  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::transactioncurrencyid
0x6754  ldc.i4.1
0x6755  newarr   [mscorlib]System.Int32
0x675a  dup
0x675b  ldc.i4.0
0x675c  ldc.i4   0x2391
0x6761  stelem.i4
0x6762  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x6767  ldarg.0
0x6768  ldfld    int32 Microsoft.Crm.Common.Web.CreateDetailDialogPage::_ObjType
0x676d  stloc.2
0x676e  ldloc.2
0x676f  ldc.i4   0x420
0x6774  beq.s    loc_6783
0x6776  ldloc.2
0x6777  ldc.i4   0x438
0x677c  beq.s    loc_67D8
0x677e  br       loc_6846
0x6783  ldarg.0
0x6784  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::txtName
0x6789  ldc.i4   0xC8
0x678e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl::set_MaxLength(int32)
0x6793  ldarg.0
0x6794  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::transactioncurrencyid
0x6799  ldc.i4.0
0x679a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x679f  ldarg.0
0x67a0  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.CreateDetailDialogPage::isamounttype
0x67a5  ldc.i4.0
0x67a6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x67ab  ldloc.0
0x67ac  ldarg.0
0x67ad  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x67b2  ldstr    aDialogAdduomsc// "Dialog_AddUOMSchedule_Description"
0x67b7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x67bc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x67c1  ldarg.0
0x67c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x67c7  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x67cc  ldstr    aBasenameC// "basename_c"
0x67d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x67d6  br.s     loc_6846
0x67d8  ldarg.0
0x67d9  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::txtName
0x67de  ldc.i4.s 0x64
0x67e0  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl::set_MaxLength(int32)
0x67e5  ldarg.0
0x67e6  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::txtBaseName
0x67eb  ldc.i4.0
0x67ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x67f1  ldloc.0
0x67f2  ldarg.0
0x67f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x67f8  ldstr    aDialogAdddisco// "Dialog_AddDiscountType_Description"
0x67fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6802  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x6807  ldarg.0
0x6808  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::transactioncurrencyid
0x680d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6812  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::ObtainDefaultCurrency(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6817  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0x681c  ldarg.0
0x681d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6822  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x6827  ldstr    aTypeC// "type_c"
0x682c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x6831  ldarg.0
0x6832  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x6837  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x683c  ldstr    aTransactioncur// "transactioncurrencyid_c"
0x6841  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x6846  ldloc.0
0x6847  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x684c  ldarg.0
0x684d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6852  ldstr    aDialogCreateTi// "Dialog_Create_Title"
0x6857  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x685c  ldc.i4.1
0x685d  newarr   [mscorlib]System.Object
0x6862  dup
0x6863  ldc.i4.0
0x6864  ldarg.0
0x6865  ldfld    string Microsoft.Crm.Common.Web.CreateDetailDialogPage::_ObjName
0x686a  stelem.ref
0x686b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6870  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x6875  ldarg.0
0x6876  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.CreateDetailDialogPage::isamounttype
0x687b  ldarg.0
0x687c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x6881  ldstr    aPicklistDiscou// "PickList_DiscountType_Value_0"
0x6886  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x688b  ldstr    a0// "0"
0x6890  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x6895  ldarg.0
0x6896  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.CreateDetailDialogPage::isamounttype
0x689b  ldarg.0
0x689c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x68a1  ldstr    aPicklistDiscou_0// "PickList_DiscountType_Value_1"
0x68a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x68ab  ldstr    a1// "1"
0x68b0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string)
0x68b5  ldarg.0
0x68b6  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.CreateDetailDialogPage::isamounttype
0x68bb  ldstr    a0// "0"
0x68c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_Selected(string)
0x68c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x68ca  ldstr    aRequiredFields// "Required_Fields_Background_Color"
0x68cf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x68d4  stloc.1
0x68d5  ldloc.1
0x68d6  brfalse.s loc_6931
0x68d8  ldloc.1
0x68d9  callvirt instance int32 [mscorlib]System.String::get_Length()
0x68de  brfalse.s loc_6931
0x68e0  ldarg.0
0x68e1  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::txtName
0x68e6  ldstr    aStyle// "Style"
0x68eb  ldstr    aBackgroundColo// "background-color:"
0x68f0  ldloc.1
0x68f1  call     string [mscorlib]System.String::Concat(string, string)
0x68f6  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0x68fb  ldarg.0
0x68fc  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.CreateDetailDialogPage::txtBaseName
0x6901  ldstr    aStyle// "Style"
0x6906  ldstr    aBackgroundColo// "background-color:"
0x690b  ldloc.1
0x690c  call     string [mscorlib]System.String::Concat(string, string)
0x6911  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::AddExpando(string, string)
0x6916  ldarg.0
0x6917  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Common.Web.CreateDetailDialogPage::isamounttype
0x691c  ldstr    aStyle// "Style"
0x6921  ldstr    aBackgroundColo// "background-color:"
0x6926  ldloc.1
0x6927  call     string [mscorlib]System.String::Concat(string, string)
0x692c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0x6931  ret
```
