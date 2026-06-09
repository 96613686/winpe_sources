# Microsoft.Crm.Setup.Common.AdminFolderValidator::InternalCheck

- ea: `0x32c0`
- end: `0x35cd`
- name: `Microsoft.Crm.Setup.Common.AdminFolderValidator::InternalCheck`
- size: `781`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x32c0`

## string_xrefs

- `0x3308`: `AdminFolderValidator.Failure.InvalidPath`
- `0x3509`: `AdminFolderValidator.Failure.InvalidPath`
- `0x33a0`: `AdminFolderValidator.Failure.NotAbsolutePath`
- `0x34e1`: `AdminFolderValidator.Failure.UnauthorizedAccess`
- `0x35a4`: `AdminFolderValidator.Failure.NotEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x32c0  ldnull
0x32c1  stloc.0
0x32c2  ldc.i4.1
0x32c3  stloc.1
0x32c4  ldarg.0
0x32c5  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x32ca  brtrue.s loc_32E4
0x32cc  ldarg.1
0x32cd  brfalse.s loc_32E4
0x32cf  ldc.i4.0
0x32d0  stloc.1
0x32d1  ldarg.1
0x32d2  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x32d7  stloc.0
0x32d8  ldarg.0
0x32d9  ldloc.0
0x32da  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_AdminFolder()
0x32df  stfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x32e4  nop
0x32e5  ldarg.0
0x32e6  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x32eb  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x32f0  pop
0x32f1  leave.s  loc_3343
0x32f3  stloc.s  5
0x32f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x32fa  ldstr    a01// "{0} {1}"
0x32ff  ldc.i4.2
0x3300  newarr   [mscorlib]System.Object
0x3305  dup
0x3306  ldc.i4.0
0x3307  ldarg.0
0x3308  ldstr    aAdminfolderval// "AdminFolderValidator.Failure.InvalidPat"...
0x330d  ldc.i4.1
0x330e  newarr   [mscorlib]System.Object
0x3313  dup
0x3314  ldc.i4.0
0x3315  ldarg.0
0x3316  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x331b  stelem.ref
0x331c  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3321  stelem.ref
0x3322  dup
0x3323  ldc.i4.1
0x3324  ldarg.0
0x3325  ldloc.s  5
0x3327  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x332c  stelem.ref
0x332d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3332  stloc.s  6
0x3334  ldc.i4.2
0x3335  ldloc.s  6
0x3337  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x333c  stloc.s  7
0x333e  leave    loc_35CA
0x3343  ldarg.0
0x3344  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x3349  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x334e  brfalse.s loc_339E
0x3350  ldc.i4.3
0x3351  ldarg.0
0x3352  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x3357  callvirt instance int32 [mscorlib]System.String::get_Length()
0x335c  bgt.s    loc_339E
0x335e  ldc.i4.s 0x5C
0x3360  ldarg.0
0x3361  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x3366  ldc.i4.0
0x3367  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x336c  bne.un.s loc_337E
0x336e  ldc.i4.s 0x5C
0x3370  ldarg.0
0x3371  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x3376  ldc.i4.1
0x3377  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x337c  bne.un.s loc_339E
0x337e  ldc.i4.s 0x3A
0x3380  ldarg.0
0x3381  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x3386  ldc.i4.1
0x3387  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x338c  bne.un.s loc_33BF
0x338e  ldc.i4.s 0x5C
0x3390  ldarg.0
0x3391  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x3396  ldc.i4.2
0x3397  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x339c  beq.s    loc_33BF
0x339e  ldc.i4.2
0x339f  ldarg.0
0x33a0  ldstr    aAdminfolderval_0// "AdminFolderValidator.Failure.NotAbsolut"...
0x33a5  ldc.i4.1
0x33a6  newarr   [mscorlib]System.Object
0x33ab  dup
0x33ac  ldc.i4.0
0x33ad  ldarg.0
0x33ae  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x33b3  stelem.ref
0x33b4  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x33b9  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x33be  ret
0x33bf  ldarg.0
0x33c0  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x33c5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x33ca  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x33cf  callvirt instance string [mscorlib]System.String::Trim()
0x33d4  ldc.i4.s 0x26
0x33d6  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x33db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x33e0  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x33e5  stloc.2
0x33e6  ldloc.2
0x33e7  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x33ec  stloc.3
0x33ed  ldsfld   string [mscorlib]System.String::Empty
0x33f2  stloc.s  4
0x33f4  ldloc.3
0x33f5  brfalse.s loc_33FC
0x33f7  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Elevated::SetSystemContext()
0x33fc  ldarg.0
0x33fd  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x3402  stloc.s  4
0x3404  br.s     loc_340F
0x3406  ldloc.s  4
0x3408  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x340d  stloc.s  4
0x340f  ldloc.s  4
0x3411  brfalse.s loc_341C
0x3413  ldloc.s  4
0x3415  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x341a  brfalse.s loc_3406
0x341c  ldloc.s  4
0x341e  brtrue.s loc_3426
0x3420  newobj   instance void [mscorlib]System.IO.DirectoryNotFoundException::.ctor()
0x3425  throw
0x3426  ldloc.s  4
0x3428  ldstr    aTmpdir0// "tmpdir0"
0x342d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3432  stloc.s  8
0x3434  ldc.i4.1
0x3435  stloc.s  0xA
0x3437  br.s     loc_3467
0x3439  ldloc.s  4
0x343b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3440  ldstr    aTmpdir0_0// "tmpdir{0}"
0x3445  ldc.i4.1
0x3446  newarr   [mscorlib]System.Object
0x344b  dup
0x344c  ldc.i4.0
0x344d  ldloc.s  0xA
0x344f  box      [mscorlib]System.Int32
0x3454  stelem.ref
0x3455  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x345a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x345f  stloc.s  8
0x3461  ldloc.s  0xA
0x3463  ldc.i4.1
0x3464  add
0x3465  stloc.s  0xA
0x3467  ldloc.s  8
0x3469  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x346e  brtrue.s loc_3439
0x3470  ldloc.s  4
0x3472  ldstr    aTmpfile0// "tmpfile0"
0x3477  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x347c  stloc.s  9
0x347e  ldc.i4.1
0x347f  stloc.s  0xB
0x3481  br.s     loc_34B1
0x3483  ldloc.s  4
0x3485  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x348a  ldstr    aTmpfile0_0// "tmpfile{0}"
0x348f  ldc.i4.1
0x3490  newarr   [mscorlib]System.Object
0x3495  dup
0x3496  ldc.i4.0
0x3497  ldloc.s  0xB
0x3499  box      [mscorlib]System.Int32
0x349e  stelem.ref
0x349f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x34a4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x34a9  stloc.s  9
0x34ab  ldloc.s  0xB
0x34ad  ldc.i4.1
0x34ae  add
0x34af  stloc.s  0xB
0x34b1  ldloc.s  9
0x34b3  call     bool [mscorlib]System.IO.File::Exists(string)
0x34b8  brtrue.s loc_3483
0x34ba  ldloc.s  8
0x34bc  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x34c1  pop
0x34c2  ldloc.s  8
0x34c4  call     void [mscorlib]System.IO.Directory::Delete(string)
0x34c9  ldloc.s  9
0x34cb  call     class [mscorlib]System.IO.StreamWriter [mscorlib]System.IO.File::CreateText(string)
0x34d0  callvirt instance void [mscorlib]System.IO.TextWriter::Close()
0x34d5  ldloc.s  9
0x34d7  call     void [mscorlib]System.IO.File::Delete(string)
0x34dc  leave.s  loc_3537
0x34de  pop
0x34df  ldc.i4.2
0x34e0  ldarg.0
0x34e1  ldstr    aAdminfolderval_1// "AdminFolderValidator.Failure.Unauthoriz"...
0x34e6  ldc.i4.1
0x34e7  newarr   [mscorlib]System.Object
0x34ec  dup
0x34ed  ldc.i4.0
0x34ee  ldarg.0
0x34ef  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x34f4  stelem.ref
0x34f5  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x34fa  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x34ff  stloc.s  7
0x3501  leave    loc_35CA
0x3506  pop
0x3507  ldc.i4.2
0x3508  ldarg.0
0x3509  ldstr    aAdminfolderval// "AdminFolderValidator.Failure.InvalidPat"...
0x350e  ldc.i4.1
0x350f  newarr   [mscorlib]System.Object
0x3514  dup
0x3515  ldc.i4.0
0x3516  ldarg.0
0x3517  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x351c  stelem.ref
0x351d  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3522  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3527  stloc.s  7
0x3529  leave    loc_35CA
0x352e  ldloc.3
0x352f  brfalse.s loc_3536
0x3531  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Elevated::SetUserContext()
0x3536  endfinally
0x3537  ldc.i4.m1
0x3538  ldarg.0
0x3539  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x353e  ldc.i4.2
0x353f  newarr   [mscorlib]System.Char
0x3544  dup
0x3545  ldc.i4.0
0x3546  ldc.i4.s 0x3B
0x3548  stelem.i2
0x3549  dup
0x354a  ldc.i4.1
0x354b  ldc.i4.s 0x2F
0x354d  stelem.i2
0x354e  callvirt instance int32 [mscorlib]System.String::IndexOfAny(char[])
0x3553  beq.s    loc_3576
0x3555  ldc.i4.2
0x3556  ldarg.0
0x3557  ldstr    aAdminfolderval_2// "AdminFolderValidator.Failure.Unsupporte"...
0x355c  ldc.i4.1
0x355d  newarr   [mscorlib]System.Object
0x3562  dup
0x3563  ldc.i4.0
0x3564  ldarg.0
0x3565  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x356a  stelem.ref
0x356b  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3570  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3575  ret
0x3576  ldloc.1
0x3577  brtrue.s loc_35C3
0x3579  ldarg.0
0x357a  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x357f  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x3584  brfalse.s loc_35C3
0x3586  ldarg.0
0x3587  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x358c  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x3591  ldlen
0x3592  brtrue.s loc_35A2
0x3594  ldarg.0
0x3595  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x359a  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x359f  ldlen
0x35a0  brfalse.s loc_35C3
0x35a2  ldc.i4.1
0x35a3  ldarg.0
0x35a4  ldstr    aAdminfolderval_3// "AdminFolderValidator.Failure.NotEmpty"
0x35a9  ldc.i4.1
0x35aa  newarr   [mscorlib]System.Object
0x35af  dup
0x35b0  ldc.i4.0
0x35b1  ldarg.0
0x35b2  ldfld    string Microsoft.Crm.Setup.Common.AdminFolderValidator::adminFolder
0x35b7  stelem.ref
0x35b8  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x35bd  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x35c2  ret
0x35c3  ldc.i4.0
0x35c4  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x35c9  ret
0x35ca  ldloc.s  7
0x35cc  ret
```
