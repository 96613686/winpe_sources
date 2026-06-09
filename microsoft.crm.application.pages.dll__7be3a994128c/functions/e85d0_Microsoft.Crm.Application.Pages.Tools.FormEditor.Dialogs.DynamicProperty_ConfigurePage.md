# Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.DynamicProperty::ConfigurePage

- ea: `0xe85d0`
- end: `0xe87c9`
- name: `Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.DynamicProperty::ConfigurePage`
- size: `505`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0xe85fc`: `/_common/styles/dialogs.css.aspx`
- `0xe869d`: `/_static/_common/styles/AutoToolTip.js`
- `0xe86cd`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xe85dc`: `/_common/styles/select.css.aspx`
- `0xe86dd`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xe874d`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xe86bd`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`
- `0xe86ed`: `/_static/Sales/CrmSoapServiceProxy.js`

## pseudocode

```c

```

## disassembly

```asm
0xe85d0  ldarg.0
0xe85d1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0xe85d6  ldarg.0
0xe85d7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe85dc  ldstr    aCommonStylesSe// "/_common/styles/select.css.aspx"
0xe85e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe85e6  ldarg.0
0xe85e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe85ec  ldstr    aNavTabsCssAspx// "/_nav/tabs.css.aspx"
0xe85f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe85f6  ldarg.0
0xe85f7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe85fc  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0xe8601  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe8606  ldarg.0
0xe8607  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe860c  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0xe8611  ldnull
0xe8612  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0xe8617  ldarg.0
0xe8618  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe861d  ldstr    aToolsFormedito_5// "/tools/formeditor/styles/dialogs.css.as"...
0xe8622  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe8627  ldarg.0
0xe8628  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe862d  ldstr    aFormsControlsC// "/_forms/controls/controls.css.aspx"
0xe8632  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe8637  ldarg.0
0xe8638  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe863d  ldstr    aToolsFieldsele// "/_tools/fieldselect/fieldselect.css.asp"...
0xe8642  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe8647  ldarg.0
0xe8648  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe864d  ldstr    aStaticToolsFor// "/_static/tools/formeditor/scripts/objec"...
0xe8652  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8657  ldarg.0
0xe8658  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe865d  ldstr    aStaticToolsFor_3// "/_static/tools/formeditor/scripts/dialo"...
0xe8662  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8667  ldarg.0
0xe8668  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe866d  ldstr    aStaticToolsFor_1// "/_static/tools/formeditor/scripts/util."...
0xe8672  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8677  ldarg.0
0xe8678  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe867d  ldstr    aStaticToolsFor_0// "/_static/tools/formeditor/scripts/field"...
0xe8682  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8687  ldarg.0
0xe8688  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe868d  ldstr    aStaticToolsFie// "/_static/_tools/fieldselect/fieldselect"...
0xe8692  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8697  ldarg.0
0xe8698  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe869d  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0xe86a2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe86a7  ldarg.0
0xe86a8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe86ad  ldstr    aControlsDplist// "/_controls/DPListControl/dynamicpropert"...
0xe86b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xe86b7  ldarg.0
0xe86b8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe86bd  ldstr    aStaticCommonSc_40// "/_static/_common/scripts/SalesCrmSoapPr"...
0xe86c2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe86c7  ldarg.0
0xe86c8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe86cd  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xe86d2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe86d7  ldarg.0
0xe86d8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe86dd  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0xe86e2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe86e7  ldarg.0
0xe86e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe86ed  ldstr    aStaticSalesCrm// "/_static/Sales/CrmSoapServiceProxy.js"
0xe86f2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe86f7  ldarg.0
0xe86f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe86fd  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0xe8702  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8707  ldarg.0
0xe8708  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe870d  ldstr    aStaticFormsTex_0// "/_static/_forms/textinputbehavior.js"
0xe8712  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8717  ldarg.0
0xe8718  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe871d  ldstr    aStaticFormsLoo// "/_static/_forms/lookupbehavior.js"
0xe8722  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8727  ldarg.0
0xe8728  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe872d  ldstr    aStaticFormsNum_0// "/_static/_forms/numberinputbehavior.js"
0xe8732  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8737  ldarg.0
0xe8738  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe873d  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0xe8742  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8747  ldarg.0
0xe8748  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe874d  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0xe8752  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8757  ldarg.0
0xe8758  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe875d  ldstr    aStaticControls_33// "/_static/_controls/inlineedit/inlineedi"...
0xe8762  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8767  ldarg.0
0xe8768  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe876d  ldstr    aStaticControls_22// "/_static/_controls/inlineedit/inlineedi"...
0xe8772  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8777  ldarg.0
0xe8778  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe877d  ldstr    aStaticControls_37// "/_static/_controls/DPListControl/Dynami"...
0xe8782  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8787  ldarg.0
0xe8788  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe878d  ldstr    aStaticControls_7// "/_static/_controls/FlyoutDialog/FlyoutD"...
0xe8792  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xe8797  ldarg.0
0xe8798  ldarg.0
0xe8799  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xe879e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xe87a3  ldstr    aIsdraftproduct// "IsDraftProduct"
0xe87a8  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xe87ad  stfld    string Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.DynamicProperty::isDraftProduct
0xe87b2  ldarg.0
0xe87b3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xe87b8  ldstr    aIsdraftproduct_0// "ISDRAFTPRODUCT"
0xe87bd  ldarg.0
0xe87be  ldfld    string Microsoft.Crm.Application.Pages.Tools.FormEditor.Dialogs.DynamicProperty::isDraftProduct
0xe87c3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xe87c8  ret
```
