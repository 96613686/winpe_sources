# Microsoft.Crm.Dialogs.DeleteSharePointSite::ConfigureForm

- ea: `0x15a00`
- end: `0x15b57`
- name: `Microsoft.Crm.Dialogs.DeleteSharePointSite::ConfigureForm`
- size: `343`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15a00`
- `0x15b60`

## string_xrefs

- `0x15ac4`: `Dialog_Delete_Description`
- `0x15afe`: `Button_Label_Delete`
- `0x15aa9`: `Dialog_Delete_Title_SharePointSite`
- `0x15b1b`: `Dialog_Delete_Confirmation_SharePointSite`
- `0x15b31`: `Dialog_Delete_Confirmation_DefaultSharePointSite`
- `0x15b47`: `Dialog_Delete_Confirmation_IncludesDefaultSharePointSite`

## pseudocode

```c

```

## disassembly

```asm
0x15a00  ldarg.0
0x15a01  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x15a06  ldarg.0
0x15a07  ldarg.0
0x15a08  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x15a0d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x15a12  ldstr    aItotal// "iTotal"
0x15a17  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x15a1c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15a21  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x15a26  stfld    int32 Microsoft.Crm.Dialogs.DeleteSharePointSite::iTotal
0x15a2b  ldarg.0
0x15a2c  ldarg.0
0x15a2d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x15a32  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x15a37  ldstr    aIobjtype// "iObjType"
0x15a3c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x15a41  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15a46  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x15a4b  stfld    int32 Microsoft.Crm.Dialogs.DeleteSharePointSite::ObjType
0x15a50  ldarg.0
0x15a51  ldfld    int32 Microsoft.Crm.Dialogs.DeleteSharePointSite::iTotal
0x15a56  ldc.i4.1
0x15a57  bne.un.s loc_15A6D
0x15a59  ldarg.0
0x15a5a  ldarg.0
0x15a5b  ldfld    int32 Microsoft.Crm.Dialogs.DeleteSharePointSite::ObjType
0x15a60  ldc.i4.1
0x15a61  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x15a66  stfld    string Microsoft.Crm.Dialogs.DeleteSharePointSite::ObjName
0x15a6b  br.s     loc_15A7F
0x15a6d  ldarg.0
0x15a6e  ldarg.0
0x15a6f  ldfld    int32 Microsoft.Crm.Dialogs.DeleteSharePointSite::ObjType
0x15a74  ldc.i4.2
0x15a75  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x15a7a  stfld    string Microsoft.Crm.Dialogs.DeleteSharePointSite::ObjName
0x15a7f  ldarg.0
0x15a80  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x15a85  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x15a8a  stloc.0
0x15a8b  ldloc.0
0x15a8c  ldc.i4   0x198
0x15a91  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Width(int32)
0x15a96  ldarg.0
0x15a97  ldarg.0
0x15a98  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeleteSharePointSite::ReadDefaultSiteId()
0x15a9d  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeleteSharePointSite::defaultSiteId
0x15aa2  ldloc.0
0x15aa3  ldarg.0
0x15aa4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15aa9  ldstr    aDialogDeleteTi_1// "Dialog_Delete_Title_SharePointSite"
0x15aae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15ab3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x15ab8  ldloc.0
0x15ab9  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x15abe  ldarg.0
0x15abf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15ac4  ldstr    aDialogDeleteDe// "Dialog_Delete_Description"
0x15ac9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15ace  ldc.i4.2
0x15acf  newarr   [mscorlib]System.Object
0x15ad4  dup
0x15ad5  ldc.i4.0
0x15ad6  ldarg.0
0x15ad7  ldfld    int32 Microsoft.Crm.Dialogs.DeleteSharePointSite::iTotal
0x15adc  box      [mscorlib]System.Int32
0x15ae1  stelem.ref
0x15ae2  dup
0x15ae3  ldc.i4.1
0x15ae4  ldarg.0
0x15ae5  ldfld    string Microsoft.Crm.Dialogs.DeleteSharePointSite::ObjName
0x15aea  stelem.ref
0x15aeb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x15af0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x15af5  ldloc.0
0x15af6  ldc.i4.0
0x15af7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x15afc  ldloc.0
0x15afd  ldc.i4.1
0x15afe  ldstr    aButtonLabelDel// "Button_Label_Delete"
0x15b03  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x15b08  ldloc.0
0x15b09  ldc.i4.2
0x15b0a  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x15b0f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x15b14  ldarg.0
0x15b15  ldarg.0
0x15b16  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15b1b  ldstr    aDialogDeleteCo_1// "Dialog_Delete_Confirmation_SharePointSi"...
0x15b20  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15b25  stfld    string Microsoft.Crm.Dialogs.DeleteSharePointSite::BodyDescription_Delete
0x15b2a  ldarg.0
0x15b2b  ldarg.0
0x15b2c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15b31  ldstr    aDialogDeleteCo_2// "Dialog_Delete_Confirmation_DefaultShare"...
0x15b36  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15b3b  stfld    string Microsoft.Crm.Dialogs.DeleteSharePointSite::BodyDescription_DeleteDefault
0x15b40  ldarg.0
0x15b41  ldarg.0
0x15b42  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x15b47  ldstr    aDialogDeleteCo_3// "Dialog_Delete_Confirmation_IncludesDefa"...
0x15b4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15b51  stfld    string Microsoft.Crm.Dialogs.DeleteSharePointSite::BodyDescription_DeleteIncludesDefault
0x15b56  ret
```
