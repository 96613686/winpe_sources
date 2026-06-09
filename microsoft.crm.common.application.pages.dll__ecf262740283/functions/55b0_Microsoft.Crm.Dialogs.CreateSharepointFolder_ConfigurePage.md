# Microsoft.Crm.Dialogs.CreateSharepointFolder::ConfigurePage

- ea: `0x55b0`
- end: `0x56e0`
- name: `Microsoft.Crm.Dialogs.CreateSharepointFolder::ConfigurePage`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x55ce`: `/_common/styles/dialogs.css.aspx`
- `0x55f4`: `folderpath`

## pseudocode

```c

```

## disassembly

```asm
0x55b0  ldsfld   string [mscorlib]System.String::Empty
0x55b5  stloc.0
0x55b6  ldarg.0
0x55b7  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x55bc  ldarg.0
0x55bd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x55c2  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x55c7  stloc.1
0x55c8  ldarg.0
0x55c9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x55ce  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x55d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x55d8  ldarg.0
0x55d9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x55de  ldstr    aMscrmDialogsco// "Mscrm.DialogsControl"
0x55e3  ldnull
0x55e4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string, string)
0x55e9  ldarg.0
0x55ea  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x55ef  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x55f4  ldstr    aFolderpath// "folderpath"
0x55f9  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x55fe  stloc.2
0x55ff  ldarg.0
0x5600  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5605  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x560a  ldstr    aObjectid// "objectId"
0x560f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5614  stloc.0
0x5615  ldarg.0
0x5616  ldloc.0
0x5617  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x561c  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.CreateSharepointFolder::objectId
0x5621  ldarg.0
0x5622  ldarg.0
0x5623  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x5628  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x562d  ldstr    aOtype// "oType"
0x5632  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5637  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x563c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5641  stfld    int32 Microsoft.Crm.Dialogs.CreateSharepointFolder::oType
0x5646  ldarg.0
0x5647  ldarg.0
0x5648  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x564d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x5652  ldstr    aFoldername// "folderName"
0x5657  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x565c  ldloc.0
0x565d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetSharePointFolderName(string, string)
0x5662  stfld    string Microsoft.Crm.Dialogs.CreateSharepointFolder::folderName
0x5667  ldloc.2
0x5668  ldstr    asc_231F0// "/"
0x566d  ldarg.0
0x566e  ldfld    string Microsoft.Crm.Dialogs.CreateSharepointFolder::folderName
0x5673  call     string [mscorlib]System.String::Concat(string, string, string)
0x5678  stloc.2
0x5679  ldloc.1
0x567a  ldarg.0
0x567b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5680  ldstr    aSharepointaddf// "SharePointAddFolder"
0x5685  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x568a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x568f  ldarg.0
0x5690  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x5695  ldstr    aSharepointaddf_0// "SharePointAddFolderDescription"
0x569a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x569f  stloc.3
0x56a0  ldloc.1
0x56a1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x56a6  ldloc.3
0x56a7  ldc.i4.1
0x56a8  newarr   [mscorlib]System.Object
0x56ad  dup
0x56ae  ldc.i4.0
0x56af  ldloc.2
0x56b0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlDecode(string)
0x56b5  stelem.ref
0x56b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x56bb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x56c0  ldloc.1
0x56c1  ldc.i4.0
0x56c2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x56c7  ldloc.1
0x56c8  ldc.i4.1
0x56c9  ldstr    aButtonLabelCon// "Button_Label_Confirm"
0x56ce  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x56d3  ldloc.1
0x56d4  ldc.i4.2
0x56d5  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x56da  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x56df  ret
```
