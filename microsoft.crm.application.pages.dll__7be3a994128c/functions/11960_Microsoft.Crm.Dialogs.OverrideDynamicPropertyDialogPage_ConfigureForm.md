# Microsoft.Crm.Dialogs.OverrideDynamicPropertyDialogPage::ConfigureForm

- ea: `0x11960`
- end: `0x11b67`
- name: `Microsoft.Crm.Dialogs.OverrideDynamicPropertyDialogPage::ConfigureForm`
- size: `519`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x11960`

## string_xrefs

- `0x119f1`: `text/xml`
- `0x11a2c`: `XML loaded from the stream returned String.Empty.`
- `0x11a36`: `XML loaded from the stream returned String.Empty.`
- `0x1198a`: `overwrite`
- `0x11a85`: `overwrite`
- `0x119b7`: `Dialog_Label_Overwrite`
- `0x11b05`: `Dialog_Overwrite_Title`
- `0x11b34`: `Dialog_Overwrite_Description`
- `0x11b50`: `Button_Label_Overwrite`

## pseudocode

```c

```

## disassembly

```asm
0x11960  ldarg.0
0x11961  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x11966  ldarg.0
0x11967  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1196c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11971  ldstr    aAction// "action"
0x11976  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1197b  stloc.2
0x1197c  ldloc.2
0x1197d  ldstr    aOverride// "override"
0x11982  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11987  brtrue.s loc_11998
0x11989  ldloc.2
0x1198a  ldstr    aOverwrite// "overwrite"
0x1198f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11994  brtrue.s loc_119B0
0x11996  br.s     loc_119C6
0x11998  ldarg.0
0x11999  ldarg.0
0x1199a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1199f  ldstr    aDialogLabelOve// "Dialog_Label_Override"
0x119a4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x119a9  stfld    string Microsoft.Crm.Dialogs.OverrideDynamicPropertyDialogPage::toObjName
0x119ae  br.s     loc_119C6
0x119b0  ldarg.0
0x119b1  ldarg.0
0x119b2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x119b7  ldstr    aDialogLabelOve_0// "Dialog_Label_Overwrite"
0x119bc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x119c1  stfld    string Microsoft.Crm.Dialogs.OverrideDynamicPropertyDialogPage::toObjName
0x119c6  ldarg.0
0x119c7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x119cc  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x119d1  stloc.0
0x119d2  ldloc.0
0x119d3  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x119d8  ldc.i4.0
0x119d9  conv.i8
0x119da  ble.s    loc_11A4E
0x119dc  ldloc.0
0x119dd  call     string [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::ReadXmlFromStream(class [mscorlib]System.IO.Stream)
0x119e2  stloc.3
0x119e3  ldloc.3
0x119e4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x119e9  brfalse.s loc_11A23
0x119eb  ldarg.0
0x119ec  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x119f1  ldstr    aTextXml// "text/xml"
0x119f6  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x119fb  ldarg.0
0x119fc  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x11a01  callvirt instance void [System.Web]System.Web.HttpResponse::Clear()
0x11a06  ldarg.0
0x11a07  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x11a0c  ldstr    aOk// "<ok/>"
0x11a11  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x11a16  ldarg.0
0x11a17  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x11a1c  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x11a21  br.s     loc_11A46
0x11a23  ldloc.3
0x11a24  callvirt instance int32 [mscorlib]System.String::get_Length()
0x11a29  ldc.i4.0
0x11a2a  cgt.un
0x11a2c  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x11a31  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x11a36  ldstr    aXmlLoadedFromT// "XML loaded from the stream returned Str"...
0x11a3b  ldc.i4   0x80049002
0x11a40  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x11a45  throw
0x11a46  leave.s  loc_11A4E
0x11a48  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0x11a4d  throw
0x11a4e  ldarg.0
0x11a4f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x11a54  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x11a59  stloc.1
0x11a5a  ldloc.1
0x11a5b  ldc.i4.0
0x11a5c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0x11a61  ldarg.0
0x11a62  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x11a67  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x11a6c  ldstr    aAction// "action"
0x11a71  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x11a76  stloc.2
0x11a77  ldloc.2
0x11a78  ldstr    aOverride// "override"
0x11a7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11a82  brtrue.s loc_11A96
0x11a84  ldloc.2
0x11a85  ldstr    aOverwrite// "overwrite"
0x11a8a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11a8f  brtrue.s loc_11AF9
0x11a91  br       loc_11B5A
0x11a96  ldloc.1
0x11a97  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11a9c  ldarg.0
0x11a9d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11aa2  ldstr    aDialogOverride// "Dialog_Override_Title"
0x11aa7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11aac  ldc.i4.1
0x11aad  newarr   [mscorlib]System.Object
0x11ab2  dup
0x11ab3  ldc.i4.0
0x11ab4  ldarg.0
0x11ab5  ldfld    string Microsoft.Crm.Dialogs.OverrideDynamicPropertyDialogPage::toObjName
0x11aba  stelem.ref
0x11abb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11ac0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x11ac5  ldloc.1
0x11ac6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11acb  ldarg.0
0x11acc  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11ad1  ldstr    aDialogOverride_0// "Dialog_Override_Description"
0x11ad6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11adb  ldc.i4.0
0x11adc  newarr   [mscorlib]System.Object
0x11ae1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11ae6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x11aeb  ldloc.1
0x11aec  ldc.i4.1
0x11aed  ldstr    aButtonLabelOve// "Button_Label_Override"
0x11af2  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x11af7  br.s     loc_11B5A
0x11af9  ldloc.1
0x11afa  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11aff  ldarg.0
0x11b00  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11b05  ldstr    aDialogOverwrit// "Dialog_Overwrite_Title"
0x11b0a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11b0f  ldc.i4.1
0x11b10  newarr   [mscorlib]System.Object
0x11b15  dup
0x11b16  ldc.i4.0
0x11b17  ldarg.0
0x11b18  ldfld    string Microsoft.Crm.Dialogs.OverrideDynamicPropertyDialogPage::toObjName
0x11b1d  stelem.ref
0x11b1e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11b23  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x11b28  ldloc.1
0x11b29  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x11b2e  ldarg.0
0x11b2f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x11b34  ldstr    aDialogOverwrit_0// "Dialog_Overwrite_Description"
0x11b39  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x11b3e  ldc.i4.0
0x11b3f  newarr   [mscorlib]System.Object
0x11b44  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11b49  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x11b4e  ldloc.1
0x11b4f  ldc.i4.1
0x11b50  ldstr    aButtonLabelOve_0// "Button_Label_Overwrite"
0x11b55  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x11b5a  ldloc.1
0x11b5b  ldc.i4.2
0x11b5c  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0x11b61  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0x11b66  ret
```
