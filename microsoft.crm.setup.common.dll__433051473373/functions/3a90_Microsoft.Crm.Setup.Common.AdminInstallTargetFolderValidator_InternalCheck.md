# Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::InternalCheck

- ea: `0x3a90`
- end: `0x3bce`
- name: `Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::InternalCheck`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x3a90`

## string_xrefs

- `0x3ad3`: `TargetFolderValidator.Failure.InvalidPath`
- `0x3b67`: `TargetFolderValidator.Failure.NotAbsolutePath`

## pseudocode

```c

```

## disassembly

```asm
0x3a90  ldnull
0x3a91  stloc.0
0x3a92  ldarg.0
0x3a93  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3a98  brtrue.s loc_3AB0
0x3a9a  ldarg.1
0x3a9b  brfalse.s loc_3AB0
0x3a9d  ldarg.1
0x3a9e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x3aa3  stloc.0
0x3aa4  ldarg.0
0x3aa5  ldloc.0
0x3aa6  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x3aab  stfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3ab0  nop
0x3ab1  ldarg.0
0x3ab2  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3ab7  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x3abc  pop
0x3abd  leave.s  loc_3B0A
0x3abf  stloc.1
0x3ac0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x3ac5  ldstr    a01// "{0} {1}"
0x3aca  ldc.i4.2
0x3acb  newarr   [mscorlib]System.Object
0x3ad0  dup
0x3ad1  ldc.i4.0
0x3ad2  ldarg.0
0x3ad3  ldstr    aTargetfolderva// "TargetFolderValidator.Failure.InvalidPa"...
0x3ad8  ldc.i4.1
0x3ad9  newarr   [mscorlib]System.Object
0x3ade  dup
0x3adf  ldc.i4.0
0x3ae0  ldarg.0
0x3ae1  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3ae6  stelem.ref
0x3ae7  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3aec  stelem.ref
0x3aed  dup
0x3aee  ldc.i4.1
0x3aef  ldarg.0
0x3af0  ldloc.1
0x3af1  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x3af6  stelem.ref
0x3af7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3afc  stloc.2
0x3afd  ldc.i4.2
0x3afe  ldloc.2
0x3aff  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3b04  stloc.3
0x3b05  leave    loc_3BCC
0x3b0a  ldarg.0
0x3b0b  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b10  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x3b15  brfalse.s loc_3B65
0x3b17  ldc.i4.3
0x3b18  ldarg.0
0x3b19  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b1e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3b23  bgt.s    loc_3B65
0x3b25  ldc.i4.s 0x5C
0x3b27  ldarg.0
0x3b28  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b2d  ldc.i4.0
0x3b2e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3b33  bne.un.s loc_3B45
0x3b35  ldc.i4.s 0x5C
0x3b37  ldarg.0
0x3b38  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b3d  ldc.i4.1
0x3b3e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3b43  bne.un.s loc_3B65
0x3b45  ldc.i4.s 0x3A
0x3b47  ldarg.0
0x3b48  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b4d  ldc.i4.1
0x3b4e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3b53  bne.un.s loc_3B86
0x3b55  ldc.i4.s 0x5C
0x3b57  ldarg.0
0x3b58  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b5d  ldc.i4.2
0x3b5e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3b63  beq.s    loc_3B86
0x3b65  ldc.i4.2
0x3b66  ldarg.0
0x3b67  ldstr    aTargetfolderva_0// "TargetFolderValidator.Failure.NotAbsolu"...
0x3b6c  ldc.i4.1
0x3b6d  newarr   [mscorlib]System.Object
0x3b72  dup
0x3b73  ldc.i4.0
0x3b74  ldarg.0
0x3b75  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b7a  stelem.ref
0x3b7b  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3b80  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3b85  ret
0x3b86  ldc.i4.m1
0x3b87  ldarg.0
0x3b88  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3b8d  ldc.i4.2
0x3b8e  newarr   [mscorlib]System.Char
0x3b93  dup
0x3b94  ldc.i4.0
0x3b95  ldc.i4.s 0x3B
0x3b97  stelem.i2
0x3b98  dup
0x3b99  ldc.i4.1
0x3b9a  ldc.i4.s 0x2F
0x3b9c  stelem.i2
0x3b9d  callvirt instance int32 [mscorlib]System.String::IndexOfAny(char[])
0x3ba2  beq.s    loc_3BC5
0x3ba4  ldc.i4.2
0x3ba5  ldarg.0
0x3ba6  ldstr    aTargetfolderva_5// "TargetFolderValidator.Failure.Unsupport"...
0x3bab  ldc.i4.1
0x3bac  newarr   [mscorlib]System.Object
0x3bb1  dup
0x3bb2  ldc.i4.0
0x3bb3  ldarg.0
0x3bb4  ldfld    string Microsoft.Crm.Setup.Common.AdminInstallTargetFolderValidator::targetFolder
0x3bb9  stelem.ref
0x3bba  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3bbf  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3bc4  ret
0x3bc5  ldc.i4.0
0x3bc6  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x3bcb  ret
0x3bcc  ldloc.3
0x3bcd  ret
```
