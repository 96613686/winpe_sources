# Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ConfigureForm

- ea: `0x3990`
- end: `0x3aaa`
- name: `Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ConfigureForm`
- size: `282`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3990`

## string_xrefs

- `0x3a3e`: `Dialog_DeleteContactConfirm_Title`
- `0x3a6d`: `Dialog_DeleteContactConfirm_Description`

## pseudocode

```c

```

## disassembly

```asm
0x3990  ldarg.0
0x3991  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x3996  ldarg.0
0x3997  ldarg.0
0x3998  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x399d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39a2  ldstr    aItotal// "iTotal"
0x39a7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39ac  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39b1  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x39b6  stfld    int32 Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::iTotal
0x39bb  ldarg.0
0x39bc  ldarg.0
0x39bd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x39c2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x39c7  ldstr    aIobjtype// "iObjType"
0x39cc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x39d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x39d6  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x39db  stfld    int32 Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjType
0x39e0  ldarg.0
0x39e1  ldarg.0
0x39e2  ldfld    int32 Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjType
0x39e7  ldc.i4.1
0x39e8  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x39ed  stfld    string Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjName
0x39f2  ldarg.0
0x39f3  ldfld    int32 Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::iTotal
0x39f8  ldc.i4.1
0x39f9  bne.un.s loc_3A09
0x39fb  ldarg.0
0x39fc  ldarg.0
0x39fd  ldfld    string Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjName
0x3a02  stfld    string Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjNamePlural
0x3a07  br.s     loc_3A1B
0x3a09  ldarg.0
0x3a0a  ldarg.0
0x3a0b  ldfld    int32 Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjType
0x3a10  ldc.i4.2
0x3a11  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x3a16  stfld    string Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjNamePlural
0x3a1b  ldarg.0
0x3a1c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3a21  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x3a26  stloc.0
0x3a27  ldloc.0
0x3a28  ldc.i4   0x198
0x3a2d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Width(int32)
0x3a32  ldloc.0
0x3a33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a38  ldarg.0
0x3a39  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a3e  ldstr    aDialogDeleteco// "Dialog_DeleteContactConfirm_Title"
0x3a43  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a48  ldc.i4.1
0x3a49  newarr   [mscorlib]System.Object
0x3a4e  dup
0x3a4f  ldc.i4.0
0x3a50  ldarg.0
0x3a51  ldfld    string Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjName
0x3a56  stelem.ref
0x3a57  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a5c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3a61  ldloc.0
0x3a62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a67  ldarg.0
0x3a68  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3a6d  ldstr    aDialogDeleteco_0// "Dialog_DeleteContactConfirm_Description"
0x3a72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3a77  ldc.i4.2
0x3a78  newarr   [mscorlib]System.Object
0x3a7d  dup
0x3a7e  ldc.i4.0
0x3a7f  ldarg.0
0x3a80  ldfld    int32 Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::iTotal
0x3a85  box      [mscorlib]System.Int32
0x3a8a  stelem.ref
0x3a8b  dup
0x3a8c  ldc.i4.1
0x3a8d  ldarg.0
0x3a8e  ldfld    string Microsoft.Crm.Dialogs.DeleteContactConfirmationPage::ObjNamePlural
0x3a93  stelem.ref
0x3a94  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a99  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x3a9e  ldloc.0
0x3a9f  ldc.i4   0x302
0x3aa4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x3aa9  ret
```
