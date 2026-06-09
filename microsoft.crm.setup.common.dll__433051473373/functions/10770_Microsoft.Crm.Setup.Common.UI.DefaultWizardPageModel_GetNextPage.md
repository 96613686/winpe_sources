# Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::GetNextPage

- ea: `0x10770`
- end: `0x107b1`
- name: `Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::GetNextPage`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10770`

## callees

- `0x106a0`
- `0x10770`
- `0x108b0`
- `0x109b0`
- `0x110e0`

## pseudocode

```c

```

## disassembly

```asm
0x10770  ldarg.0
0x10771  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_Pages()
0x10776  ldarg.1
0x10777  callvirt instance int32 Microsoft.Crm.Setup.Common.UI.WizardPageCollection::IndexOf(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x1077c  stloc.0
0x1077d  ldloc.0
0x1077e  ldc.i4.0
0x1077f  blt.s    loc_10791
0x10781  ldloc.0
0x10782  ldarg.0
0x10783  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_Pages()
0x10788  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1078d  ldc.i4.1
0x1078e  sub
0x1078f  blt.s    loc_10794
0x10791  ldnull
0x10792  br.s     loc_107A2
0x10794  ldarg.0
0x10795  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_Pages()
0x1079a  ldloc.0
0x1079b  ldc.i4.1
0x1079c  add
0x1079d  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageCollection::get_Item(int32 index)
0x107a2  starg.s  1
0x107a4  ldarg.1
0x107a5  brfalse.s loc_107AF
0x107a7  ldarg.1
0x107a8  callvirt instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::ShouldPageBeSkipped()
0x107ad  brtrue.s Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel__GetNextPage
0x107af  ldarg.1
0x107b0  ret
```
