# Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ConfigureForm

- ea: `0x37b0`
- end: `0x38de`
- name: `Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ConfigureForm`
- size: `302`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x37b0`
- `0x38e0`

## string_xrefs

- `0x385e`: `Dialog_DeleteAccountConfirm_Title`
- `0x388d`: `Dialog_DeleteAccountConfirm_Description`

## pseudocode

```c

```

## disassembly

```asm
0x37b0  ldarg.0
0x37b1  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x37b6  ldarg.0
0x37b7  ldarg.0
0x37b8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x37bd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x37c2  ldstr    aItotal// "iTotal"
0x37c7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x37cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37d1  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x37d6  stfld    int32 Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::iTotal
0x37db  ldarg.0
0x37dc  ldarg.0
0x37dd  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x37e2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x37e7  ldstr    aIobjtype// "iObjType"
0x37ec  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x37f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37f6  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x37fb  stfld    int32 Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjType
0x3800  ldarg.0
0x3801  ldarg.0
0x3802  ldfld    int32 Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjType
0x3807  ldc.i4.1
0x3808  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x380d  stfld    string Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjName
0x3812  ldarg.0
0x3813  ldfld    int32 Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::iTotal
0x3818  ldc.i4.1
0x3819  bne.un.s loc_3829
0x381b  ldarg.0
0x381c  ldarg.0
0x381d  ldfld    string Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjName
0x3822  stfld    string Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjNamePlural
0x3827  br.s     loc_383B
0x3829  ldarg.0
0x382a  ldarg.0
0x382b  ldfld    int32 Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjType
0x3830  ldc.i4.2
0x3831  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x3836  stfld    string Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjNamePlural
0x383b  ldarg.0
0x383c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3841  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x3846  stloc.0
0x3847  ldloc.0
0x3848  ldc.i4   0x198
0x384d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Width(int32)
0x3852  ldloc.0
0x3853  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3858  ldarg.0
0x3859  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x385e  ldstr    aDialogDeleteac// "Dialog_DeleteAccountConfirm_Title"
0x3863  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3868  ldc.i4.1
0x3869  newarr   [mscorlib]System.Object
0x386e  dup
0x386f  ldc.i4.0
0x3870  ldarg.0
0x3871  ldfld    string Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjName
0x3876  stelem.ref
0x3877  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x387c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3881  ldloc.0
0x3882  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3887  ldarg.0
0x3888  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x388d  ldstr    aDialogDeleteac_0// "Dialog_DeleteAccountConfirm_Description"
0x3892  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3897  ldc.i4.2
0x3898  newarr   [mscorlib]System.Object
0x389d  dup
0x389e  ldc.i4.0
0x389f  ldarg.0
0x38a0  ldfld    int32 Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::iTotal
0x38a5  box      [mscorlib]System.Int32
0x38aa  stelem.ref
0x38ab  dup
0x38ac  ldc.i4.1
0x38ad  ldarg.0
0x38ae  ldfld    string Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::ObjNamePlural
0x38b3  stelem.ref
0x38b4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x38b9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x38be  ldloc.0
0x38bf  ldc.i4   0x302
0x38c4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x38c9  ldarg.0
0x38ca  call     instance bool Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::IsCollaborationOnAccountEnabled()
0x38cf  brtrue.s loc_38DD
0x38d1  ldarg.0
0x38d2  ldfld    class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Dialogs.DeleteAccountConfirmationPage::sharePointDocumentsWarning
0x38d7  ldc.i4.0
0x38d8  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x38dd  ret
```
