# Microsoft.Crm.Setup.Common.UI.InstallLocationPage::.ctor

- ea: `0x80a0`
- end: `0x80dc`
- name: `Microsoft.Crm.Setup.Common.UI.InstallLocationPage::.ctor`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x80e0`
- `0x8130`
- `0xc530`
- `0x10fe0`

## string_xrefs

- `0x80b2`: `InstallLocationPage.HeaderDetails`

## pseudocode

```c

```

## disassembly

```asm
0x80a0  ldarg.0
0x80a1  call     instance void Microsoft.Crm.Setup.Common.UI.SetupWizardPage::.ctor()
0x80a6  ldarg.0
0x80a7  call     instance void Microsoft.Crm.Setup.Common.UI.InstallLocationPage::InitializeComponent()
0x80ac  ldarg.0
0x80ad  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80b2  ldstr    aInstalllocatio_0// "InstallLocationPage.HeaderDetails"
0x80b7  ldc.i4.0
0x80b8  newarr   [mscorlib]System.Object
0x80bd  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x80c2  ldc.i4.1
0x80c3  newarr   [mscorlib]System.Object
0x80c8  dup
0x80c9  ldc.i4.0
0x80ca  ldarg.0
0x80cb  callvirt instance string Microsoft.Crm.Setup.Common.UI.InstallLocationPage::get_ProductTitle()
0x80d0  stelem.ref
0x80d1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80d6  call     instance void Microsoft.Crm.Setup.Common.UI.WizardPage::set_HeaderDetails(string value)
0x80db  ret
```
