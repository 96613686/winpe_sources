# Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::ConfigureForm

- ea: `0x1002b0`
- end: `0x100560`
- name: `Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::ConfigureForm`
- size: `688`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1001c0`
- `0x1001e0`
- `0x1002b0`
- `0x100560`
- `0x100610`

## string_xrefs

- `0x1002bc`: `Web.CreateTemplate.Window_Title_Ara`
- `0x1002ff`: `updateTemplateDialogLink`
- `0x100304`: `DocumentTemplate.Buttons.Upload.Title`
- `0x100317`: `DocumentTemplate.Buttons.Upload.Title`
- `0x100420`: `TemplateTypeCode`
- `0x10043d`: `TemplateTypeCode`
- `0x10050b`: `createTemplateGetFile`

## pseudocode

```c

```

## disassembly

```asm
0x1002b0  ldarg.0
0x1002b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1002b6  ldarg.0
0x1002b7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1002bc  ldstr    aWebCreatetempl// "Web.CreateTemplate.Window_Title_Ara"
0x1002c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1002c6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x1002cb  ldarg.0
0x1002cc  ldc.i4.1
0x1002cd  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::set_IsInlined(bool)
0x1002d2  ldarg.0
0x1002d3  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x1002d8  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x1002dd  stloc.0
0x1002de  ldloc.0
0x1002df  ldc.i4.1
0x1002e0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowButtons(bool)
0x1002e5  ldloc.0
0x1002e6  ldc.i4.0
0x1002e7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowHeader(bool)
0x1002ec  ldloc.0
0x1002ed  ldc.i4.0
0x1002ee  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ShowStatusBar(bool)
0x1002f3  ldloc.0
0x1002f4  ldc.i4   0x800
0x1002f9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x1002fe  ldloc.0
0x1002ff  ldstr    aUpdatetemplate// "updateTemplateDialogLink"
0x100304  ldstr    aDocumenttempla_2// "DocumentTemplate.Buttons.Upload.Title"
0x100309  ldstr    asc_11EF2A// ""
0x10030e  ldc.i4.0
0x10030f  ldc.i4.0
0x100310  ldc.i4.0
0x100311  ldarg.0
0x100312  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x100317  ldstr    aDocumenttempla_2// "DocumentTemplate.Buttons.Upload.Title"
0x10031c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x100321  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, bool, string)
0x100326  ldarg.0
0x100327  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x10032c  ldstr    aButtonLabelHel// "Button_Label_Help"
0x100331  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x100336  stloc.1
0x100337  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x10033c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_UseImageStrips()
0x100341  brfalse.s loc_100364
0x100343  ldarg.0
0x100344  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x100349  ldstr    aImgIdHelpiconS// "<img id=\"helpIcon\" src=\"/_imgs/offic"...
0x10034e  ldc.i4.1
0x10034f  newarr   [mscorlib]System.Object
0x100354  dup
0x100355  ldc.i4.0
0x100356  ldloc.1
0x100357  stelem.ref
0x100358  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10035d  stfld    string Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::HelpIconTag
0x100362  br.s     loc_100383
0x100364  ldarg.0
0x100365  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x10036a  ldstr    aImgIdHelpiconS_0// "<img id=\"helpIcon\" src=\"/_imgs/offic"...
0x10036f  ldc.i4.1
0x100370  newarr   [mscorlib]System.Object
0x100375  dup
0x100376  ldc.i4.0
0x100377  ldloc.1
0x100378  stelem.ref
0x100379  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10037e  stfld    string Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::HelpIconTag
0x100383  ldarg.0
0x100384  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x100389  ldstr    aExporttoexceld// "ExportToExcelDownloadStarted"
0x10038e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x100393  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x100398  stfld    string Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::DownloadStartedText
0x10039d  ldarg.0
0x10039e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1003a3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1003a8  ldstr    aEntitytypecode_1// "EntityTypeCode"
0x1003ad  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1003b2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1003b7  brtrue.s loc_1003DE
0x1003b9  ldarg.0
0x1003ba  ldarg.0
0x1003bb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1003c0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1003c5  ldstr    aEntitytypecode_1// "EntityTypeCode"
0x1003ca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1003cf  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1003d4  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x1003d9  stfld    int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::entityTypeCode
0x1003de  ldarg.0
0x1003df  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1003e4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1003e9  ldstr    aViewid_0// "ViewId"
0x1003ee  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1003f3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1003f8  brtrue.s loc_100415
0x1003fa  ldarg.0
0x1003fb  ldarg.0
0x1003fc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x100401  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x100406  ldstr    aViewid_0// "ViewId"
0x10040b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x100410  stfld    string Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::viewId
0x100415  ldarg.0
0x100416  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10041b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x100420  ldstr    aTemplatetypeco_0// "TemplateTypeCode"
0x100425  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10042a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10042f  brtrue.s loc_100456
0x100431  ldarg.0
0x100432  ldarg.0
0x100433  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x100438  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10043d  ldstr    aTemplatetypeco_0// "TemplateTypeCode"
0x100442  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x100447  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x10044c  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x100451  stfld    int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::TemplateTypeCode
0x100456  ldarg.0
0x100457  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10045c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x100461  ldstr    aViewtype_0// "ViewType"
0x100466  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x10046b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x100470  brtrue.s loc_100497
0x100472  ldarg.0
0x100473  ldarg.0
0x100474  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x100479  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x10047e  ldstr    aViewtype_0// "ViewType"
0x100483  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x100488  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x10048d  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x100492  stfld    int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::viewType
0x100497  ldarg.0
0x100498  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10049d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1004a2  ldstr    aDocumenttype_0// "DocumentType"
0x1004a7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1004ac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1004b1  brtrue.s loc_1004D8
0x1004b3  ldarg.0
0x1004b4  ldarg.0
0x1004b5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1004ba  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1004bf  ldstr    aDocumenttype_0// "DocumentType"
0x1004c4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1004c9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1004ce  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x1004d3  stfld    int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::DocumentType
0x1004d8  ldarg.0
0x1004d9  call     instance bool Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::get_isExcelTemplateEnabled()
0x1004de  brtrue.s loc_1004E7
0x1004e0  ldarg.0
0x1004e1  ldc.i4.2
0x1004e2  stfld    int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::DocumentType
0x1004e7  ldarg.0
0x1004e8  call     instance bool Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::get_isWordTemplateEnabled()
0x1004ed  brtrue.s loc_1004F6
0x1004ef  ldarg.0
0x1004f0  ldc.i4.1
0x1004f1  stfld    int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::DocumentType
0x1004f6  ldarg.0
0x1004f7  ldfld    int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::DocumentType
0x1004fc  ldc.i4.2
0x1004fd  bne.un.s loc_10050A
0x1004ff  ldarg.0
0x100500  ldstr    aWebSelectentit// "Web.SelectEntities.Window_Title_Ara"
0x100505  stfld    string Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::nextButtonResourceId
0x10050a  ldloc.0
0x10050b  ldstr    aCreatetemplate// "createTemplateGetFile"
0x100510  ldarg.0
0x100511  ldfld    string Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::nextButtonResourceId
0x100516  ldstr    asc_11EF2A// ""
0x10051b  ldc.i4.0
0x10051c  ldc.i4.0
0x10051d  ldc.i4.0
0x10051e  ldarg.0
0x10051f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x100524  ldarg.0
0x100525  ldfld    string Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::nextButtonResourceId
0x10052a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x10052f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, bool, string)
0x100534  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x100539  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x10053e  stloc.2
0x10053f  ldarg.0
0x100540  ldflda   int32 Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::TemplateTypeCode
0x100545  ldc.i4   0x26D5
0x10054a  call     instance bool [mscorlib]System.Int32::Equals(int32)
0x10054f  stloc.3
0x100550  ldarg.0
0x100551  ldloc.2
0x100552  ldloc.3
0x100553  call     instance void Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::BindEntityList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache, bool selectEntityOnLoad)
0x100558  ldarg.0
0x100559  ldloc.2
0x10055a  call     instance void Microsoft.Crm.Application.Pages.Common.CreateTemplateDialog::BindViewList(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache)
0x10055f  ret
```
