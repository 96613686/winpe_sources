# Microsoft.Crm.Web.Tools.Admin.AddOn.RemoveStoragePage::InitializePageSpecificVariables

- ea: `0x8c7b0`
- end: `0x8c94d`
- name: `Microsoft.Crm.Web.Tools.Admin.AddOn.RemoveStoragePage::InitializePageSpecificVariables`
- size: `413`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x8a130`
- `0x8a2e0`
- `0x8a310`
- `0x8c7b0`

## string_xrefs

- `0x8c7fa`: `AddOnWizard.RemoveStorageLicenseInputPage.Title`
- `0x8c80b`: `AddOnWizard.RemoveStorageLicenseInputPageAfterChange.Title`
- `0x8c81c`: `AddOnWizard.RemoveStorageLicenseInputPage.Description`
- `0x8c82e`: `AddOnWizard.RemoveStorageLicenseInputPageAfterChange.Description`
- `0x8c86c`: `AddOnWizard.StorageLicenseInputPage.RemoveStorageLicensesInfoText`
- `0x8c893`: `STORAGE_LICENSES_TO_REMOVE_USAGE_INFO_PURCHASE_PAGE`
- `0x8c8a4`: `STORAGE_LICENSES_TO_REMOVE_USAGE_INFO_CONFIRM_PAGE`
- `0x8c8b5`: `STORAGE_REMOVE_INFO_TEXT`

## pseudocode

```c

```

## disassembly

```asm
0x8c7b0  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SubscriptionManagementClient::.ctor()
0x8c7b5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c7ba  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8c7bf  ldc.i4.3
0x8c7c0  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.SubscriptionManagementClient::IsAddOnSupported(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.CrmLive.ClientSubscriptionManagement.ResourceType)
0x8c7c5  brtrue.s loc_8C7D2
0x8c7c7  ldarg.0
0x8c7c8  ldc.i4   0x80040277
0x8c7cd  call     instance void Microsoft.Crm.Web.Tools.Admin.AddOnBase::NavigateToErrorPage(int32 errorCode)
0x8c7d2  ldarg.0
0x8c7d3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c7d8  ldstr    aAddonwizardSto_3// "AddOnWizard.StorageLicenseInputPage.Lic"...
0x8c7dd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c7e2  stloc.0
0x8c7e3  ldarg.0
0x8c7e4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c7e9  ldstr    aAddonwizardSto_4// "AddOnWizard.StorageLicenseInputPage.Lic"...
0x8c7ee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c7f3  stloc.1
0x8c7f4  ldarg.0
0x8c7f5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c7fa  ldstr    aAddonwizardRem// "AddOnWizard.RemoveStorageLicenseInputPa"...
0x8c7ff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c804  stloc.2
0x8c805  ldarg.0
0x8c806  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c80b  ldstr    aAddonwizardRem_0// "AddOnWizard.RemoveStorageLicenseInputPa"...
0x8c810  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c815  stloc.3
0x8c816  ldarg.0
0x8c817  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c81c  ldstr    aAddonwizardRem_1// "AddOnWizard.RemoveStorageLicenseInputPa"...
0x8c821  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c826  stloc.s  4
0x8c828  ldarg.0
0x8c829  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c82e  ldstr    aAddonwizardRem_2// "AddOnWizard.RemoveStorageLicenseInputPa"...
0x8c833  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c838  stloc.s  5
0x8c83a  ldarg.0
0x8c83b  ldc.i4.3
0x8c83c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.CrmLive.ClientSubscriptionManagement.ResourcePurchaseOptions Microsoft.Crm.Web.Tools.Admin.AddOnBase::GetResources(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.CrmLive.ClientSubscriptionManagement.ResourceType resourceType)
0x8c841  dup
0x8c842  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.CrmLive.ClientSubscriptionManagement.ResourcePurchaseOptions::get_HighestChange()
0x8c847  stloc.s  6
0x8c849  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.CrmLive.ClientSubscriptionManagement.ResourcePurchaseOptions::get_LowestChange()
0x8c84e  ldc.i4.m1
0x8c84f  mul
0x8c850  stloc.s  7
0x8c852  ldloc.s  7
0x8c854  brtrue.s loc_8C861
0x8c856  ldarg.0
0x8c857  ldc.i4   0x8004B058
0x8c85c  call     instance void Microsoft.Crm.Web.Tools.Admin.AddOnBase::NavigateToErrorPage(int32 errorCode)
0x8c861  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8c866  ldarg.0
0x8c867  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8c86c  ldstr    aAddonwizardSto_7// "AddOnWizard.StorageLicenseInputPage.Rem"...
0x8c871  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8c876  ldc.i4.1
0x8c877  newarr   [mscorlib]System.Object
0x8c87c  dup
0x8c87d  ldc.i4.0
0x8c87e  ldloc.s  7
0x8c880  box      [mscorlib]System.Int32
0x8c885  stelem.ref
0x8c886  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8c88b  stloc.s  8
0x8c88d  ldarg.0
0x8c88e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c893  ldstr    aStorageLicense_4// "STORAGE_LICENSES_TO_REMOVE_USAGE_INFO_P"...
0x8c898  ldloc.0
0x8c899  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8c89e  ldarg.0
0x8c89f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c8a4  ldstr    aStorageLicense_5// "STORAGE_LICENSES_TO_REMOVE_USAGE_INFO_C"...
0x8c8a9  ldloc.1
0x8c8aa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8c8af  ldarg.0
0x8c8b0  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c8b5  ldstr    aStorageRemoveI// "STORAGE_REMOVE_INFO_TEXT"
0x8c8ba  ldloc.s  8
0x8c8bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8c8c1  ldarg.0
0x8c8c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c8c7  ldstr    aPageTitlePurch// "PAGE_TITLE_PURCHASE_PAGE"
0x8c8cc  ldloc.2
0x8c8cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8c8d2  ldarg.0
0x8c8d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c8d8  ldstr    aPageTitleConfi// "PAGE_TITLE_CONFIRM_PAGE"
0x8c8dd  ldloc.3
0x8c8de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8c8e3  ldarg.0
0x8c8e4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c8e9  ldstr    aPageDescriptio// "PAGE_DESCRIPTION_PURCHASE_PAGE"
0x8c8ee  ldloc.s  4
0x8c8f0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8c8f5  ldarg.0
0x8c8f6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c8fb  ldstr    aPageDescriptio_0// "PAGE_DESCRIPTION_CONFIRM_PAGE"
0x8c900  ldloc.s  5
0x8c902  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8c907  ldarg.0
0x8c908  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c90d  ldstr    aHighestChange// "HIGHEST_CHANGE"
0x8c912  ldloc.s  6
0x8c914  conv.i8
0x8c915  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x8c91a  ldarg.0
0x8c91b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x8c920  ldstr    aLowestChange// "LOWEST_CHANGE"
0x8c925  ldloc.s  7
0x8c927  conv.i8
0x8c928  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x8c92d  ldarg.0
0x8c92e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x8c933  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm
0x8c938  ldloc.2
0x8c939  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.WizardForm::set_PageTitle(string)
0x8c93e  leave.s  loc_8C94C
0x8c940  stloc.s  9
0x8c942  ldarg.0
0x8c943  ldloc.s  9
0x8c945  call     instance void Microsoft.Crm.Web.Tools.Admin.AddOnBase::TraceAndNavigateToErrorPage(class [System.Web.Services]System.Web.Services.Protocols.SoapException exception)
0x8c94a  leave.s  loc_8C94C
0x8c94c  ret
```
