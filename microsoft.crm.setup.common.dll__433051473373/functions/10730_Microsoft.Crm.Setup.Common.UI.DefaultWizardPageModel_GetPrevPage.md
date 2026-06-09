# Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::GetPrevPage

- ea: `0x10730`
- end: `0x1076f`
- name: `Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::GetPrevPage`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10730`

## callees

- `0x106a0`
- `0x10730`
- `0x108b0`
- `0x109b0`
- `0x110e0`

## pseudocode

```c

```

## disassembly

```asm
0x10730  ldarg.0
0x10731  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_Pages()
0x10736  ldarg.1
0x10737  callvirt instance int32 Microsoft.Crm.Setup.Common.UI.WizardPageCollection::IndexOf(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x1073c  stloc.0
0x1073d  ldloc.0
0x1073e  ldc.i4.0
0x1073f  ble.s    loc_1074F
0x10741  ldloc.0
0x10742  ldarg.0
0x10743  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_Pages()
0x10748  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1074d  blt.s    loc_10752
0x1074f  ldnull
0x10750  br.s     loc_10760
0x10752  ldarg.0
0x10753  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_Pages()
0x10758  ldloc.0
0x10759  ldc.i4.1
0x1075a  sub
0x1075b  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.WizardPageCollection::get_Item(int32 index)
0x10760  starg.s  1
0x10762  ldarg.1
0x10763  brfalse.s loc_1076D
0x10765  ldarg.1
0x10766  callvirt instance bool Microsoft.Crm.Setup.Common.UI.WizardPage::ShouldPageBeSkipped()
0x1076b  brtrue.s Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel__GetPrevPage
0x1076d  ldarg.1
0x1076e  ret
```
