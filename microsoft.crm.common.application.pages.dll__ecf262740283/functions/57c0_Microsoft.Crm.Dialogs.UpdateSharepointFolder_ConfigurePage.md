# Microsoft.Crm.Dialogs.UpdateSharepointFolder::ConfigurePage

- ea: `0x57c0`
- end: `0x5988`
- name: `Microsoft.Crm.Dialogs.UpdateSharepointFolder::ConfigurePage`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x57d8`: `/_common/styles/dialogs.css.aspx`
- `0x5855`: `isCreateFolder`
- `0x58c6`: `locationRelativePath`
- `0x5921`: `SharePointUpdateFolder`
- `0x5936`: `SharePointUpdateFolderDescription`

## pseudocode

```c

```

## disassembly

```asm
0x57c0  ldarg.0
0x57c1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x57c6  ldarg.0
0x57c7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x57cc  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x57d1  stloc.0
0x57d2  ldarg.0
0x57d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x57d8  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x57dd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x57e2  ldarg.0
0x57e3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x57e8  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x57ed  ldnull
0x57ee  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x57f3  ldarg.0
0x57f4  ldarg.0
0x57f5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x57fa  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x57ff  ldstr    aAbsurl// "absUrl"
0x5804  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5809  stfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::absUrl
0x580e  ldarg.0
0x580f  ldarg.0
0x5810  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5815  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x581a  ldstr    aIsaddmode// "isAddMode"
0x581f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5824  call     bool [mscorlib]System.Boolean::Parse(string)
0x5829  stfld    bool Microsoft.Crm.Dialogs.UpdateSharepointFolder::isAddMode
0x582e  ldarg.0
0x582f  ldarg.0
0x5830  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5835  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x583a  ldstr    aLocationname// "locationName"
0x583f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5844  stfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::locationName
0x5849  ldarg.0
0x584a  ldarg.0
0x584b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5850  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5855  ldstr    aIscreatefolder// "isCreateFolder"
0x585a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x585f  call     bool [mscorlib]System.Boolean::Parse(string)
0x5864  stfld    bool Microsoft.Crm.Dialogs.UpdateSharepointFolder::isCreateFolder
0x5869  ldarg.0
0x586a  ldarg.0
0x586b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5870  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5875  ldstr    aRegardingobjec// "regardingObjectId"
0x587a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x587f  stfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::regardingObjectId
0x5884  ldarg.0
0x5885  ldarg.0
0x5886  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x588b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5890  ldstr    aParentid// "parentId"
0x5895  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x589a  stfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::parentId
0x589f  ldarg.0
0x58a0  ldarg.0
0x58a1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x58a6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x58ab  ldstr    aDocid// "docId"
0x58b0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x58b5  stfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::docId
0x58ba  ldarg.0
0x58bb  ldarg.0
0x58bc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x58c1  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x58c6  ldstr    aLocationrelati// "locationRelativePath"
0x58cb  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x58d0  stfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::locationRelativePath
0x58d5  ldarg.0
0x58d6  ldarg.0
0x58d7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x58dc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x58e1  ldstr    aRegardingtype// "regardingType"
0x58e6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x58eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x58f0  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x58f5  stfld    int32 Microsoft.Crm.Dialogs.UpdateSharepointFolder::regardingObjectType
0x58fa  ldarg.0
0x58fb  ldarg.0
0x58fc  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5901  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5906  ldstr    aParenttype// "parentType"
0x590b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5910  callvirt instance string [mscorlib]System.Object::ToString()
0x5915  stfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::parentType
0x591a  ldloc.0
0x591b  ldarg.0
0x591c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5921  ldstr    aSharepointupda// "SharePointUpdateFolder"
0x5926  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x592b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x5930  ldarg.0
0x5931  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5936  ldstr    aSharepointupda_0// "SharePointUpdateFolderDescription"
0x593b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x5940  stloc.1
0x5941  ldarg.0
0x5942  ldfld    string Microsoft.Crm.Dialogs.UpdateSharepointFolder::absUrl
0x5947  stloc.2
0x5948  ldloc.0
0x5949  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x594e  ldloc.1
0x594f  ldc.i4.1
0x5950  newarr   [mscorlib]System.Object
0x5955  dup
0x5956  ldc.i4.0
0x5957  ldloc.2
0x5958  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x595d  stelem.ref
0x595e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5963  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x5968  ldloc.0
0x5969  ldc.i4.0
0x596a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x596f  ldloc.0
0x5970  ldc.i4.1
0x5971  ldstr    aButtonLabelCon// "Button_Label_Confirm"
0x5976  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x597b  ldloc.0
0x597c  ldc.i4.2
0x597d  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x5982  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x5987  ret
```
