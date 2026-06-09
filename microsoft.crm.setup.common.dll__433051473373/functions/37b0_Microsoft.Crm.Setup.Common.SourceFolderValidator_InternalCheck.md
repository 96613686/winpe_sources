# Microsoft.Crm.Setup.Common.SourceFolderValidator::InternalCheck

- ea: `0x37b0`
- end: `0x3a45`
- name: `Microsoft.Crm.Setup.Common.SourceFolderValidator::InternalCheck`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x37b0`

## string_xrefs

- `0x37f1`: `SourceFolderValidator.Failure.InvalidPath`
- `0x3865`: `SourceFolderValidator.Failure.NotAbsolutePath`
- `0x3893`: `SourceFolderValidator.Failure.NonexistingPath`
- `0x38e3`: `SourceFolderValidator.Failure.UnauthorizedAccess`
- `0x396c`: `SourceFolderValidator.Failure.MsiDoesNotExist`
- `0x39ab`: `SourceFolderValidator.Failure.MsiProductInvalid`
- `0x39f0`: `SourceFolderValidator.Failure.MsiVersionInvalid`
- `0x3a26`: `SourceFolderValidator.Failure.MsiLanguageInvalid`

## pseudocode

```c

```

## disassembly

```asm
0x37b0  ldarg.0
0x37b1  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x37b6  brtrue.s loc_37CE
0x37b8  ldarg.1
0x37b9  brfalse.s loc_37CE
0x37bb  ldarg.1
0x37bc  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x37c1  stloc.0
0x37c2  ldarg.0
0x37c3  ldloc.0
0x37c4  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_SourceFolder()
0x37c9  stfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x37ce  nop
0x37cf  ldarg.0
0x37d0  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x37d5  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x37da  pop
0x37db  leave.s  loc_3828
0x37dd  stloc.1
0x37de  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x37e3  ldstr    a01// "{0} {1}"
0x37e8  ldc.i4.2
0x37e9  newarr   [mscorlib]System.Object
0x37ee  dup
0x37ef  ldc.i4.0
0x37f0  ldarg.0
0x37f1  ldstr    aSourcefolderva// "SourceFolderValidator.Failure.InvalidPa"...
0x37f6  ldc.i4.1
0x37f7  newarr   [mscorlib]System.Object
0x37fc  dup
0x37fd  ldc.i4.0
0x37fe  ldarg.0
0x37ff  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x3804  stelem.ref
0x3805  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x380a  stelem.ref
0x380b  dup
0x380c  ldc.i4.1
0x380d  ldarg.0
0x380e  ldloc.1
0x380f  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x3814  stelem.ref
0x3815  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x381a  stloc.2
0x381b  ldc.i4.2
0x381c  ldloc.2
0x381d  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3822  stloc.3
0x3823  leave    loc_3A43
0x3828  ldarg.0
0x3829  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x382e  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x3833  brfalse.s loc_3863
0x3835  ldc.i4.3
0x3836  ldarg.0
0x3837  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x383c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3841  bgt.s    loc_3863
0x3843  ldc.i4.s 0x5C
0x3845  ldarg.0
0x3846  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x384b  ldc.i4.0
0x384c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3851  bne.un.s loc_3884
0x3853  ldc.i4.s 0x5C
0x3855  ldarg.0
0x3856  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x385b  ldc.i4.1
0x385c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3861  beq.s    loc_3884
0x3863  ldc.i4.2
0x3864  ldarg.0
0x3865  ldstr    aSourcefolderva_0// "SourceFolderValidator.Failure.NotAbsolu"...
0x386a  ldc.i4.1
0x386b  newarr   [mscorlib]System.Object
0x3870  dup
0x3871  ldc.i4.0
0x3872  ldarg.0
0x3873  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x3878  stelem.ref
0x3879  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x387e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3883  ret
0x3884  ldarg.0
0x3885  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x388a  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x388f  brtrue.s loc_38B2
0x3891  ldc.i4.2
0x3892  ldarg.0
0x3893  ldstr    aSourcefolderva_1// "SourceFolderValidator.Failure.Nonexisti"...
0x3898  ldc.i4.1
0x3899  newarr   [mscorlib]System.Object
0x389e  dup
0x389f  ldc.i4.0
0x38a0  ldarg.0
0x38a1  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x38a6  stelem.ref
0x38a7  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x38ac  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x38b1  ret
0x38b2  nop
0x38b3  ldarg.0
0x38b4  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x38b9  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x38be  pop
0x38bf  ldarg.0
0x38c0  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x38c5  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x38ca  pop
0x38cb  leave.s  loc_390F
0x38cd  stloc.s  4
0x38cf  ldc.i4.2
0x38d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x38d5  ldstr    a01// "{0} {1}"
0x38da  ldc.i4.2
0x38db  newarr   [mscorlib]System.Object
0x38e0  dup
0x38e1  ldc.i4.0
0x38e2  ldarg.0
0x38e3  ldstr    aSourcefolderva_2// "SourceFolderValidator.Failure.Unauthori"...
0x38e8  ldc.i4.0
0x38e9  newarr   [mscorlib]System.Object
0x38ee  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x38f3  stelem.ref
0x38f4  dup
0x38f5  ldc.i4.1
0x38f6  ldarg.0
0x38f7  ldloc.s  4
0x38f9  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x38fe  stelem.ref
0x38ff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3904  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3909  stloc.3
0x390a  leave    loc_3A43
0x390f  ldc.i4.m1
0x3910  ldarg.0
0x3911  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x3916  ldc.i4.s 0x2F
0x3918  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x391d  beq.s    loc_3937
0x391f  ldc.i4.2
0x3920  ldarg.0
0x3921  ldstr    aSourcefolderva_3// "SourceFolderValidator.Failure.Unsupport"...
0x3926  ldc.i4.0
0x3927  newarr   [mscorlib]System.Object
0x392c  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3931  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3936  ret
0x3937  ldarg.1
0x3938  brfalse  loc_3A3C
0x393d  ldarg.1
0x393e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x3943  stloc.s  5
0x3945  ldarg.1
0x3946  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProductInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x394b  stloc.s  6
0x394d  ldarg.0
0x394e  ldfld    string Microsoft.Crm.Setup.Common.SourceFolderValidator::sourceFolder
0x3953  ldloc.s  5
0x3955  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_PackageName()
0x395a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x395f  stloc.s  7
0x3961  ldloc.s  7
0x3963  call     bool [mscorlib]System.IO.File::Exists(string)
0x3968  brtrue.s loc_3982
0x396a  ldc.i4.2
0x396b  ldarg.0
0x396c  ldstr    aSourcefolderva_4// "SourceFolderValidator.Failure.MsiDoesNo"...
0x3971  ldc.i4.0
0x3972  newarr   [mscorlib]System.Object
0x3977  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x397c  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3981  ret
0x3982  ldloca.s 8
0x3984  ldloc.s  7
0x3986  ldstr    aProductcode// "ProductCode"
0x398b  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetProductProperty(string, string)
0x3990  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3995  ldloc.s  6
0x3997  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProductInfo::get_ExistingProductCode()
0x399c  stloc.s  0xB
0x399e  ldloca.s 0xB
0x39a0  ldloc.s  8
0x39a2  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x39a7  brtrue.s loc_39C1
0x39a9  ldc.i4.2
0x39aa  ldarg.0
0x39ab  ldstr    aSourcefolderva_5// "SourceFolderValidator.Failure.MsiProduc"...
0x39b0  ldc.i4.0
0x39b1  newarr   [mscorlib]System.Object
0x39b6  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x39bb  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x39c0  ret
0x39c1  ldloc.s  7
0x39c3  ldstr    aProductversion// "ProductVersion"
0x39c8  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetProductProperty(string, string)
0x39cd  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x39d2  stloc.s  9
0x39d4  ldloc.s  8
0x39d6  ldstr    aVersionstring// "VersionString"
0x39db  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetProductInfo(valuetype [mscorlib]System.Guid, string)
0x39e0  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x39e5  ldloc.s  9
0x39e7  callvirt instance bool [mscorlib]System.Version::Equals(class [mscorlib]System.Version)
0x39ec  brtrue.s loc_3A06
0x39ee  ldc.i4.2
0x39ef  ldarg.0
0x39f0  ldstr    aSourcefolderva_6// "SourceFolderValidator.Failure.MsiVersio"...
0x39f5  ldc.i4.0
0x39f6  newarr   [mscorlib]System.Object
0x39fb  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3a00  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3a05  ret
0x3a06  ldloc.s  7
0x3a08  ldstr    aProductlanguag// "ProductLanguage"
0x3a0d  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetProductProperty(string, string)
0x3a12  stloc.s  0xA
0x3a14  ldloc.s  6
0x3a16  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.ProductInfo::get_ExistingLanguage()
0x3a1b  ldloc.s  0xA
0x3a1d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x3a22  brfalse.s loc_3A3C
0x3a24  ldc.i4.2
0x3a25  ldarg.0
0x3a26  ldstr    aSourcefolderva_7// "SourceFolderValidator.Failure.MsiLangua"...
0x3a2b  ldc.i4.0
0x3a2c  newarr   [mscorlib]System.Object
0x3a31  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x3a36  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3a3b  ret
0x3a3c  ldc.i4.0
0x3a3d  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x3a42  ret
0x3a43  ldloc.3
0x3a44  ret
```
