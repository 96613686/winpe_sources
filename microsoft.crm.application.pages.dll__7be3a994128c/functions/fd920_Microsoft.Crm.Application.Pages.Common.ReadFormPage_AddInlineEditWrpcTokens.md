# Microsoft.Crm.Application.Pages.Common.ReadFormPage::AddInlineEditWrpcTokens

- ea: `0xfd920`
- end: `0xfda11`
- name: `Microsoft.Crm.Application.Pages.Common.ReadFormPage::AddInlineEditWrpcTokens`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xfce90`

## string_xrefs

- `0xfd9a6`: `AppGridWebService`
- `0xfd9b6`: `PaneWebService`
- `0xfd976`: `CustomerService`
- `0xfd9c6`: `ActivitiesWebService`
- `0xfd926`: `InlineEditWebService`
- `0xfda06`: `RollupFieldsWebService`
- `0xfd9f6`: `RecentlyViewedWebService`
- `0xfd936`: `LookupService`
- `0xfd946`: `LookupMruWebService`

## pseudocode

```c

```

## disassembly

```asm
0xfd920  ldarg.0
0xfd921  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd926  ldstr    aInlineeditwebs// "InlineEditWebService"
0xfd92b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd930  ldarg.0
0xfd931  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd936  ldstr    aLookupservice// "LookupService"
0xfd93b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd940  ldarg.0
0xfd941  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd946  ldstr    aLookupmruwebse// "LookupMruWebService"
0xfd94b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd950  ldarg.0
0xfd951  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd956  ldstr    aSubjectmanager// "SubjectManager"
0xfd95b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd960  ldarg.0
0xfd961  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd966  ldstr    aConnection// "Connection"
0xfd96b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd970  ldarg.0
0xfd971  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd976  ldstr    aCustomerservic// "CustomerService"
0xfd97b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd980  ldarg.0
0xfd981  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd986  ldstr    aAssociaterecor// "AssociateRecords"
0xfd98b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd990  ldarg.0
0xfd991  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd996  ldstr    aAnnotation_0// "Annotation"
0xfd99b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd9a0  ldarg.0
0xfd9a1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd9a6  ldstr    aAppgridwebserv// "AppGridWebService"
0xfd9ab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService(string)
0xfd9b0  ldarg.0
0xfd9b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd9b6  ldstr    aPanewebservice// "PaneWebService"
0xfd9bb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd9c0  ldarg.0
0xfd9c1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd9c6  ldstr    aActivitieswebs// "ActivitiesWebService"
0xfd9cb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd9d0  ldarg.0
0xfd9d1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd9d6  ldstr    aSystemcustomiz_14// "SystemCustomization"
0xfd9db  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfd9e0  ldarg.0
0xfd9e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd9e6  ldstr    aSystemcustomiz_14// "SystemCustomization"
0xfd9eb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService(string)
0xfd9f0  ldarg.0
0xfd9f1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfd9f6  ldstr    aRecentlyviewed// "RecentlyViewedWebService"
0xfd9fb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfda00  ldarg.0
0xfda01  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage::get_HeaderControl()
0xfda06  ldstr    aRollupfieldswe// "RollupFieldsWebService"
0xfda0b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xfda10  ret
```
