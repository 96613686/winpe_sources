# Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::InternalCheck

- ea: `0x3630`
- end: `0x376b`
- name: `Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::InternalCheck`
- size: `315`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2cd0`
- `0x3630`

## string_xrefs

- `0x3688`: `InstallLocation`

## pseudocode

```c

```

## disassembly

```asm
0x3630  ldnull
0x3631  stloc.0
0x3632  ldarg.0
0x3633  ldfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x3638  brtrue.s loc_3650
0x363a  ldarg.1
0x363b  brfalse.s loc_3650
0x363d  ldarg.1
0x363e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x3643  stloc.0
0x3644  ldarg.0
0x3645  ldloc.0
0x3646  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_TargetFolder()
0x364b  stfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x3650  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3655  stloc.1
0x3656  ldc.i4.m1
0x3657  stloc.2
0x3658  ldarg.0
0x3659  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::peerVersionComponentCode
0x365e  ldloca.s 1
0x3660  call     valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallState [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetProductCode(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid&)
0x3665  pop
0x3666  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x366b  ldloc.1
0x366c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3671  brfalse.s loc_367A
0x3673  ldloc.1
0x3674  call     valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallState [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::QueryProductState(valuetype [mscorlib]System.Guid)
0x3679  stloc.2
0x367a  ldsfld   string [mscorlib]System.String::Empty
0x367f  stloc.3
0x3680  ldloc.2
0x3681  ldc.i4.m1
0x3682  beq      loc_3764
0x3687  ldloc.1
0x3688  ldstr    aInstalllocatio// "InstallLocation"
0x368d  call     string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.MsiUtility::GetProductInfo(valuetype [mscorlib]System.Guid, string)
0x3692  stloc.3
0x3693  ldloc.3
0x3694  callvirt instance string [mscorlib]System.String::Trim()
0x3699  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x369e  stloc.3
0x369f  ldloc.3
0x36a0  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x36a5  stloc.s  4
0x36a7  ldloca.s 4
0x36a9  call     instance string [mscorlib]System.Char::ToString()
0x36ae  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x36b3  brfalse.s loc_36C5
0x36b5  ldloc.3
0x36b6  ldloc.3
0x36b7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x36bc  ldc.i4.1
0x36bd  sub
0x36be  ldc.i4.1
0x36bf  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x36c4  stloc.3
0x36c5  ldarg.0
0x36c6  ldarg.0
0x36c7  ldfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x36cc  callvirt instance string [mscorlib]System.String::Trim()
0x36d1  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x36d6  stfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x36db  ldarg.0
0x36dc  ldfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x36e1  ldsfld   char [mscorlib]System.IO.Path::DirectorySeparatorChar
0x36e6  stloc.s  4
0x36e8  ldloca.s 4
0x36ea  call     instance string [mscorlib]System.Char::ToString()
0x36ef  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x36f4  brfalse.s loc_3715
0x36f6  ldarg.0
0x36f7  ldarg.0
0x36f8  ldfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x36fd  ldarg.0
0x36fe  ldfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x3703  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3708  ldc.i4.1
0x3709  sub
0x370a  ldc.i4.1
0x370b  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0x3710  stfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x3715  ldloc.3
0x3716  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x371b  ldarg.0
0x371c  ldfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x3721  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x3726  ldc.i4.1
0x3727  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x372c  call     int32 [mscorlib]System.String::Compare(string, string, bool, class [mscorlib]System.Globalization.CultureInfo)
0x3731  brtrue.s loc_3764
0x3733  ldc.i4.2
0x3734  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x3739  ldarg.0
0x373a  ldstr    aTargetfolderva_8// "TargetFolderValidator.Failure.Collision"
0x373f  ldc.i4.0
0x3740  newarr   [mscorlib]System.Object
0x3745  call     instance string Microsoft.Crm.Setup.Common.Validator::GetResourceString(string name, object[] args)
0x374a  ldc.i4.1
0x374b  newarr   [mscorlib]System.Object
0x3750  dup
0x3751  ldc.i4.0
0x3752  ldarg.0
0x3753  ldfld    string Microsoft.Crm.Setup.Common.PeerTargetFolderValidator::targetFolder
0x3758  stelem.ref
0x3759  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x375e  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x3763  ret
0x3764  ldc.i4.0
0x3765  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x376a  ret
```
