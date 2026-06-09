# Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::ConfigureForm

- ea: `0xbf80`
- end: `0xc07d`
- name: `Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::ConfigureForm`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbed0`

## string_xrefs

- `0xbf99`: `Email_TemplateTarget_Title`
- `0xbfaf`: `Email_TemplateTarget_Description`
- `0xc06b`: `Email_TemplateTarget_OkButtonLabel`

## pseudocode

```c

```

## disassembly

```asm
0xbf80  ldarg.0
0xbf81  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0xbf86  ldarg.0
0xbf87  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0xbf8c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0xbf91  stloc.0
0xbf92  ldloc.0
0xbf93  ldarg.0
0xbf94  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbf99  ldstr    aEmailTemplatet// "Email_TemplateTarget_Title"
0xbf9e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbfa3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0xbfa8  ldloc.0
0xbfa9  ldarg.0
0xbfaa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xbfaf  ldstr    aEmailTemplatet_0// "Email_TemplateTarget_Description"
0xbfb4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xbfb9  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0xbfbe  ldarg.0
0xbfbf  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbfc4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xbfc9  ldstr    aOids// "oids"
0xbfce  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbfd3  ldc.i4.1
0xbfd4  newarr   [mscorlib]System.Char
0xbfd9  dup
0xbfda  ldc.i4.0
0xbfdb  ldc.i4.s 0x3B
0xbfdd  stelem.i2
0xbfde  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xbfe3  stloc.1
0xbfe4  ldarg.0
0xbfe5  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xbfea  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xbfef  ldstr    aOtypes// "otypes"
0xbff4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xbff9  ldc.i4.1
0xbffa  newarr   [mscorlib]System.Char
0xbfff  dup
0xc000  ldc.i4.0
0xc001  ldc.i4.s 0x3B
0xc003  stelem.i2
0xc004  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xc009  stloc.2
0xc00a  ldarg.0
0xc00b  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc010  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc015  ldstr    aOparts// "oparts"
0xc01a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc01f  ldc.i4.1
0xc020  newarr   [mscorlib]System.Char
0xc025  dup
0xc026  ldc.i4.0
0xc027  ldc.i4.s 0x3B
0xc029  stelem.i2
0xc02a  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xc02f  stloc.3
0xc030  ldarg.0
0xc031  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc036  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc03b  ldstr    aOnames// "onames"
0xc040  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc045  ldc.i4.1
0xc046  newarr   [mscorlib]System.Char
0xc04b  dup
0xc04c  ldc.i4.0
0xc04d  ldc.i4.s 0x3B
0xc04f  stelem.i2
0xc050  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xc055  stloc.s  4
0xc057  ldarg.0
0xc058  ldloc.1
0xc059  ldloc.2
0xc05a  ldloc.3
0xc05b  ldloc.s  4
0xc05d  call     instance void Microsoft.Crm.Common.Web.Activities.TemplateTargetDialog::FillLists(string[] arrstrObjectIds, string[] arrstrObjectTypes, string[] arrstrObjectParticipation, string[] arrstrObjectNames)
0xc062  ldloc.0
0xc063  ldc.i4.0
0xc064  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_ButtonStyle(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xc069  ldloc.0
0xc06a  ldc.i4.1
0xc06b  ldstr    aEmailTemplatet_1// "Email_TemplateTarget_OkButtonLabel"
0xc070  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles, string)
0xc075  ldloc.0
0xc076  ldc.i4.2
0xc077  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::AddButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogButtonStyles)
0xc07c  ret
```
