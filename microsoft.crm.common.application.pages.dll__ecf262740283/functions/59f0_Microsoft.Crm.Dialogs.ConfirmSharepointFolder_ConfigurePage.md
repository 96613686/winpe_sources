# Microsoft.Crm.Dialogs.ConfirmSharepointFolder::ConfigurePage

- ea: `0x59f0`
- end: `0x5b07`
- name: `Microsoft.Crm.Dialogs.ConfirmSharepointFolder::ConfigurePage`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x5a08`: `/_common/styles/dialogs.css.aspx`
- `0x5a85`: `isCreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x59f0  ldarg.0
0x59f1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x59f6  ldarg.0
0x59f7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x59fc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x5a01  stloc.0
0x5a02  ldarg.0
0x5a03  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5a08  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x5a0d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x5a12  ldarg.0
0x5a13  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5a18  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x5a1d  ldnull
0x5a1e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x5a23  ldarg.0
0x5a24  ldarg.0
0x5a25  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5a2a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5a2f  ldstr    aLocationurl// "locationUrl"
0x5a34  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a39  stfld    string Microsoft.Crm.Dialogs.ConfirmSharepointFolder::locationUrl
0x5a3e  ldarg.0
0x5a3f  ldarg.0
0x5a40  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5a45  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5a4a  ldstr    aIsaddmode// "isAddMode"
0x5a4f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a54  call     bool [mscorlib]System.Boolean::Parse(string)
0x5a59  stfld    bool Microsoft.Crm.Dialogs.ConfirmSharepointFolder::isAddMode
0x5a5e  ldarg.0
0x5a5f  ldarg.0
0x5a60  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5a65  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5a6a  ldstr    aFoldername// "folderName"
0x5a6f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a74  stfld    string Microsoft.Crm.Dialogs.ConfirmSharepointFolder::folderName
0x5a79  ldarg.0
0x5a7a  ldarg.0
0x5a7b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5a80  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5a85  ldstr    aIscreatefolder// "isCreateFolder"
0x5a8a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5a8f  call     bool [mscorlib]System.Boolean::Parse(string)
0x5a94  stfld    bool Microsoft.Crm.Dialogs.ConfirmSharepointFolder::isCreateFolder
0x5a99  ldloc.0
0x5a9a  ldarg.0
0x5a9b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5aa0  ldstr    aSharepointaddf// "SharePointAddFolder"
0x5aa5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5aaa  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x5aaf  ldarg.0
0x5ab0  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5ab5  ldstr    aSharepointaddf_0// "SharePointAddFolderDescription"
0x5aba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5abf  stloc.1
0x5ac0  ldarg.0
0x5ac1  ldfld    string Microsoft.Crm.Dialogs.ConfirmSharepointFolder::locationUrl
0x5ac6  stloc.2
0x5ac7  ldloc.0
0x5ac8  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x5acd  ldloc.1
0x5ace  ldc.i4.1
0x5acf  newarr   [mscorlib]System.Object
0x5ad4  dup
0x5ad5  ldc.i4.0
0x5ad6  ldloc.2
0x5ad7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x5adc  stelem.ref
0x5add  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5ae2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x5ae7  ldloc.0
0x5ae8  ldc.i4.0
0x5ae9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x5aee  ldloc.0
0x5aef  ldc.i4.1
0x5af0  ldstr    aButtonLabelCon// "Button_Label_Confirm"
0x5af5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x5afa  ldloc.0
0x5afb  ldc.i4.2
0x5afc  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x5b01  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x5b06  ret
```
