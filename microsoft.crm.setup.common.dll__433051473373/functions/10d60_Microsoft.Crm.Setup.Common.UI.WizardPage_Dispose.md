# Microsoft.Crm.Setup.Common.UI.WizardPage::Dispose

- ea: `0x10d60`
- end: `0x10d7e`
- name: `Microsoft.Crm.Setup.Common.UI.WizardPage::Dispose`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4b50`
- `0x5720`
- `0x8110`
- `0x87c0`
- `0x9ef0`
- `0xb8b0`
- `0xc040`
- `0xc580`

## callees

- `0x10d60`

## pseudocode

```c

```

## disassembly

```asm
0x10d60  ldarg.1
0x10d61  brfalse.s loc_10D76
0x10d63  ldarg.0
0x10d64  ldfld    class [System]System.ComponentModel.Container Microsoft.Crm.Setup.Common.UI.WizardPage::components
0x10d69  brfalse.s loc_10D76
0x10d6b  ldarg.0
0x10d6c  ldfld    class [System]System.ComponentModel.Container Microsoft.Crm.Setup.Common.UI.WizardPage::components
0x10d71  callvirt instance void [System]System.ComponentModel.Container::Dispose()
0x10d76  ldarg.0
0x10d77  ldarg.1
0x10d78  call     instance void [System.Windows.Forms]System.Windows.Forms.ContainerControl::Dispose(bool)
0x10d7d  ret
```
