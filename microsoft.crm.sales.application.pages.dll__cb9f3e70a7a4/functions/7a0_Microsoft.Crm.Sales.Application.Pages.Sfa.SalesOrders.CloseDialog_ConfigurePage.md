# Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::ConfigurePage

- ea: `0x7a0`
- end: `0x8a0`
- name: `Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::ConfigurePage`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7a0`

## pseudocode

```c

```

## disassembly

```asm
0x7a0  ldarg.0
0x7a1  ldarg.0
0x7a2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x7a7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x7ac  ldstr    aClosedstate// "closedstate"
0x7b1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x7b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7bb  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x7c0  ldstr    aSalesorder// "salesorder"
0x7c5  ldc.i4.3
0x7c6  stloc.1
0x7c7  ldloca.s 1
0x7c9  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.SalesOrderState
0x7cf  callvirt instance string [mscorlib]System.Object::ToString()
0x7d4  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x7d9  ceq
0x7db  stfld    bool Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::IsOrderFulfillDialog
0x7e0  ldarg.0
0x7e1  ldfld    bool Microsoft.Crm.Sales.Application.Pages.Sfa.SalesOrders.CloseDialog::IsOrderFulfillDialog
0x7e6  brfalse.s loc_837
0x7e8  ldarg.0
0x7e9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x7ee  ldarg.0
0x7ef  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x7f4  ldstr    aWebSfaSalesord// "Web.SFA.salesorders.aspx_11.dlg_close"
0x7f9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7fe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x803  ldarg.0
0x804  ldarg.0
0x805  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x80a  ldstr    aOrderFulfillDl// "Order_Fulfill_Dlg_Title"
0x80f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x814  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x819  ldarg.0
0x81a  ldarg.0
0x81b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x820  ldstr    aOrderFulfillDl_0// "Order_Fulfill_Dlg_Desc"
0x825  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x82a  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x82f  ldstr    aWebSfaSalesord_0// "Web.SFA.salesorders.aspx_FulfillButton."...
0x834  stloc.0
0x835  br.s     loc_884
0x837  ldarg.0
0x838  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x83d  ldarg.0
0x83e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x843  ldstr    aWebSfaSalesord_1// "Web.SFA.salesorders.aspx_10.dlg_close"
0x848  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x84d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x852  ldarg.0
0x853  ldarg.0
0x854  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x859  ldstr    aOrderCancelDlg// "Order_Cancel_Dlg_Title"
0x85e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x863  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x868  ldarg.0
0x869  ldarg.0
0x86a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x86f  ldstr    aOrderCancelDlg_0// "Order_Cancel_Dlg_Desc"
0x874  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x879  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x87e  ldstr    aWebSfaSalesord_2// "Web.SFA.salesorders.aspx_ConfirmButton."...
0x883  stloc.0
0x884  ldarg.0
0x885  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x88a  ldc.i4.1
0x88b  ldloc.0
0x88c  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons, string)
0x891  pop
0x892  ldarg.0
0x893  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x898  ldc.i4.2
0x899  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x89e  pop
0x89f  ret
```
