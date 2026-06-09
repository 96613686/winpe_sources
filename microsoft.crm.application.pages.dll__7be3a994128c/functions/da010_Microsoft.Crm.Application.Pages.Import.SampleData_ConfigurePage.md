# Microsoft.Crm.Application.Pages.Import.SampleData::ConfigurePage

- ea: `0xda010`
- end: `0xda29a`
- name: `Microsoft.Crm.Application.Pages.Import.SampleData::ConfigurePage`
- size: `650`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xd9fb0`
- `0xda010`
- `0xda2a0`
- `0xda3d0`
- `0xda480`

## string_xrefs

- `0xda023`: `ImportWebService`
- `0xda039`: `installsoln`
- `0xda097`: `SampleData.SampleDataDialog.Status.Installed`
- `0xda0bd`: `SampleData.SampleDataDialog.Status.NotInstalled`
- `0xda127`: `SAMPLE_DATA_UNINSTALLING`
- `0xda132`: `SampleData.SampleDataDialog.Status.UninstallationStarted`
- `0xda147`: `SAMPLE_DATA_INSTALLING`
- `0xda152`: `SampleData.SampleDataDialog.Status.InstallationStarted`
- `0xda1cc`: `BUSINESS_PROCESS_INSTALLED`
- `0xda1d7`: `InstallBusinessProcess.InstallBusinessProcessDialog.Status.ProcessesIsInstalled`
- `0xda1ec`: `BUSINESS_PROCESS_IS_BEING_INSTALLED`
- `0xda1f7`: `InstallBusinessProcess.InstallBusinessProcessDialog.Status.ProcessesIsBeingInstalled`
- `0xda20c`: `BUSINESS_PROCESS_NOT_INSTALLED`
- `0xda217`: `InstallBusinessProcess.InstallBusinessProcessDialog.Status.ProcessesIsNotInstalled`
- `0xda22d`: `InstallBusinessProcess.InstallBusinessProcessDialog.Title`
- `0xda262`: `installsamplesolutions()`

## pseudocode

```c

