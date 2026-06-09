# Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::RenderDeleteIcon

- ea: `0x4d2b0`
- end: `0x4d372`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::RenderDeleteIcon`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x4cf80`
- `0x4d430`

## callees

- `0x4cee0`
- `0x4cf00`
- `0x4d2b0`
- `0x4e090`
- `0x4f7d0`
- `0xefef0`

## string_xrefs

- `0x4d2fb`: `ProcessControl.Configurator.DeleteStep`
- `0x4d2b4`: `Expected writer to be not null.`
- `0x4d32b`: `/_imgs/processcontrol/12_inactive_config_delete.png`
- `0x4d311`: `delete-step`
- `0x4d341`: `Expected deleteStepButtonViewModel to be not null.`
- `0x4d35c`: `Expected deleteStepButtonViewModel to be not null.`

## pseudocode

```c

```

## disassembly

```asm
0x4d2b0  ldarg.1
0x4d2b1  ldnull
0x4d2b2  cgt.un
0x4d2b4  ldstr    aExpectedWriter// "Expected writer to be not null."
0x4d2b9  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4d2be  ldarg.0
0x4d2bf  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_ViewModelFactory()
0x4d2c4  ldnull
0x4d2c5  cgt.un
0x4d2c7  ldstr    aExpectedThisVi// "Expected this.ViewModelFactory to be no"...
0x4d2cc  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4d2d1  ldarg.0
0x4d2d2  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_ViewModelFactory()
0x4d2d7  brtrue.s loc_4D2DA
0x4d2d9  ret
0x4d2da  ldarg.0
0x4d2db  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_ViewFactory()
0x4d2e0  ldnull
0x4d2e1  cgt.un
0x4d2e3  ldstr    aExpectedThisVi_0// "Expected this.ViewFactory to be not nul"...
0x4d2e8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4d2ed  ldarg.0
0x4d2ee  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_ViewFactory()
0x4d2f3  brtrue.s loc_4D2F6
0x4d2f5  ret
0x4d2f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4d2fb  ldstr    aProcesscontrol_44// "ProcessControl.Configurator.DeleteStep"
0x4d300  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4d305  stloc.0
0x4d306  ldarg.0
0x4d307  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_ViewModelFactory()
0x4d30c  ldsfld   string [mscorlib]System.String::Empty
0x4d311  ldstr    aDeleteStep// "delete-step"
0x4d316  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x4d31b  ldc.i4.1
0x4d31c  newarr   [mscorlib]System.Char
0x4d321  dup
0x4d322  ldc.i4.0
0x4d323  ldc.i4.s 0x2F
0x4d325  stelem.i2
0x4d326  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x4d32b  ldstr    aImgsProcesscon_0// "/_imgs/processcontrol/12_inactive_confi"...
0x4d330  call     string [mscorlib]System.String::Concat(string, string)
0x4d335  ldloc.0
0x4d336  ldloc.0
0x4d337  callvirt instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IButtonViewModel Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory::CreateButtonViewModel(string labelText, string className, string iconPath, string iconAltText, string title)
0x4d33c  stloc.1
0x4d33d  ldloc.1
0x4d33e  ldnull
0x4d33f  cgt.un
0x4d341  ldstr    aExpectedDelete_0// "Expected deleteStepButtonViewModel to b"...
0x4d346  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4d34b  ldarg.0
0x4d34c  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStepControl::get_ViewFactory()
0x4d351  ldloc.1
0x4d352  callvirt instance class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.IView Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory::CreateButtonView(class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IButtonViewModel viewModel)
0x4d357  stloc.2
0x4d358  ldloc.2
0x4d359  ldnull
0x4d35a  cgt.un
0x4d35c  ldstr    aExpectedDelete_0// "Expected deleteStepButtonViewModel to b"...
0x4d361  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4d366  ldloc.2
0x4d367  brtrue.s loc_4D36A
0x4d369  ret
0x4d36a  ldloc.2
0x4d36b  ldarg.1
0x4d36c  callvirt instance void Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.IView::RenderView(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x4d371  ret
```
