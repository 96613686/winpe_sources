# Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::ConfigureForm

- ea: `0x1270`
- end: `0x13aa`
- name: `Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::ConfigureForm`
- size: `314`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1270`

## pseudocode

```c

```

## disassembly

```asm
0x1270  ldarg.0
0x1271  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x1276  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x127b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1280  ldc.i4   0x442
0x1285  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x128a  stloc.0
0x128b  ldarg.0
0x128c  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::selStatus
0x1291  ldloc.0
0x1292  ldstr    aStatuscode// "statuscode"
0x1297  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x129c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x12a1  ldarg.0
0x12a2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x12a7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x12ac  ldstr    aClosedstate// "closedstate"
0x12b1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x12b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12bb  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x12c0  ldstr    aInvoice// "invoice"
0x12c5  ldc.i4.2
0x12c6  stloc.1
0x12c7  ldloca.s 1
0x12c9  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.InvoiceState
0x12cf  callvirt instance string [mscorlib]System.Object::ToString()
0x12d4  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x12d9  bne.un.s loc_1336
0x12db  ldarg.0
0x12dc  ldarg.0
0x12dd  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12e2  ldstr    aDialogPaidinvo// "Dialog_PaidInvoice_Title"
0x12e7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12ec  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x12f1  ldarg.0
0x12f2  ldarg.0
0x12f3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x12f8  ldstr    aDialogPaidinvo_0// "Dialog_PaidInvoice_Description"
0x12fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1302  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x1307  ldarg.0
0x1308  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::selStatus
0x130d  ldc.i4.1
0x130e  newarr   [mscorlib]System.Int32
0x1313  dup
0x1314  ldc.i4.0
0x1315  ldstr    aInvoice// "invoice"
0x131a  ldc.i4.2
0x131b  stloc.1
0x131c  ldloca.s 1
0x131e  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.InvoiceState
0x1324  callvirt instance string [mscorlib]System.Object::ToString()
0x1329  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x132e  stelem.i4
0x132f  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x1334  br.s     loc_138F
0x1336  ldarg.0
0x1337  ldarg.0
0x1338  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x133d  ldstr    aDialogCancelin// "Dialog_CancelInvoice_Title"
0x1342  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1347  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0x134c  ldarg.0
0x134d  ldarg.0
0x134e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1353  ldstr    aDialogCancelin_0// "Dialog_CancelInvoice_Description"
0x1358  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x135d  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogDescription(string)
0x1362  ldarg.0
0x1363  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl Microsoft.Crm.Sales.Web.Sfa.InvoiceCloseDetailPage::selStatus
0x1368  ldc.i4.1
0x1369  newarr   [mscorlib]System.Int32
0x136e  dup
0x136f  ldc.i4.0
0x1370  ldstr    aInvoice// "invoice"
0x1375  ldc.i4.3
0x1376  stloc.1
0x1377  ldloca.s 1
0x1379  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.InvoiceState
0x137f  callvirt instance string [mscorlib]System.Object::ToString()
0x1384  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateToNumber(string, string)
0x1389  stelem.i4
0x138a  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistStatusControl::set_States(int32[])
0x138f  ldarg.0
0x1390  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x1395  ldc.i4.1
0x1396  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x139b  pop
0x139c  ldarg.0
0x139d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0x13a2  ldc.i4.2
0x13a3  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButton(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0x13a8  pop
0x13a9  ret
```
