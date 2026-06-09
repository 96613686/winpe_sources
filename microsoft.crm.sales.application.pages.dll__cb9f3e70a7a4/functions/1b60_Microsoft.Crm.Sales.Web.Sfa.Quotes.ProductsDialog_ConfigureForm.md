# Microsoft.Crm.Sales.Web.Sfa.Quotes.ProductsDialog::ConfigureForm

- ea: `0x1b60`
- end: `0x1c21`
- name: `Microsoft.Crm.Sales.Web.Sfa.Quotes.ProductsDialog::ConfigureForm`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1b60`

## pseudocode

```c

```

## disassembly

```asm
0x1b60  ldarg.0
0x1b61  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1b66  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1b6b  ldstr    aOpportunityid// "opportunityid"
0x1b70  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1b75  stloc.0
0x1b76  ldarg.0
0x1b77  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Sales.Web.Sfa.Quotes.ProductsDialog::lookupOpportunity
0x1b7c  ldc.i4.1
0x1b7d  newarr   [mscorlib]System.Int32
0x1b82  dup
0x1b83  ldc.i4.0
0x1b84  ldc.i4.3
0x1b85  stelem.i4
0x1b86  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupTypes(int32[])
0x1b8b  ldloc.0
0x1b8c  brfalse.s loc_1BB9
0x1b8e  ldloc.0
0x1b8f  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1b94  ldc.i4.0
0x1b95  ble.s    loc_1BB9
0x1b97  ldarg.0
0x1b98  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl Microsoft.Crm.Sales.Web.Sfa.Quotes.ProductsDialog::lookupOpportunity
0x1b9d  ldloc.0
0x1b9e  ldc.i4.3
0x1b9f  ldarg.0
0x1ba0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1ba5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1baa  ldstr    aName// "name"
0x1baf  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1bb4  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::AddItem(string, int32, string)
0x1bb9  ldarg.0
0x1bba  ldarg.0
0x1bbb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1bc0  ldstr    aQuoteProductDl// "Quote_Product_Dlg_Title"
0x1bc5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1bca  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x1bcf  ldarg.0
0x1bd0  ldarg.0
0x1bd1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1bd6  ldstr    aQuoteProductDl_0// "Quote_Product_Dlg_Desc"
0x1bdb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1be0  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x1be5  ldarg.0
0x1be6  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x1beb  ldc.i4.1
0x1bec  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x1bf1  pop
0x1bf2  ldarg.0
0x1bf3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x1bf8  ldc.i4.2
0x1bf9  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x1bfe  pop
0x1bff  ldarg.0
0x1c00  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x1c05  ldstr    aLocidOpportuni// "LOCID_OPPORTUNITY_NOT_SELECTED"
0x1c0a  ldarg.0
0x1c0b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1c10  ldstr    aWebSfaQuotesDl_3// "Web.SFA.quotes.dlg_products.aspx_26"
0x1c15  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1c1a  ldc.i4.0
0x1c1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1c20  ret
```