```

## disassembly

```asm
0xda010  ldarg.0
0xda011  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xda016  ldc.i4.s 0x10
0xda018  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::AddStandardButtons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.StandardDialogButtons)
0xda01d  ldarg.0
0xda01e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda023  ldstr    aImportwebservi// "ImportWebService"
0xda028  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xda02d  ldarg.0
0xda02e  ldarg.0
0xda02f  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xda034  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xda039  ldstr    aInstallsoln// "installsoln"
0xda03e  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xda043  stfld    string Microsoft.Crm.Application.Pages.Import.SampleData::_installSoln
0xda048  ldarg.0
0xda049  ldc.i4.0
0xda04a  stfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_hideInstallOrUninstallButton
0xda04f  ldarg.0
0xda050  ldfld    string Microsoft.Crm.Application.Pages.Import.SampleData::_installSoln
0xda055  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xda05a  brfalse  loc_DA1C6
0xda05f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Data.InitialSolutionDataManager::.ctor()
0xda064  stloc.0
0xda065  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0xda06a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_OrganizationId()
0xda06f  stloc.1
0xda070  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0xda075  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetSku()
0xda07a  ldc.i4.2
0xda07b  bne.un.s loc_DA086
0xda07d  ldarg.0
0xda07e  ldloc.1
0xda07f  call     instance bool Microsoft.Crm.Application.Pages.Import.SampleData::UseImprovedSampleData(valuetype [mscorlib]System.Guid organizationId)
0xda084  br.s     loc_DA087
0xda086  ldc.i4.0
0xda087  ldnull
0xda088  stloc.2
0xda089  brfalse.s loc_DA0D8
0xda08b  ldloc.0
0xda08c  ldloc.1
0xda08d  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Data.InitialSolutionSampleDataState [Microsoft.Crm]Microsoft.Crm.Data.InitialSolutionDataManager::GetState(valuetype [mscorlib]System.Guid)
0xda092  stloc.3
0xda093  ldloc.3
0xda094  ldc.i4.1
0xda095  bne.un.s loc_DA0A6
0xda097  ldstr    aSampledataSamp// "SampleData.SampleDataDialog.Status.Inst"...
0xda09c  stloc.2
0xda09d  ldarg.0
0xda09e  ldc.i4.1
0xda09f  stfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_sampleDataInstalled
0xda0a4  br.s     loc_DA111
0xda0a6  ldloc.3
0xda0a7  ldc.i4.4
0xda0a8  bne.un.s loc_DA0B9
0xda0aa  ldstr    aSampledataSamp_0// "SampleData.SampleDataDialog.Status.InPr"...
0xda0af  stloc.2
0xda0b0  ldarg.0
0xda0b1  ldc.i4.1
0xda0b2  stfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_hideInstallOrUninstallButton
0xda0b7  br.s     loc_DA111
0xda0b9  ldloc.3
0xda0ba  ldc.i4.3
0xda0bb  bne.un.s loc_DA0C5
0xda0bd  ldstr    aSampledataSamp_1// "SampleData.SampleDataDialog.Status.NotI"...
0xda0c2  stloc.2
0xda0c3  br.s     loc_DA111
0xda0c5  ldloc.3
0xda0c6  ldc.i4.2
0xda0c7  bne.un.s loc_DA111
0xda0c9  ldstr    aSampledataSamp_0// "SampleData.SampleDataDialog.Status.InPr"...
0xda0ce  stloc.2
0xda0cf  ldarg.0
0xda0d0  ldc.i4.1
0xda0d1  stfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_hideInstallOrUninstallButton
0xda0d6  br.s     loc_DA111
0xda0d8  ldarg.0
0xda0d9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SubscriptionLifecycleUtility::get_IsSampleDataInstalled()
0xda0de  stfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_sampleDataInstalled
0xda0e3  ldarg.0
0xda0e4  ldfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_sampleDataInstalled
0xda0e9  brtrue.s loc_DA111
0xda0eb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0xda0f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SampleDataImportId()
0xda0f5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xda0fa  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xda0ff  brfalse.s loc_DA111
0xda101  ldarg.0
0xda102  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xda107  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SubscriptionLifecycleUtility::GetSampleDataImportStatus(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xda10c  stfld    int32 Microsoft.Crm.Application.Pages.Import.SampleData::_sampleDataImportStatus
0xda111  ldarg.0
0xda112  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda117  ldstr    aFormsControlsF// "/_forms/controls/form.css.aspx"
0xda11c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xda121  ldarg.0
0xda122  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda127  ldstr    aSampleDataUnin// "SAMPLE_DATA_UNINSTALLING"
0xda12c  ldarg.0
0xda12d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda132  ldstr    aSampledataSamp_2// "SampleData.SampleDataDialog.Status.Unin"...
0xda137  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda13c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xda141  ldarg.0
0xda142  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda147  ldstr    aSampleDataInst// "SAMPLE_DATA_INSTALLING"
0xda14c  ldarg.0
0xda14d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda152  ldstr    aSampledataSamp_3// "SampleData.SampleDataDialog.Status.Inst"...
0xda157  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda15c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xda161  ldarg.0
0xda162  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda167  ldstr    aSampleDataFail// "SAMPLE_DATA_FAILED"
0xda16c  ldarg.0
0xda16d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda172  ldstr    aSampledataSamp_4// "SampleData.SampleDataDialog.Status.Fail"...
0xda177  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda17c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xda181  ldarg.0
0xda182  ldarg.0
0xda183  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda188  ldstr    aDatamanagement_13// "DataManagement.SampleData.Title"
0xda18d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda192  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xda197  ldarg.0
0xda198  call     instance void Microsoft.Crm.Application.Pages.Import.SampleData::AddInstallUninstallButton()
0xda19d  ldarg.0
0xda19e  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xda1a3  ldstr    aButclose// "butClose"
0xda1a8  ldstr    aButtonLabelClo// "Button_Label_Close"
0xda1ad  ldstr    aClosewindow// "closeWindow();"
0xda1b2  ldc.i4.0
0xda1b3  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0xda1b8  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0xda1bd  pop
0xda1be  ldarg.0
0xda1bf  ldloc.2
0xda1c0  call     instance void Microsoft.Crm.Application.Pages.Import.SampleData::SetStatus(string resourceId)
0xda1c5  ret
0xda1c6  ldarg.0
0xda1c7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda1cc  ldstr    aBusinessProces// "BUSINESS_PROCESS_INSTALLED"
0xda1d1  ldarg.0
0xda1d2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda1d7  ldstr    aInstallbusines// "InstallBusinessProcess.InstallBusinessP"...
0xda1dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda1e1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xda1e6  ldarg.0
0xda1e7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda1ec  ldstr    aBusinessProces_0// "BUSINESS_PROCESS_IS_BEING_INSTALLED"
0xda1f1  ldarg.0
0xda1f2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda1f7  ldstr    aInstallbusines_0// "InstallBusinessProcess.InstallBusinessP"...
0xda1fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda201  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xda206  ldarg.0
0xda207  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xda20c  ldstr    aBusinessProces_1// "BUSINESS_PROCESS_NOT_INSTALLED"
0xda211  ldarg.0
0xda212  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda217  ldstr    aInstallbusines_1// "InstallBusinessProcess.InstallBusinessP"...
0xda21c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda221  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xda226  ldarg.0
0xda227  ldarg.0
0xda228  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xda22d  ldstr    aInstallbusines_2// "InstallBusinessProcess.InstallBusinessP"...
0xda232  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xda237  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
0xda23c  ldarg.0
0xda23d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xda242  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SubscriptionLifecycleUtility::IsSampleBusinessProcessInstalled(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xda247  stfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_sampleBusinessProcessinstalled
0xda24c  ldarg.0
0xda24d  call     instance void Microsoft.Crm.Application.Pages.Import.SampleData::SetBusinessPorcessStatus()
0xda252  ldarg.0
0xda253  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xda258  ldstr    aButtonadd// "buttonAdd"
0xda25d  ldstr    aButtonLabelAdd// "Button_Label_Add"
0xda262  ldstr    aInstallsamples// "installsamplesolutions()"
0xda267  ldarg.0
0xda268  ldfld    bool Microsoft.Crm.Application.Pages.Import.SampleData::_sampleBusinessProcessinstalled
0xda26d  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0xda272  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0xda277  pop
0xda278  ldarg.0
0xda279  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::get_Buttons()
0xda27e  ldstr    aButtoncancel// "buttonCancel"
0xda283  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xda288  ldstr    aClosewindow// "closeWindow();"
0xda28d  ldc.i4.0
0xda28e  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton::.ctor(string, string, string, bool)
0xda293  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButtonCollection::Add(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogButton)
0xda298  pop
0xda299  ret
```
