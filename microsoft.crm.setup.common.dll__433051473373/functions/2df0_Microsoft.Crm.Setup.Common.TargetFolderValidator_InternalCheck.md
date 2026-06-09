# Microsoft.Crm.Setup.Common.TargetFolderValidator::InternalCheck

- ea: `0x2df0`
- end: `0x327a`
- name: `Microsoft.Crm.Setup.Common.TargetFolderValidator::InternalCheck`
- size: `1162`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x2df0`

## string_xrefs

- `0x2e33`: `TargetFolderValidator.Failure.InvalidPath`
- `0x2f30`: `TargetFolderValidator.Failure.NotAbsolutePath`
- `0x2f5e`: `TargetFolderValidator.Failure.NetworkPath`
- `0x2fd8`: `InstallInfo.ExistingFolder`
- `0x300c`: `TargetFolderValidator.Failure.NonexistingPath`
- `0x302e`: `InstallInfo.AdminTargetFolder`
- `0x3140`: `TargetFolderValidator.Failure.UnauthorizedAccess`
- `0x3168`: `TargetFolderValidator.Failure.UnauthorizedAccess`
- `0x31ea`: `TargetFolderValidator.Failure.PathTooLong`
- `0x3251`: `TargetFolderValidator.Failure.NotEmpty`

## pseudocode

```c

