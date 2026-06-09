# Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::ConfigureForm

- ea: `0x28d0`
- end: `0x29b1`
- name: `Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::ConfigureForm`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x28b0`
- `0x28d0`
- `0x29c0`

## pseudocode

```c

```

## disassembly

```asm
0x28d0  ldarg.0
0x28d1  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x28d6  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x28db  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x28e0  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x28e5  ldarg.0
0x28e6  ldarg.0
0x28e7  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x28ec  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x28f1  ldstr    aRequesttype// "requestType"
0x28f6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x28fb  stfld    string Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::requestType
0x2900  ldarg.0
0x2901  ldarg.0
0x2902  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2907  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x290c  ldstr    aCustomerid// "customerId"
0x2911  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2916  stfld    string Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::customerId
0x291b  ldarg.0
0x291c  ldarg.0
0x291d  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x2922  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x2927  ldstr    aDefaultexists// "defaultexists"
0x292c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2931  stfld    string Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::defaultExists
0x2936  ldarg.0
0x2937  ldc.i4   0x25E4
0x293c  call     instance void Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::set_EntityTypeCode(int32 value)
0x2941  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2946  brtrue.s loc_29AA
0x2948  ldarg.0
0x2949  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x294e  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm
0x2953  stloc.0
0x2954  ldloc.0
0x2955  ldarg.0
0x2956  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x295b  ldstr    aEntitlementDef// "Entitlement_Default_Confirmation_Dialog"...
0x2960  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2965  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogTitle(string)
0x296a  ldarg.0
0x296b  ldfld    string Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::defaultExists
0x2970  ldstr    aTrue// "true"
0x2975  call     bool [mscorlib]System.String::op_Equality(string, string)
0x297a  brfalse.s loc_2993
0x297c  ldloc.0
0x297d  ldarg.0
0x297e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2983  ldstr    aEntitlementDef_0// "Entitlement_Default_Change_Confirmation"...
0x2988  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x298d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x2992  ret
0x2993  ldloc.0
0x2994  ldarg.0
0x2995  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x299a  ldstr    aEntitlementDef_1// "Entitlement_Default_Confirmation_Messag"...
0x299f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x29a4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DialogForm::set_DialogDescription(string)
0x29a9  ret
0x29aa  ldarg.0
0x29ab  call     instance void Microsoft.Crm.Service.Dialogs.DefaultEntitlementConfirmationDialogPage::OnPostBack()
0x29b0  ret
```
