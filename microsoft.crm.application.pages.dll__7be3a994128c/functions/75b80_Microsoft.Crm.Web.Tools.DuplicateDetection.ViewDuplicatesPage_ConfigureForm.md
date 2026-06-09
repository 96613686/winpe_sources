# Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::ConfigureForm

- ea: `0x75b80`
- end: `0x75c5b`
- name: `Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::ConfigureForm`
- size: `219`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x75b80`

## string_xrefs

- `0x75be5`: `showopen`
- `0x75c01`: `showopen`
- `0x75c13`: `OpenExisting`
- `0x75c18`: `ViewDuplicates_aspx_Button_Label_OpenRecord`
- `0x75c1d`: `btnOpenExisting()`
- `0x75c4b`: `UpdateRecord_Dialog_Description_ViewDuplicates_aspx`

## pseudocode

```c

```

## disassembly

```asm
0x75b80  ldarg.0
0x75b81  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x75b86  ldarg.0
0x75b87  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75b8c  ldc.i4.1
0x75b8d  beq.s    loc_75B99
0x75b8f  ldarg.0
0x75b90  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75b95  ldc.i4.2
0x75b96  beq.s    loc_75B99
0x75b98  ret
0x75b99  ldarg.0
0x75b9a  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x75b9f  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x75ba4  stloc.0
0x75ba5  ldloc.0
0x75ba6  brtrue.s loc_75BA9
0x75ba8  ret
0x75ba9  ldloc.0
0x75baa  dup
0x75bab  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_ButtonStyle()
0x75bb0  ldc.i4.0
0x75bb1  and
0x75bb2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x75bb7  ldarg.0
0x75bb8  ldfld    valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util/DuplicatesSource Microsoft.Crm.Web.Tools.DuplicateDetection.ViewDuplicatesPage::duplicatesSource
0x75bbd  ldc.i4.1
0x75bbe  beq.s    loc_75BC1
0x75bc0  ret
0x75bc1  ldloc.0
0x75bc2  ldc.i4.1
0x75bc3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_SetAccessKeysForDefaultButtons(bool)
0x75bc8  ldloc.0
0x75bc9  dup
0x75bca  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::get_ButtonStyle()
0x75bcf  ldc.i4   0x422
0x75bd4  or
0x75bd5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x75bda  ldarg.0
0x75bdb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75be0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x75be5  ldstr    aShowopen// "showopen"
0x75bea  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75bef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x75bf4  brtrue.s loc_75C2E
0x75bf6  ldarg.0
0x75bf7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x75bfc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x75c01  ldstr    aShowopen// "showopen"
0x75c06  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x75c0b  call     bool [mscorlib]System.Boolean::Parse(string)
0x75c10  brfalse.s loc_75C2E
0x75c12  ldloc.0
0x75c13  ldstr    aOpenexisting// "OpenExisting"
0x75c18  ldstr    aViewduplicates_0// "ViewDuplicates_aspx_Button_Label_OpenRe"...
0x75c1d  ldstr    aBtnopenexistin// "btnOpenExisting()"
0x75c22  ldc.i4.1
0x75c23  ldc.i4   0x800
0x75c28  ldc.i4.1
0x75c29  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool, valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, bool)
0x75c2e  ldloc.0
0x75c2f  ldarg.0
0x75c30  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75c35  ldstr    aDialogTitleVie// "Dialog_Title_ViewDuplicates_aspx"
0x75c3a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75c3f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x75c44  ldloc.0
0x75c45  ldarg.0
0x75c46  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x75c4b  ldstr    aUpdaterecordDi// "UpdateRecord_Dialog_Description_ViewDup"...
0x75c50  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75c55  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x75c5a  ret
```
