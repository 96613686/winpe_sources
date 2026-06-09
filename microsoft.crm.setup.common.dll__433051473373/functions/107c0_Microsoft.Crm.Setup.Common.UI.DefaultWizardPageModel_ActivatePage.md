# Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::ActivatePage

- ea: `0x107c0`
- end: `0x10839`
- name: `Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::ActivatePage`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x106a0`
- `0x106b0`
- `0x106c0`
- `0x107c0`
- `0x10840`
- `0x10890`
- `0x11000`

## pseudocode

```c

```

## disassembly

```asm
0x107c0  ldarg.1
0x107c1  brtrue.s loc_107D4
0x107c3  ldstr    aActivatepageNu// "ActivatePage(null)"
0x107c8  ldc.i4.0
0x107c9  newarr   [mscorlib]System.Object
0x107ce  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x107d3  ret
0x107d4  ldarg.1
0x107d5  ldarg.0
0x107d6  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_CurrentPage()
0x107db  bne.un.s loc_107EE
0x107dd  ldstr    aActivatepageCu// "ActivatePage(current)"
0x107e2  ldc.i4.0
0x107e3  newarr   [mscorlib]System.Object
0x107e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x107ed  ret
0x107ee  ldstr    aActivatepage0// "ActivatePage({0})"
0x107f3  ldc.i4.1
0x107f4  newarr   [mscorlib]System.Object
0x107f9  dup
0x107fa  ldc.i4.0
0x107fb  ldarg.1
0x107fc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10801  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10806  stelem.ref
0x10807  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1080c  ldarg.1
0x1080d  ldarg.0
0x1080e  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPageCollection Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_Pages()
0x10813  callvirt instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPageCollection::get_Wizard()
0x10818  callvirt instance void Microsoft.Crm.Setup.Common.UI.WizardPage::SetWizard(class Microsoft.Crm.Setup.Common.UI.Wizard wizard)
0x1081d  ldarg.0
0x1081e  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_CurrentPage()
0x10823  stloc.0
0x10824  ldarg.0
0x10825  ldarg.1
0x10826  call     instance void Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::SetCurrentPage(class Microsoft.Crm.Setup.Common.UI.WizardPage page)
0x1082b  ldarg.0
0x1082c  ldloc.0
0x1082d  ldarg.0
0x1082e  call     instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::get_CurrentPage()
0x10833  call     instance void Microsoft.Crm.Setup.Common.UI.DefaultWizardPageModel::RaisePageChanged(class Microsoft.Crm.Setup.Common.UI.WizardPage lastPage, class Microsoft.Crm.Setup.Common.UI.WizardPage currentPage)
0x10838  ret
```
