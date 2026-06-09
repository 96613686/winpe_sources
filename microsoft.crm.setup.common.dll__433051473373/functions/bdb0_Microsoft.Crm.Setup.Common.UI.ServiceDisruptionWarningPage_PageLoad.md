# Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::PageLoad

- ea: `0xbdb0`
- end: `0xbde5`
- name: `Microsoft.Crm.Setup.Common.UI.ServiceDisruptionWarningPage::PageLoad`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x10ee0`
- `0x10fc0`
- `0x10fe0`

## string_xrefs

- `0xbdb9`: `ServiceDisruptionWarningPage.HeaderTitle`
- `0xbdcf`: `ServiceDisruptionWarningPage.HeaderDetails`

## pseudocode

```c

```

## disassembly

```asm
0xbdb0  ldarg.0
0xbdb1  ldarg.1
0xbdb2  ldarg.2
0xbdb3  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::PageLoad(object sender, class [mscorlib]System.EventArgs e)
0xbdb8  ldarg.0
0xbdb9  ldstr    aServicedisrupt// "ServiceDisruptionWarningPage.HeaderTitl"...
0xbdbe  ldc.i4.0
0xbdbf  newarr   [mscorlib]System.Object
0xbdc4  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xbdc9  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::set_HeaderTitle(string value)
0xbdce  ldarg.0
0xbdcf  ldstr    aServicedisrupt_0// "ServiceDisruptionWarningPage.HeaderDeta"...
0xbdd4  ldc.i4.0
0xbdd5  newarr   [mscorlib]System.Object
0xbdda  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xbddf  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::set_HeaderDetails(string value)
0xbde4  ret
```
