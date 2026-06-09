# Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::ConfigureForm

- ea: `0xf0`
- end: `0x2a7`
- name: `Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::ConfigureForm`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x40`
- `0x60`
- `0x80`
- `0xa0`
- `0xb0`
- `0xc0`
- `0xd0`
- `0xe0`
- `0xf0`
- `0x2b0`

## pseudocode

```c

```

## disassembly

```asm
0xf0  ldarg.0
0xf1  ldarg.0
0xf2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xf7  ldstr    aDialogAddtocam// "Dialog_AddToCampaign_ActionStringAddToL"...
0xfc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x101  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::set_ActionString(string value)
0x106  ldarg.0
0x107  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x10c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x111  ldstr    aItotal// "iTotal"
0x116  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11b  stloc.0
0x11c  ldarg.0
0x11d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x122  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x127  ldstr    aIobjtype// "iObjType"
0x12c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x131  stloc.1
0x132  ldloc.0
0x133  brfalse.s loc_14B
0x135  ldloc.1
0x136  brfalse.s loc_14B
0x138  ldloc.0
0x139  callvirt instance int32 [mscorlib]System.String::get_Length()
0x13e  brfalse.s loc_14B
0x140  ldloc.1
0x141  callvirt instance int32 [mscorlib]System.String::get_Length()
0x146  ldc.i4.0
0x147  cgt.un
0x149  br.s     loc_14C
0x14b  ldc.i4.0
0x14c  ldstr    aNumAndTypeMust// "num and type must be defined on the que"...
0x151  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x156  ldarg.0
0x157  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15c  ldloc.0
0x15d  ldc.i4.0
0x15e  newarr   [mscorlib]System.Object
0x163  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x168  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16d  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x172  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::set_Total(int32 value)
0x177  ldarg.0
0x178  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17d  ldloc.1
0x17e  ldc.i4.0
0x17f  newarr   [mscorlib]System.Object
0x184  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x189  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18e  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x193  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::set_ObjectType(int32 value)
0x198  ldarg.0
0x199  call     instance int32 Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::get_Total()
0x19e  ldc.i4.1
0x19f  beq.s    loc_1B5
0x1a1  ldarg.0
0x1a2  ldarg.0
0x1a3  call     instance int32 Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::get_ObjectType()
0x1a8  ldc.i4.2
0x1a9  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1ae  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::set_ObjectName(string value)
0x1b3  br.s     loc_1C7
0x1b5  ldarg.0
0x1b6  ldarg.0
0x1b7  call     instance int32 Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::get_ObjectType()
0x1bc  ldc.i4.1
0x1bd  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1c2  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::set_ObjectName(string value)
0x1c7  ldarg.0
0x1c8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1cd  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1d2  stloc.2
0x1d3  ldloc.2
0x1d4  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1d9  ldc.i4.0
0x1da  conv.i8
0x1db  ble.s    loc_1E4
0x1dd  ldarg.0
0x1de  ldloc.2
0x1df  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::HandlePostback(class [mscorlib]System.IO.Stream inputStream)
0x1e4  ldarg.0
0x1e5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1ea  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1ef  ldstr    aConfirmmode// "confirmMode"
0x1f4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1f9  ldstr    a1// "1"
0x1fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x203  brfalse.s loc_21B
0x205  ldarg.0
0x206  ldstr    aConfirmmodeTru// "confirmMode(true)"
0x20b  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::set_DialogActionOk(string value)
0x210  ldarg.0
0x211  ldstr    aConfirmmodeFal// "confirmMode(false)"
0x216  call     instance void Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::set_DialogActionCancel(string value)
0x21b  ldarg.0
0x21c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x221  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x226  dup
0x227  ldc.i4   0x198
0x22c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Width(int32)
0x231  dup
0x232  ldc.i4   0xFA
0x237  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_Height(int32)
0x23c  dup
0x23d  ldarg.0
0x23e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x243  ldstr    aDialogTitleAdd// "Dialog_Title_AddList"
0x248  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x252  dup
0x253  ldarg.0
0x254  call     instance int32 Microsoft.Crm.Marketing.Dialogs.AddToCampaignDialogPage::get_Total()
0x259  ldc.i4.1
0x25a  beq.s    loc_26E
0x25c  ldarg.0
0x25d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x262  ldstr    aMaCampaignDial// "MA.Campaign.Dialogs.ListAssoc.AddingMan"...
0x267  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x26c  br.s     loc_27E
0x26e  ldarg.0
0x26f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x274  ldstr    aMaCampaignDial_0// "MA.Campaign.Dialogs.ListAssoc.AddingOne"...
0x279  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x27e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x283  dup
0x284  ldc.i4.0
0x285  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x28a  dup
0x28b  ldstr    aButbegin// "butBegin"
0x290  ldstr    aButtonLabelAdd// "Button_Label_Add"
0x295  ldstr    aIfMscrmUtiliti// "if(!Mscrm.Utilities.resetValidationFail"...
0x29a  ldc.i4.0
0x29b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(string, string, string, bool)
0x2a0  ldc.i4.2
0x2a1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x2a6  ret
```