```

## disassembly

```asm
0x2df0  ldnull
0x2df1  stloc.0
0x2df2  ldarg.0
0x2df3  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2df8  brtrue.s loc_2E10
0x2dfa  ldarg.1
0x2dfb  brfalse.s loc_2E10
0x2dfd  ldarg.1
0x2dfe  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x2e03  stloc.0
0x2e04  ldarg.0
0x2e05  ldloc.0
0x2e06  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x2e0b  stfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2e10  nop
0x2e11  ldarg.0
0x2e12  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2e17  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x2e1c  pop
0x2e1d  leave.s  loc_2E6D
0x2e1f  stloc.3
0x2e20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x2e25  ldstr    a01// "{0} {1}"
0x2e2a  ldc.i4.2
0x2e2b  newarr   [mscorlib]System.Object
0x2e30  dup
0x2e31  ldc.i4.0
0x2e32  ldarg.0
0x2e33  ldstr    aTargetfolderva// "TargetFolderValidator.Failure.InvalidPa"...
0x2e38  ldc.i4.1
0x2e39  newarr   [mscorlib]System.Object
0x2e3e  dup
0x2e3f  ldc.i4.0
0x2e40  ldarg.0
0x2e41  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2e46  stelem.ref
0x2e47  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x2e4c  stelem.ref
0x2e4d  dup
0x2e4e  ldc.i4.1
0x2e4f  ldarg.0
0x2e50  ldloc.3
0x2e51  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x2e56  stelem.ref
0x2e57  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e5c  stloc.s  4
0x2e5e  ldc.i4.2
0x2e5f  ldloc.s  4
0x2e61  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x2e66  stloc.s  5
0x2e68  leave    loc_3277
0x2e6d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e72  ldstr    a00// "{0}..{0}"
0x2e77  ldc.i4.1
0x2e78  newarr   [mscorlib]System.Object
0x2e7d  dup
0x2e7e  ldc.i4.0
0x2e7f  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x2e84  box      [mscorlib]System.Char
0x2e89  stelem.ref
0x2e8a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2e8f  stloc.1
0x2e90  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2e95  ldstr    a00_0// "{0}.{0}"
0x2e9a  ldc.i4.1
0x2e9b  newarr   [mscorlib]System.Object
0x2ea0  dup
0x2ea1  ldc.i4.0
0x2ea2  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x2ea7  box      [mscorlib]System.Char
0x2eac  stelem.ref
0x2ead  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2eb2  stloc.2
0x2eb3  ldarg.0
0x2eb4  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2eb9  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x2ebe  brfalse.s loc_2F2E
0x2ec0  ldc.i4.3
0x2ec1  ldarg.0
0x2ec2  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2ec7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2ecc  bgt.s    loc_2F2E
0x2ece  ldc.i4.s 0x5C
0x2ed0  ldarg.0
0x2ed1  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2ed6  ldc.i4.0
0x2ed7  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2edc  bne.un.s loc_2EEE
0x2ede  ldc.i4.s 0x5C
0x2ee0  ldarg.0
0x2ee1  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2ee6  ldc.i4.1
0x2ee7  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2eec  bne.un.s loc_2F2E
0x2eee  ldc.i4.s 0x3A
0x2ef0  ldarg.0
0x2ef1  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2ef6  ldc.i4.1
0x2ef7  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2efc  bne.un.s loc_2F0E
0x2efe  ldc.i4.s 0x5C
0x2f00  ldarg.0
0x2f01  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2f06  ldc.i4.2
0x2f07  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2f0c  bne.un.s loc_2F2E
0x2f0e  ldarg.0
0x2f0f  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2f14  ldloc.1
0x2f15  ldc.i4.5
0x2f16  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2f1b  ldc.i4.m1
0x2f1c  bgt.s    loc_2F2E
0x2f1e  ldarg.0
0x2f1f  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2f24  ldloc.2
0x2f25  ldc.i4.5
0x2f26  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2f2b  ldc.i4.m1
0x2f2c  ble.s    loc_2F4F
0x2f2e  ldc.i4.2
0x2f2f  ldarg.0
0x2f30  ldstr    aTargetfolderva_0// "TargetFolderValidator.Failure.NotAbsolu"...
0x2f35  ldc.i4.1
0x2f36  newarr   [mscorlib]System.Object
0x2f3b  dup
0x2f3c  ldc.i4.0
0x2f3d  ldarg.0
0x2f3e  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2f43  stelem.ref
0x2f44  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x2f49  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x2f4e  ret
0x2f4f  ldarg.0
0x2f50  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2f55  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::PathIsNetworkPath(string)
0x2f5a  brfalse.s loc_2F7D
0x2f5c  ldc.i4.2
0x2f5d  ldarg.0
0x2f5e  ldstr    aTargetfolderva_1// "TargetFolderValidator.Failure.NetworkPa"...
0x2f63  ldc.i4.1
0x2f64  newarr   [mscorlib]System.Object
0x2f69  dup
0x2f6a  ldc.i4.0
0x2f6b  ldarg.0
0x2f6c  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2f71  stelem.ref
0x2f72  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x2f77  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x2f7c  ret
0x2f7d  ldc.i4.3
0x2f7e  ldarg.0
0x2f7f  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2f84  call     string [mscorlib]System.IO.Path::GetPathRoot(string)
0x2f89  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::GetDriveType(string)
0x2f8e  beq.s    loc_2FB1
0x2f90  ldc.i4.2
0x2f91  ldarg.0
0x2f92  ldstr    aTargetfolderva_2// "TargetFolderValidator.Failure.NotFixedD"...
0x2f97  ldc.i4.1
0x2f98  newarr   [mscorlib]System.Object
0x2f9d  dup
0x2f9e  ldc.i4.0
0x2f9f  ldarg.0
0x2fa0  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2fa5  stelem.ref
0x2fa6  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x2fab  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x2fb0  ret
0x2fb1  ldloc.0
0x2fb2  brfalse.s loc_3027
0x2fb4  ldc.i4.1
0x2fb5  ldloc.0
0x2fb6  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x2fbb  beq.s    loc_3027
0x2fbd  ldc.i4.3
0x2fbe  ldloc.0
0x2fbf  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x2fc4  beq.s    loc_3027
0x2fc6  ldarg.0
0x2fc7  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x2fcc  stloc.s  6
0x2fce  ldc.i4.2
0x2fcf  ldloc.0
0x2fd0  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallType [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_InstallType()
0x2fd5  bne.un.s loc_3001
0x2fd7  ldarg.1
0x2fd8  ldstr    aInstallinfoExi// "InstallInfo.ExistingFolder"
0x2fdd  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x2fe2  brfalse.s loc_3001
0x2fe4  ldloc.0
0x2fe5  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_ExistingFolder()
0x2fea  brfalse.s loc_3001
0x2fec  ldloc.0
0x2fed  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_ExistingFolder()
0x2ff2  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2ff7  brfalse.s loc_3001
0x2ff9  ldloc.0
0x2ffa  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_ExistingFolder()
0x2fff  stloc.s  6
0x3001  ldloc.s  6
0x3003  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x3008  brtrue.s loc_3027
0x300a  ldc.i4.2
0x300b  ldarg.0
0x300c  ldstr    aTargetfolderva_3// "TargetFolderValidator.Failure.Nonexisti"...
0x3011  ldc.i4.1
0x3012  newarr   [mscorlib]System.Object
0x3017  dup
0x3018  ldc.i4.0
0x3019  ldloc.s  6
0x301b  stelem.ref
0x301c  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3021  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3026  ret
0x3027  ldloc.0
0x3028  brfalse  loc_3197
0x302d  ldarg.1
0x302e  ldstr    aInstallinfoAdm// "InstallInfo.AdminTargetFolder"
0x3033  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x3038  brfalse.s loc_3056
0x303a  ldloc.0
0x303b  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x3040  ldloc.0
0x3041  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_AdminTargetFolder()
0x3046  ldc.i4.1
0x3047  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x304c  call     int32 [mscorlib]System.String::Compare(string, string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x3051  ldc.i4.0
0x3052  ceq
0x3054  br.s     loc_3057
0x3056  ldc.i4.0
0x3057  stloc.s  7
0x3059  ldsfld   string [mscorlib]System.String::Empty
0x305e  stloc.s  8
0x3060  ldloc.s  7
0x3062  brfalse.s loc_3069
0x3064  call     void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Elevated::SetSystemContext()
0x3069  ldarg.0
0x306a  ldfld    string Microsoft.Crm.Setup.Common.TargetFolderValidator::targetFolder
0x306f  stloc.s  8
0x3071  br.s     loc_307C
0x3073  ldloc.s  8
0x3075  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x307a  stloc.s  8
0x307c  ldloc.s  8
0x307e  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x3083  brfalse.s loc_3073
0x3085  ldloc.s  8
0x3087  ldstr    aTmpdir0// "tmpdir0"
0x308c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3091  stloc.s  9
0x3093  ldc.i4.1
0x3094  stloc.s  0xB
0x3096  br.s     loc_30C6
0x3098  ldloc.s  8
0x309a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x309f  ldstr    aTmpdir0_0// "tmpdir{0}"
0x30a4  ldc.i4.1
0x30a5  newarr   [mscorlib]System.Object
0x30aa  dup
0x30ab  ldc.i4.0
0x30ac  ldloc.s  0xB
0x30ae  box      [mscorlib]System.Int32
0x30b3  stelem.ref
0x30b4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x30b9  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x30be  stloc.s  9
0x30c0  ldloc.s  0xB
0x30c2  ldc.i4.1
0x30c3  add
0x30c4  stloc.s  0xB
0x30c6  ldloc.s  9
0x30c8  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x30cd  brtrue.s loc_3098
0x30cf  ldloc.s  8
0x30d1  ldstr    aTmpfile0// "tmpfile0"
0x30d6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x30db  stloc.s  0xA
0x30dd  ldc.i4.1
0x30de  stloc.s  0xC
0x30e0  br.s     loc_3110
0x30e2  ldloc.s  8
0x30e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x30e9  ldstr    aTmpfile0_0// "tmpfile{0}"
0x30ee  ldc.i4.1
0x30ef  newarr   [mscorlib]System.Object
0x30f4  dup
0x30f5  ldc.i4.0
0x30f6  ldloc.s  0xC
0x30f8  box      [mscorlib]System.Int32
0x30fd  stelem.ref
0x30fe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3103  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3108  stloc.s  0xA
0x310a  ldloc.s  0xC
0x310c  ldc.i4.1
0x310d  add
0x310e  stloc.s  0xC
0x3110  ldloc.s  0xA
  ... truncated ...
```
