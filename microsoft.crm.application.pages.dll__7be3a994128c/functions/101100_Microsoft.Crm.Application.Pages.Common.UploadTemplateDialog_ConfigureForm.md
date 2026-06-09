# Microsoft.Crm.Application.Pages.Common.UploadTemplateDialog::ConfigureForm

- ea: `0x101100`
- end: `0x101220`
- name: `Microsoft.Crm.Application.Pages.Common.UploadTemplateDialog::ConfigureForm`
- size: `288`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x101100`
- `0x101220`

## string_xrefs

- `0x10112c`: `editTemplateInformation`
- `0x101131`: `Web.UploadDocumentTemplatePage.EditTemplateInformation`
- `0x101144`: `Web.UploadTemplate.ButtonTooltip`
- `0x101158`: `Web.UploadDocumentTemplatePage.CancelButton`
- `0x10116b`: `Web.UploadDocumentTemplatePage.CancelButton`
- `0x10117a`: `<a href="" id="upload_link" class="dragHereAnchor">`
- `0x10118c`: `Web.UploadDocumentTemplatePage.DragHere`
- `0x1011c2`: `TemplateType`
- `0x1011df`: `TemplateType`

## pseudocode

```c

```

## disassembly

```asm
0x101100  ldarg.0
0x101101  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x101106  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x10110b  dup
0x10110c  ldc.i4.1
0x10110d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowButtons(bool)
0x101112  dup
0x101113  ldc.i4.0
0x101114  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowHeader(bool)
0x101119  dup
0x10111a  ldc.i4.0
0x10111b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowStatusBar(bool)
0x101120  dup
0x101121  ldc.i4   0x800
0x101126  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x10112b  dup
0x10112c  ldstr    aEdittemplatein// "editTemplateInformation"
0x101131  ldstr    aWebUploaddocum// "Web.UploadDocumentTemplatePage.EditTemp"...
0x101136  ldstr    asc_11EF2A// ""
0x10113b  ldc.i4.0
0x10113c  ldc.i4.1
0x10113d  ldc.i4.0
0x10113e  ldarg.0
0x10113f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x101144  ldstr    aWebUploadtempl// "Web.UploadTemplate.ButtonTooltip"
0x101149  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10114e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, bool, string)
0x101153  ldstr    aBtncancel// "btnCancel"
0x101158  ldstr    aWebUploaddocum_0// "Web.UploadDocumentTemplatePage.CancelBu"...
0x10115d  ldstr    aClosewindow// "closeWindow();"
0x101162  ldc.i4.0
0x101163  ldc.i4.2
0x101164  ldc.i4.0
0x101165  ldarg.0
0x101166  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10116b  ldstr    aWebUploaddocum_0// "Web.UploadDocumentTemplatePage.CancelBu"...
0x101170  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x101175  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, bool, string)
0x10117a  ldstr    aAHrefIdUploadL// "<a href=\"\" id=\"upload_link\" class="...
0x10117f  stloc.0
0x101180  ldarg.0
0x101181  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x101186  ldarg.0
0x101187  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10118c  ldstr    aWebUploaddocum_1// "Web.UploadDocumentTemplatePage.DragHere"
0x101191  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x101196  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x10119b  ldc.i4.2
0x10119c  newarr   [mscorlib]System.Object
0x1011a1  dup
0x1011a2  ldc.i4.0
0x1011a3  ldloc.0
0x1011a4  stelem.ref
0x1011a5  dup
0x1011a6  ldc.i4.1
0x1011a7  ldstr    aA// "</a>"
0x1011ac  stelem.ref
0x1011ad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1011b2  stfld    string Microsoft.Crm.Application.Pages.Common.UploadTemplateDialog::uploadTemplateUploadText
0x1011b7  ldarg.0
0x1011b8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1011bd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1011c2  ldstr    aTemplatetype_0// "TemplateType"
0x1011c7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1011cc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1011d1  brtrue.s loc_1011F8
0x1011d3  ldarg.0
0x1011d4  ldarg.0
0x1011d5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1011da  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1011df  ldstr    aTemplatetype_0// "TemplateType"
0x1011e4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1011e9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1011ee  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x1011f3  stfld    int32 Microsoft.Crm.Application.Pages.Common.UploadTemplateDialog::TemplateType
0x1011f8  ldarg.0
0x1011f9  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1011fe  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x101203  ldstr    aAction// "action"
0x101208  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10120d  ldstr    aFileupload// "fileUpload"
0x101212  call     bool [mscorlib]System.String::op_Equality(string, string)
0x101217  brfalse.s loc_10121F
0x101219  ldarg.0
0x10121a  call     instance void Microsoft.Crm.Application.Pages.Common.UploadTemplateDialog::CreateNewDocumentTemplate()
0x10121f  ret
```
