# Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::ShowDialog_0

- ea: `0x5330`
- end: `0x549d`
- name: `Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::ShowDialog_0`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5320`

## callees

- `0xff0`
- `0x52a0`
- `0x52c0`
- `0x52e0`
- `0x5300`
- `0x5310`
- `0x5330`
- `0x5590`
- `0x55c0`

## pseudocode

```c

```

## disassembly

```asm
0x5330  ldarg.1
0x5331  brtrue.s loc_533A
0x5333  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x5338  br.s     loc_5340
0x533a  ldarg.1
0x533b  callvirt instance native int [System.Windows.Forms]System.Windows.Forms.IWin32Window::get_Handle()
0x5340  stloc.0
0x5341  ldc.i4   0x2210
0x5346  newarr   [mscorlib]System.Char
0x534b  stloc.1
0x534c  ldarg.0
0x534d  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_Path()
0x5352  brfalse.s loc_537A
0x5354  ldarg.0
0x5355  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_Path()
0x535a  callvirt instance char[] [mscorlib]System.String::ToCharArray()
0x535f  ldloc.1
0x5360  ldarg.0
0x5361  ldfld    string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::path
0x5366  callvirt instance int32 [mscorlib]System.String::get_Length()
0x536b  ldc.i4   0x2210
0x5370  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x5375  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x537a  ldloc.1
0x537b  newobj   instance void [mscorlib]System.String::.ctor(char[])
0x5380  stloc.2
0x5381  ldloca.s 3
0x5383  initobj  Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO
0x5389  ldloca.s 3
0x538b  ldloc.3
0x538c  call     T0x2B000004
0x5391  stfld    int32 Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::cbStruct
0x5396  ldloca.s 3
0x5398  ldloc.0
0x5399  stfld    native int Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::hwndOwner
0x539e  ldloca.s 3
0x53a0  ldarg.0
0x53a1  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_Description()
0x53a6  stfld    string Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pszTitle
0x53ab  ldloca.s 3
0x53ad  ldarg.0
0x53ae  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_Text()
0x53b3  brtrue.s loc_53BC
0x53b5  ldsfld   string [mscorlib]System.String::Empty
0x53ba  br.s     loc_53C2
0x53bc  ldarg.0
0x53bd  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_Text()
0x53c2  stfld    string Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pszCaption
0x53c7  ldloca.s 3
0x53c9  ldarg.0
0x53ca  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_RootPath()
0x53cf  brfalse.s loc_53DF
0x53d1  ldarg.0
0x53d2  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_RootPath()
0x53d7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x53dc  ldc.i4.0
0x53dd  bgt.s    loc_53E2
0x53df  ldnull
0x53e0  br.s     loc_53E8
0x53e2  ldarg.0
0x53e3  call     instance string Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::get_RootPath()
0x53e8  stfld    string Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pszRoot
0x53ed  ldloca.s 3
0x53ef  ldloc.2
0x53f0  stfld    string Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pszPath
0x53f5  ldloca.s 3
0x53f7  ldc.i4   0x2210
0x53fc  stfld    int32 Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::cchPath
0x5401  ldloca.s 3
0x5403  ldc.i4   0x40000
0x5408  stfld    int32 Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::dwFlags
0x540d  ldloca.s 3
0x540f  ldarg.0
0x5410  ldftn    instance int32 Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::OnBFFCallback(native int hwnd, int32 uMsg, native int lParam, native int lpData)
0x5416  newobj   instance void Microsoft.Crm.Setup.Common.UI.BFFCallBack::.ctor(object object, native int method)
0x541b  stfld    class Microsoft.Crm.Setup.Common.UI.BFFCallBack Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pfnCallback
0x5420  ldloca.s 3
0x5422  ldsfld   string [mscorlib]System.String::Empty
0x5427  stfld    string Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pszObjectClass
0x542c  ldloca.s 3
0x542e  ldc.i4.0
0x542f  stfld    int32 Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::cchObjectClass
0x5434  ldloca.s 3
0x5436  call     int32 Microsoft.Crm.Setup.Common.UI.DSNativeMethods::DsBrowseForContainer(valuetype Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO& pInfo)
0x543b  stloc.s  4
0x543d  ldarg.0
0x543e  ldsfld   string [mscorlib]System.String::Empty
0x5443  call     instance void Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::set_Path(string value)
0x5448  ldc.i4.2
0x5449  stloc.s  5
0x544b  ldloc.s  4
0x544d  ldc.i4.m1
0x544e  sub
0x544f  switch   loc_5484, loc_549A, loc_5466, loc_547F
0x5464  br.s     loc_549A
0x5466  ldc.i4.1
0x5467  stloc.s  5
0x5469  ldloc.3
0x546a  ldfld    string Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pszPath
0x546f  brfalse.s loc_549A
0x5471  ldarg.0
0x5472  ldloc.3
0x5473  ldfld    string Microsoft.Crm.Setup.Common.UI.DSBROWSEINFO::pszPath
0x5478  call     instance void Microsoft.Crm.Setup.Common.UI.DSBrowserDialog::set_Path(string value)
0x547d  br.s     loc_549A
0x547f  ldc.i4.2
0x5480  stloc.s  5
0x5482  br.s     loc_549A
0x5484  ldstr    aErrorDsbrowser// "Error.DsBrowserDialog.CannotBrowse"
0x5489  ldc.i4.0
0x548a  newarr   [mscorlib]System.Object
0x548f  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x5494  call     valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InputResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MessageReport::RequestInput(object)
0x5499  pop
0x549a  ldloc.s  5
0x549c  ret
```
