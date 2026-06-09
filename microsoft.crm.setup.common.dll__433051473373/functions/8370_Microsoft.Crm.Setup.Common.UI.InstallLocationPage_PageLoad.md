# Microsoft.Crm.Setup.Common.UI.InstallLocationPage::PageLoad

- ea: `0x8370`
- end: `0x83d6`
- name: `Microsoft.Crm.Setup.Common.UI.InstallLocationPage::PageLoad`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x80f0`
- `0x8370`
- `0xb1d0`
- `0xb200`
- `0xfbc0`
- `0x10ff0`

## string_xrefs

- `0x838c`: `InstallInfo.TargetFolder`

## pseudocode

```c

```

## disassembly

```asm
0x8370  ldarg.0
0x8371  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x8376  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x837b  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x8380  stloc.0
0x8381  ldarg.0
0x8382  call     instance class Microsoft.Crm.Setup.Common.UI.Wizard Microsoft.Crm.Setup.Common.UI.WizardPage::get_Wizard()
0x8387  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Setup.Common.UI.Wizard::get_Data()
0x838c  ldstr    aInstallinfoTar// "InstallInfo.TargetFolder"
0x8391  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x8396  brfalse.s loc_83A9
0x8398  ldarg.0
0x8399  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x839e  ldloc.0
0x839f  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x83a4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0x83a9  ldarg.0
0x83aa  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x83af  ldarg.0
0x83b0  call     instance int64 Microsoft.Crm.Setup.Common.UI.InstallLocationPage::get_RequiredSpace()
0x83b5  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_SpaceRequired(int64 value)
0x83ba  ldarg.0
0x83bb  ldfld    class Microsoft.Crm.Setup.Common.UI.PathSpaceControl Microsoft.Crm.Setup.Common.UI.InstallLocationPage::pathSpace
0x83c0  ldarg.0
0x83c1  ldfld    class [System.Windows.Forms]System.Windows.Forms.TextBox Microsoft.Crm.Setup.Common.UI.InstallLocationPage::targetFolderTextBox
0x83c6  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x83cb  callvirt instance string [mscorlib]System.String::Trim()
0x83d0  callvirt instance void Microsoft.Crm.Setup.Common.UI.PathSpaceControl::set_Path(string value)
0x83d5  ret
```
