# Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InstallLocationPage_PageActivated

- ea: `0x83e0`
- end: `0x84a5`
- name: `Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InstallLocationPage_PageActivated`
- size: `197`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x80f0`
- `0x83e0`
- `0xb1d0`
- `0xb200`
- `0xfbc0`
- `0xfbe0`
- `0xfca0`
- `0xfcb0`
- `0xfcd0`
- `0x105d0`
- `0x10ff0`

## string_xrefs

- `0x83fc`: `InstallInfo.TargetFolder`

## pseudocode

```c

```

## disassembly

```asm
0x83e0  ldarg.0
0x83e1  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x83e6  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x83eb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x83f0  stloc.0
0x83f1  ldarg.0
0x83f2  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x83f7  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x83fc  ldstr    aInstallinfoTar// "InstallInfo.TargetFolder"
0x8401  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8406  brfalse.s loc_8419
0x8408  ldarg.0
0x8409  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x840e  ldloc.0
0x840f  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x8414  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x8419  ldarg.0
0x841a  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x841f  ldarg.0
0x8420  call     instance int64 Microsoft.Crm.Setup.Common.UI.InstallLocationPage::get_RequiredSpace()
0x8425  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_SpaceRequired(int64 value)
0x842a  ldarg.0
0x842b  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x8430  ldarg.0
0x8431  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x8436  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x843b  callvirt instance string [mscorlib]System.String::Trim()
0x8440  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_Path(string value)
0x8445  ldarg.0
0x8446  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x844b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_BackButton()
0x8450  ldarg.0
0x8451  ldarg.0
0x8452  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x8457  callvirt instance class Microsoft.Crm.Setup.Common.UI.IWizardPageModel Microsoft.Crm.Setup.Common.UI.Wizard::get_Model()
0x845c  callvirt instance class Microsoft.Crm.Setup.Common.UI.WizardPage Microsoft.Crm.Setup.Common.UI.IWizardPageModel::GetFirstPage()
0x8461  ceq
0x8463  ldc.i4.0
0x8464  ceq
0x8466  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x846b  ldarg.0
0x846c  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x8471  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_NextButton()
0x8476  ldarg.0
0x8477  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x847c  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x8481  callvirt instance string [mscorlib]System.String::Trim()
0x8486  callvirt instance int32 [mscorlib]System.String::get_Length()
0x848b  ldc.i4.0
0x848c  cgt
0x848e  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x8493  ldarg.0
0x8494  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x8499  callvirt instance class [System.Windows.Forms]System.Windows.Forms.Button Microsoft.Crm.Setup.Common.UI.Wizard::get_CancelButton()
0x849e  ldc.i4.1
0x849f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Enabled(bool)
0x84a4  ret
```
