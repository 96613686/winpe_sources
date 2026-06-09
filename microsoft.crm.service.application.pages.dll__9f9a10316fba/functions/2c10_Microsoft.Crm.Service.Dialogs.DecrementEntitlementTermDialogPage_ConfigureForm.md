# Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::ConfigureForm

- ea: `0x2c10`
- end: `0x2d80`
- name: `Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::ConfigureForm`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x2bf0`
- `0x2c10`
- `0x2d80`

## string_xrefs

- `0x2cf9`: `DontDecrementTermsSet_RecordAssociated_CaseTerms_DecrementedAlready_DialogTitle`
- `0x2d0f`: `DontDecrementTermsSet_RecordAssociated_CaseTerms_DecrementedAlready_DialogMessage`

## pseudocode

```c

```

## disassembly

```asm
0x2c10  ldarg.0
0x2c11  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2c16  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x2c1b  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x2c20  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x2c25  ldarg.0
0x2c26  ldarg.0
0x2c27  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2c2c  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2c31  ldstr    aRequesttype// "requestType"
0x2c36  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2c3b  stfld    string Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::requestType
0x2c40  ldarg.0
0x2c41  ldarg.0
0x2c42  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2c47  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2c4c  ldstr    aIid// "iId"
0x2c51  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2c56  stfld    string Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::incidentId
0x2c5b  ldarg.0
0x2c5c  ldc.i4   0x25E4
0x2c61  call     instance void Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::set_EntityTypeCode(int32 value)
0x2c66  ldarg.0
0x2c67  ldarg.0
0x2c68  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2c6d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2c72  ldstr    aReason// "reason"
0x2c77  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2c7c  stfld    string Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::reasonType
0x2c81  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2c86  brtrue   loc_2D79
0x2c8b  ldarg.0
0x2c8c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x2c91  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x2c96  stloc.0
0x2c97  ldarg.0
0x2c98  ldfld    string Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::reasonType
0x2c9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ca2  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x2ca7  stloc.1
0x2ca8  ldloc.1
0x2ca9  ldc.i4.1
0x2caa  sub
0x2cab  switch   loc_2CC5, loc_2CF2, loc_2D1F, loc_2D4C
0x2cc0  br       loc_2D79
0x2cc5  ldloc.0
0x2cc6  ldarg.0
0x2cc7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2ccc  ldstr    aDontdecrementt// "DontDecrementTerms_Not_Set_DialogTitle"
0x2cd1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cd6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2cdb  ldloc.0
0x2cdc  ldarg.0
0x2cdd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2ce2  ldstr    aDontdecrementt_0// "DontDecrementTerms_Not_Set_DialogMessag"...
0x2ce7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cec  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x2cf1  ret
0x2cf2  ldloc.0
0x2cf3  ldarg.0
0x2cf4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2cf9  ldstr    aDontdecrementt_1// "DontDecrementTermsSet_RecordAssociated_"...
0x2cfe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d03  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2d08  ldloc.0
0x2d09  ldarg.0
0x2d0a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d0f  ldstr    aDontdecrementt_2// "DontDecrementTermsSet_RecordAssociated_"...
0x2d14  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d19  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x2d1e  ret
0x2d1f  ldloc.0
0x2d20  ldarg.0
0x2d21  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d26  ldstr    aDontdecrementt_3// "DontDecrementTermsSet_RecordAssociated_"...
0x2d2b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d30  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2d35  ldloc.0
0x2d36  ldarg.0
0x2d37  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d3c  ldstr    aDontdecrementt_4// "DontDecrementTermsSet_RecordAssociated_"...
0x2d41  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d46  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x2d4b  ret
0x2d4c  ldloc.0
0x2d4d  ldarg.0
0x2d4e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d53  ldstr    aDontdecrementt_5// "DontDecrementTermsSet_Record_Not_Yet_As"...
0x2d58  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d5d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x2d62  ldloc.0
0x2d63  ldarg.0
0x2d64  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2d69  ldstr    aDontdecrementt_6// "DontDecrementTermsSet_Record_NotYet_Ass"...
0x2d6e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d73  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x2d78  ret
0x2d79  ldarg.0
0x2d7a  call     instance void Microsoft.Crm.Service.Dialogs.DecrementEntitlementTermDialogPage::OnPostBack()
0x2d7f  ret
```
