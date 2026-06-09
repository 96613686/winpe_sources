# Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ConfigureForm

- ea: `0x3b20`
- end: `0x3cb0`
- name: `Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ConfigureForm`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3b20`

## string_xrefs

- `0x3b88`: `Dialog_DeleteQueue_Description`
- `0x3bcd`: `Dialog_DeleteQueue_ActiveMembers_Warning`
- `0x3c10`: `Dialog_DeleteQueueEmpty_Title`
- `0x3c3f`: `Dialog_DeleteQueue_BodyTextEmpty`
- `0x3c99`: `Button_Label_Delete`

## pseudocode

```c

```

## disassembly

```asm
0x3b20  ldarg.0
0x3b21  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x3b26  ldarg.0
0x3b27  ldarg.0
0x3b28  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3b2d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3b32  ldstr    aItotal// "iTotal"
0x3b37  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3b3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b41  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x3b46  stfld    int32 Microsoft.Crm.Dialogs.DeleteQueueDialogPage::iTotal
0x3b4b  ldarg.0
0x3b4c  ldarg.0
0x3b4d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3b52  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3b57  ldstr    aIobjtype// "iObjType"
0x3b5c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3b61  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b66  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3b6b  stfld    int32 Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjType
0x3b70  ldarg.0
0x3b71  ldarg.0
0x3b72  ldfld    int32 Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjType
0x3b77  ldc.i4.1
0x3b78  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x3b7d  stfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjName
0x3b82  ldarg.0
0x3b83  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3b88  ldstr    aDialogDeletequ// "Dialog_DeleteQueue_Description"
0x3b8d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3b92  stloc.0
0x3b93  ldarg.0
0x3b94  ldfld    int32 Microsoft.Crm.Dialogs.DeleteQueueDialogPage::iTotal
0x3b99  ldc.i4.1
0x3b9a  bne.un.s loc_3BE6
0x3b9c  ldarg.0
0x3b9d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3ba2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x3ba7  ldstr    aSids// "sIds"
0x3bac  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3bb1  callvirt instance string [mscorlib]System.Object::ToString()
0x3bb6  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3bbb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3bc0  call     bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.Queue::CheckActiveMembersForQueue(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3bc5  brfalse.s loc_3BD8
0x3bc7  ldarg.0
0x3bc8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3bcd  ldstr    aDialogDeletequ_0// "Dialog_DeleteQueue_ActiveMembers_Warnin"...
0x3bd2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3bd7  stloc.0
0x3bd8  ldarg.0
0x3bd9  ldarg.0
0x3bda  ldfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjName
0x3bdf  stfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjNamePlural
0x3be4  br.s     loc_3BF8
0x3be6  ldarg.0
0x3be7  ldarg.0
0x3be8  ldfld    int32 Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjType
0x3bed  ldc.i4.2
0x3bee  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x3bf3  stfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjNamePlural
0x3bf8  ldarg.0
0x3bf9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3bfe  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x3c03  stloc.1
0x3c04  ldloc.1
0x3c05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c0a  ldarg.0
0x3c0b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3c10  ldstr    aDialogDeletequ_1// "Dialog_DeleteQueueEmpty_Title"
0x3c15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c1a  ldc.i4.1
0x3c1b  newarr   [mscorlib]System.Object
0x3c20  dup
0x3c21  ldc.i4.0
0x3c22  ldarg.0
0x3c23  ldfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjNamePlural
0x3c28  stelem.ref
0x3c29  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c2e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x3c33  ldarg.0
0x3c34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c39  ldarg.0
0x3c3a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x3c3f  ldstr    aDialogDeletequ_2// "Dialog_DeleteQueue_BodyTextEmpty"
0x3c44  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x3c49  ldc.i4.1
0x3c4a  newarr   [mscorlib]System.Object
0x3c4f  dup
0x3c50  ldc.i4.0
0x3c51  ldarg.0
0x3c52  ldfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjNamePlural
0x3c57  stelem.ref
0x3c58  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c5d  stfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::_sBodyText
0x3c62  ldloc.1
0x3c63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3c68  ldloc.0
0x3c69  ldc.i4.2
0x3c6a  newarr   [mscorlib]System.Object
0x3c6f  dup
0x3c70  ldc.i4.0
0x3c71  ldarg.0
0x3c72  ldfld    int32 Microsoft.Crm.Dialogs.DeleteQueueDialogPage::iTotal
0x3c77  box      [mscorlib]System.Int32
0x3c7c  stelem.ref
0x3c7d  dup
0x3c7e  ldc.i4.1
0x3c7f  ldarg.0
0x3c80  ldfld    string Microsoft.Crm.Dialogs.DeleteQueueDialogPage::ObjNamePlural
0x3c85  stelem.ref
0x3c86  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3c8b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x3c90  ldloc.1
0x3c91  ldc.i4.0
0x3c92  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x3c97  ldloc.1
0x3c98  ldc.i4.1
0x3c99  ldstr    aButtonLabelDel// "Button_Label_Delete"
0x3c9e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3ca3  ldloc.1
0x3ca4  ldc.i4.2
0x3ca5  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x3caa  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x3caf  ret
```
