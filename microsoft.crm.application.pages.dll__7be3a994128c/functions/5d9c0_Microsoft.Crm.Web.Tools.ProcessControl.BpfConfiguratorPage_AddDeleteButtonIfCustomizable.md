# Microsoft.Crm.Web.Tools.ProcessControl.BpfConfiguratorPage::AddDeleteButtonIfCustomizable

- ea: `0x5d9c0`
- end: `0x5da2c`
- name: `Microsoft.Crm.Web.Tools.ProcessControl.BpfConfiguratorPage::AddDeleteButtonIfCustomizable`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x5d7d0`

## callees

- `0x5d9c0`
- `0x5dca0`

## string_xrefs

- `0x5da0f`: `Delete`
- `0x5d9ff`: `/_imgs/ico_16_delete.gif`
- `0x5d9d8`: `_deleteActionEnabled`
- `0x5da20`: `_deleteActionEnabled`
- `0x5d9e5`: `ProcessControl.Configurator.Delete`
- `0x5da09`: `ProcessControl.Configurator.DeleteBusinessProcess`

## pseudocode

```c

```

## disassembly

```asm
0x5d9c0  ldarg.0
0x5d9c1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x5d9c6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_CurrentEntity()
0x5d9cb  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_IsInstanceCustomizable()
0x5d9d0  brfalse.s loc_5DA1A
0x5d9d2  ldarg.0
0x5d9d3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5d9d8  ldstr    aDeleteactionen// "_deleteActionEnabled"
0x5d9dd  ldc.i4.1
0x5d9de  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x5d9e3  ldarg.0
0x5d9e4  ldarg.1
0x5d9e5  ldstr    aProcesscontrol_0// "ProcessControl.Configurator.Delete"
0x5d9ea  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x5d9ef  ldc.i4.1
0x5d9f0  newarr   [mscorlib]System.Char
0x5d9f5  dup
0x5d9f6  ldc.i4.0
0x5d9f7  ldc.i4.s 0x2F
0x5d9f9  stelem.i2
0x5d9fa  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x5d9ff  ldstr    aImgsIco16Delet// "/_imgs/ico_16_delete.gif"
0x5da04  call     string [mscorlib]System.String::Concat(string, string)
0x5da09  ldstr    aProcesscontrol_1// "ProcessControl.Configurator.DeleteBusin"...
0x5da0e  ldc.i4.1
0x5da0f  ldstr    aDelete// "Delete"
0x5da14  call     instance void Microsoft.Crm.Web.Tools.ProcessControl.BpfConfiguratorPage::AddButton(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs e, string title, string iconUrl, string tooltipResource, bool flipImageInRTL, string action)
0x5da19  ret
0x5da1a  ldarg.0
0x5da1b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x5da20  ldstr    aDeleteactionen// "_deleteActionEnabled"
0x5da25  ldc.i4.0
0x5da26  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0x5da2b  ret
```
