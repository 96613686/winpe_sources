# Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderDeleteStageIcon

- ea: `0x4c990`
- end: `0x4ca52`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::RenderDeleteStageIcon`
- size: `194`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x4c260`
- `0x4cc30`

## callees

- `0x4c220`
- `0x4c240`
- `0x4c990`
- `0x4e090`
- `0x4f7d0`
- `0xefef0`

## string_xrefs

- `0x4c9db`: `ProcessControl.Configurator.DeleteStage`
- `0x4c994`: `Expected writer to be not null.`
- `0x4c9f1`: `delete-stage`
- `0x4ca0b`: `/_imgs/processcontrol/12_inactive_config_delete.png`
- `0x4ca21`: `Expected deleteStageButtonViewModel to be not null.`
- `0x4ca3c`: `Expected deleteStageButtonViewModel to be not null.`

## pseudocode

```c

```

## disassembly

```asm
0x4c990  ldarg.1
0x4c991  ldnull
0x4c992  cgt.un
0x4c994  ldstr    aExpectedWriter// "Expected writer to be not null."
0x4c999  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4c99e  ldarg.0
0x4c99f  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewModelFactory()
0x4c9a4  ldnull
0x4c9a5  cgt.un
0x4c9a7  ldstr    aExpectedThisVi// "Expected this.ViewModelFactory to be no"...
0x4c9ac  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4c9b1  ldarg.0
0x4c9b2  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewModelFactory()
0x4c9b7  brtrue.s loc_4C9BA
0x4c9b9  ret
0x4c9ba  ldarg.0
0x4c9bb  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewFactory()
0x4c9c0  ldnull
0x4c9c1  cgt.un
0x4c9c3  ldstr    aExpectedThisVi_0// "Expected this.ViewFactory to be not nul"...
0x4c9c8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4c9cd  ldarg.0
0x4c9ce  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewFactory()
0x4c9d3  brtrue.s loc_4C9D6
0x4c9d5  ret
0x4c9d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4c9db  ldstr    aProcesscontrol_42// "ProcessControl.Configurator.DeleteStage"
0x4c9e0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4c9e5  stloc.0
0x4c9e6  ldarg.0
0x4c9e7  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewModelFactory()
0x4c9ec  ldsfld   string [mscorlib]System.String::Empty
0x4c9f1  ldstr    aDeleteStage// "delete-stage"
0x4c9f6  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x4c9fb  ldc.i4.1
0x4c9fc  newarr   [mscorlib]System.Char
0x4ca01  dup
0x4ca02  ldc.i4.0
0x4ca03  ldc.i4.s 0x2F
0x4ca05  stelem.i2
0x4ca06  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x4ca0b  ldstr    aImgsProcesscon_0// "/_imgs/processcontrol/12_inactive_confi"...
0x4ca10  call     string [mscorlib]System.String::Concat(string, string)
0x4ca15  ldloc.0
0x4ca16  ldloc.0
0x4ca17  callvirt instance class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IButtonViewModel Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IViewModelFactory::CreateButtonViewModel(string labelText, string className, string iconPath, string iconAltText, string title)
0x4ca1c  stloc.1
0x4ca1d  ldloc.1
0x4ca1e  ldnull
0x4ca1f  cgt.un
0x4ca21  ldstr    aExpectedDelete// "Expected deleteStageButtonViewModel to "...
0x4ca26  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4ca2b  ldarg.0
0x4ca2c  call     instance class Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory Microsoft.Crm.Application.ProcessControl.Configuration.BpfStageControl::get_ViewFactory()
0x4ca31  ldloc.1
0x4ca32  callvirt instance class Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.IView Microsoft.Crm.Application.ProcessControl.Configuration.Views.IViewFactory::CreateButtonView(class Microsoft.Crm.Application.ProcessControl.Configuration.ViewModels.IButtonViewModel viewModel)
0x4ca37  stloc.2
0x4ca38  ldloc.2
0x4ca39  ldnull
0x4ca3a  cgt.un
0x4ca3c  ldstr    aExpectedDelete// "Expected deleteStageButtonViewModel to "...
0x4ca41  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x4ca46  ldloc.2
0x4ca47  brtrue.s loc_4CA4A
0x4ca49  ret
0x4ca4a  ldloc.2
0x4ca4b  ldarg.1
0x4ca4c  callvirt instance void Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.Views.IView::RenderView(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x4ca51  ret
```
