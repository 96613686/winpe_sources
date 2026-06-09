# Microsoft.Crm.Setup.Common.UI.WizardPage::add_PageActivated

- ea: `0x10ac0`
- end: `0x10ae9`
- name: `Microsoft.Crm.Setup.Common.UI.WizardPage::add_PageActivated`
- size: `41`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4a10`
- `0x57c0`
- `0x8130`
- `0x87e0`
- `0x9f10`
- `0xb8f0`
- `0xbd50`
- `0xc5a0`

## callees

- `0x10ac0`

## pseudocode

```c

```

## disassembly

```asm
0x10ac0  ldarg.0
0x10ac1  ldfld    class [mscorlib]System.EventHandler Microsoft.Crm.Setup.Common.UI.WizardPage::PageActivated
0x10ac6  stloc.0
0x10ac7  ldloc.0
0x10ac8  stloc.1
0x10ac9  ldloc.1
0x10aca  ldarg.1
0x10acb  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x10ad0  castclass [mscorlib]System.EventHandler
0x10ad5  stloc.2
0x10ad6  ldarg.0
0x10ad7  ldflda   class [mscorlib]System.EventHandler Microsoft.Crm.Setup.Common.UI.WizardPage::PageActivated
0x10adc  ldloc.2
0x10add  ldloc.1
0x10ade  call     T0x2B00000C
0x10ae3  stloc.0
0x10ae4  ldloc.0
0x10ae5  ldloc.1
0x10ae6  bne.un.s loc_10AC7
0x10ae8  ret
```
