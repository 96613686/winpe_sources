# Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::buttonBrowse_Click

- ea: `0x7fd0`
- end: `0x8081`
- name: `Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::buttonBrowse_Click`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7f80`
- `0x7f90`
- `0x7fa0`
- `0x7fd0`

## pseudocode

```c

```

## disassembly

```asm
0x7fd0  ldarg.0
0x7fd1  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x7fd6  ldarg.0
0x7fd7  callvirt instance string [System.Windows.Forms]System.Windows.Forms.Control::get_Text()
0x7fdc  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Title(string)
0x7fe1  ldarg.0
0x7fe2  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x7fe7  ldc.i4.1
0x7fe8  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_RestoreDirectory(bool)
0x7fed  ldarg.0
0x7fee  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x7ff3  ldc.i4.1
0x7ff4  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_CheckPathExists(bool)
0x7ff9  ldarg.0
0x7ffa  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x7fff  ldc.i4.1
0x8000  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_CheckFileExists(bool)
0x8005  ldarg.0
0x8006  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x800b  ldarg.0
0x800c  call     instance string Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::get_FileLocation()
0x8011  ldarg.0
0x8012  call     instance string Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::get_FileName()
0x8017  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x801c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FileName(string)
0x8021  ldarg.0
0x8022  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x8027  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x802c  ldstr    a00_1// "{0}|{0}"
0x8031  ldc.i4.1
0x8032  newarr   [mscorlib]System.Object
0x8037  dup
0x8038  ldc.i4.0
0x8039  ldarg.0
0x803a  call     instance string Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::get_FileName()
0x803f  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x8044  stelem.ref
0x8045  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x804a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_Filter(string)
0x804f  ldarg.0
0x8050  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x8055  ldc.i4.1
0x8056  callvirt instance void [System.Windows.Forms]System.Windows.Forms.FileDialog::set_FilterIndex(int32)
0x805b  ldc.i4.1
0x805c  ldarg.0
0x805d  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x8062  ldarg.0
0x8063  callvirt instance valuetype [System.Windows.Forms]System.Windows.Forms.DialogResult [System.Windows.Forms]System.Windows.Forms.CommonDialog::ShowDialog(class [System.Windows.Forms]System.Windows.Forms.IWin32Window)
0x8068  bne.un.s loc_8080
0x806a  ldarg.0
0x806b  ldarg.0
0x806c  ldfld    class [System.Windows.Forms]System.Windows.Forms.OpenFileDialog Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::openFileDialog
0x8071  callvirt instance string [System.Windows.Forms]System.Windows.Forms.FileDialog::get_FileName()
0x8076  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x807b  call     instance void Microsoft.Crm.Setup.Common.UI.FileLocatorDialog::set_FileLocation(string value)
0x8080  ret
```
