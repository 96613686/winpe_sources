# Microsoft.Crm.Setup.Common.UI.PathSpaceControl::RecalcAvailableSpace

- ea: `0xb210`
- end: `0xb41f`
- name: `Microsoft.Crm.Setup.Common.UI.PathSpaceControl::RecalcAvailableSpace`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xb1d0`

## callees

- `0xff0`
- `0x2bd0`
- `0x2dc0`
- `0x3290`
- `0xb210`

## string_xrefs

- `0xb39c`: `InstallPath.Exception`

## pseudocode

```c

```

## disassembly

```asm
0xb210  ldc.i4.0
0xb211  stloc.1
0xb212  ldarg.0
0xb213  ldfld    bool Microsoft.Crm.Setup.Common.UI.PathSpaceControl::adminInstall
0xb218  brtrue.s loc_B231
0xb21a  ldc.i4.2
0xb21b  ldarg.1
0xb21c  newobj   instance void Microsoft.Crm.Setup.Common.TargetFolderValidator::.ctor(string targetFolder)
0xb221  ldnull
0xb222  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo Microsoft.Crm.Setup.Common.Validator::Check(class [mscorlib]System.Collections.IDictionary parameters)
0xb227  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::get_Result()
0xb22c  ceq
0xb22e  stloc.1
0xb22f  br.s     loc_B246
0xb231  ldc.i4.2
0xb232  ldarg.1
0xb233  newobj   instance void Microsoft.Crm.Setup.Common.AdminFolderValidator::.ctor(string adminFolder)
0xb238  ldnull
0xb239  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo Microsoft.Crm.Setup.Common.Validator::Check(class [mscorlib]System.Collections.IDictionary parameters)
0xb23e  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::get_Result()
0xb243  ceq
0xb245  stloc.1
0xb246  ldloc.1
0xb247  brfalse.s loc_B292
0xb249  ldarg.0
0xb24a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb24f  ldstr    asc_18D5A// ""
0xb254  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb259  ldarg.0
0xb25a  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb25f  ldstr    asc_18D5A// ""
0xb264  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb269  ldarg.0
0xb26a  ldc.i4.m1
0xb26b  conv.i8
0xb26c  stfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceAvailable
0xb271  ldarg.0
0xb272  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb277  ldstr    asc_18D5A// ""
0xb27c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb281  ldarg.0
0xb282  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb287  ldstr    asc_18D5A// ""
0xb28c  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb291  ret
0xb292  ldc.i4.m1
0xb293  conv.i8
0xb294  ldarg.0
0xb295  ldfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceRequired
0xb29a  bne.un.s loc_B2C1
0xb29c  ldarg.0
0xb29d  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb2a2  ldstr    asc_18D5A// ""
0xb2a7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb2ac  ldarg.0
0xb2ad  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb2b2  ldstr    asc_18D5A// ""
0xb2b7  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb2bc  br       loc_B344
0xb2c1  ldarg.0
0xb2c2  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceRequired
0xb2c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb2cc  ldarg.0
0xb2cd  ldfld    string Microsoft.Crm.Setup.Common.UI.PathSpaceControl::formatLabelSpaceRequired
0xb2d2  ldc.i4.1
0xb2d3  newarr   [mscorlib]System.Object
0xb2d8  dup
0xb2d9  ldc.i4.0
0xb2da  ldarg.1
0xb2db  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0xb2e0  stelem.ref
0xb2e1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb2e6  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb2eb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb2f0  ldstr    a0N// "{0:N}"
0xb2f5  ldc.i4.1
0xb2f6  newarr   [mscorlib]System.Object
0xb2fb  dup
0xb2fc  ldc.i4.0
0xb2fd  ldarg.0
0xb2fe  ldfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceRequired
0xb303  box      [mscorlib]System.Int64
0xb308  stelem.ref
0xb309  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb30e  stloc.0
0xb30f  ldloc.0
0xb310  ldc.i4.0
0xb311  ldloc.0
0xb312  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb317  ldc.i4.3
0xb318  sub
0xb319  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xb31e  stloc.0
0xb31f  ldarg.0
0xb320  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceRequired
0xb325  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb32a  ldarg.0
0xb32b  ldfld    string Microsoft.Crm.Setup.Common.UI.PathSpaceControl::formatTextSpaceRequired
0xb330  ldc.i4.1
0xb331  newarr   [mscorlib]System.Object
0xb336  dup
0xb337  ldc.i4.0
0xb338  ldloc.0
0xb339  stelem.ref
0xb33a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb33f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb344  ldarg.0
0xb345  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::labelSpaceAvailable
0xb34a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb34f  ldarg.0
0xb350  ldfld    string Microsoft.Crm.Setup.Common.UI.PathSpaceControl::formatLabelSpaceAvailable
0xb355  ldc.i4.1
0xb356  newarr   [mscorlib]System.Object
0xb35b  dup
0xb35c  ldc.i4.0
0xb35d  ldarg.1
0xb35e  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0xb363  stelem.ref
0xb364  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb369  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb36e  ldc.i4.0
0xb36f  conv.i8
0xb370  stloc.2
0xb371  ldc.i4.0
0xb372  conv.i8
0xb373  stloc.3
0xb374  ldarg.0
0xb375  ldc.i4.m1
0xb376  conv.i8
0xb377  stfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceAvailable
0xb37c  ldarg.1
0xb37d  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0xb382  ldarg.0
0xb383  ldflda   int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceAvailable
0xb388  ldloca.s 2
0xb38a  ldloca.s 3
0xb38c  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::GetDiskFreeSpace(string, int64&, int64&, int64&)
0xb391  pop
0xb392  ldc.i4.m1
0xb393  conv.i8
0xb394  ldarg.0
0xb395  ldfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceAvailable
0xb39a  bne.un.s loc_B3B2
0xb39c  ldstr    aInstallpathExc// "InstallPath.Exception"
0xb3a1  ldc.i4.0
0xb3a2  newarr   [mscorlib]System.Object
0xb3a7  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0xb3ac  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string)
0xb3b1  throw
0xb3b2  ldarg.0
0xb3b3  ldarg.0
0xb3b4  ldfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceAvailable
0xb3b9  ldc.i4   0x100000
0xb3be  conv.i8
0xb3bf  div
0xb3c0  stfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceAvailable
0xb3c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb3ca  ldstr    a0N// "{0:N}"
0xb3cf  ldc.i4.1
0xb3d0  newarr   [mscorlib]System.Object
0xb3d5  dup
0xb3d6  ldc.i4.0
0xb3d7  ldarg.0
0xb3d8  ldfld    int64 Microsoft.Crm.Setup.Common.UI.PathSpaceControl::spaceAvailable
0xb3dd  box      [mscorlib]System.Int64
0xb3e2  stelem.ref
0xb3e3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb3e8  stloc.0
0xb3e9  ldloc.0
0xb3ea  ldc.i4.0
0xb3eb  ldloc.0
0xb3ec  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb3f1  ldc.i4.3
0xb3f2  sub
0xb3f3  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xb3f8  stloc.0
0xb3f9  ldarg.0
0xb3fa  ldfld    class [System.Windows.Forms]System.Windows.Forms.Label Microsoft.Crm.Setup.Common.UI.PathSpaceControl::textSpaceAvailable
0xb3ff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0xb404  ldarg.0
0xb405  ldfld    string Microsoft.Crm.Setup.Common.UI.PathSpaceControl::formatTextSpaceAvailable
0xb40a  ldc.i4.1
0xb40b  newarr   [mscorlib]System.Object
0xb410  dup
0xb411  ldc.i4.0
0xb412  ldloc.0
0xb413  stelem.ref
0xb414  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb419  callvirt instance void [System.Windows.Forms]System.Windows.Forms.Control::set_Text(string)
0xb41e  ret
```
