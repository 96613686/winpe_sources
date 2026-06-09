# Microsoft.Crm.Tools.Admin.ExistingRSValidator::InternalCheck

- ea: `0x11b20`
- end: `0x11cf5`
- name: `Microsoft.Crm.Tools.Admin.ExistingRSValidator::InternalCheck`
- size: `469`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x84f0`
- `0x8ab0`
- `0x11b20`

## string_xrefs

- `0x11bfa`: `ExistingRSValidator.Failure.NoPrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x11b20  ldarg.1
0x11b21  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x11b26  stloc.0
0x11b27  ldloc.0
0x11b28  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11b2d  newobj   instance void [System]System.Uri::.ctor(string)
0x11b32  stloc.1
0x11b33  ldloc.1
0x11b34  callvirt instance string [System]System.Uri::get_Host()
0x11b39  call     class [System]System.Net.IPHostEntry [System]System.Net.Dns::GetHostEntry(string)
0x11b3e  pop
0x11b3f  leave.s  loc_11B8F
0x11b41  stloc.3
0x11b42  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x11b47  ldstr    a01_1// "{0} {1}"
0x11b4c  ldc.i4.2
0x11b4d  newarr   [mscorlib]System.Object
0x11b52  dup
0x11b53  ldc.i4.0
0x11b54  ldarg.0
0x11b55  ldstr    aExistingrsvali// "ExistingRSValidator.Failure.UrlNotResol"...
0x11b5a  ldc.i4.1
0x11b5b  newarr   [mscorlib]System.Object
0x11b60  dup
0x11b61  ldc.i4.0
0x11b62  ldloc.0
0x11b63  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11b68  stelem.ref
0x11b69  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11b6e  stelem.ref
0x11b6f  dup
0x11b70  ldc.i4.1
0x11b71  ldarg.0
0x11b72  ldloc.3
0x11b73  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x11b78  stelem.ref
0x11b79  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11b7e  stloc.s  4
0x11b80  ldc.i4.2
0x11b81  ldloc.s  4
0x11b83  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x11b88  stloc.s  5
0x11b8a  leave    loc_11CF2
0x11b8f  ldloc.1
0x11b90  newobj   instance void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.UrlAccessValidator::.ctor(class [System]System.Uri)
0x11b95  ldarg.1
0x11b96  callvirt instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::Check(class [mscorlib]System.Collections.IDictionary)
0x11b9b  stloc.2
0x11b9c  ldc.i4.2
0x11b9d  ldloc.2
0x11b9e  callvirt instance valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::get_Result()
0x11ba3  bne.un.s loc_11BA7
0x11ba5  ldloc.2
0x11ba6  ret
0x11ba7  nop
0x11ba8  ldloc.1
0x11ba9  call     void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.ReportsUtility::ValidateServer(class [System]System.Uri)
0x11bae  leave    loc_11CEB
0x11bb3  stloc.s  6
0x11bb5  ldc.i4   0x80048303
0x11bba  ldloc.s  6
0x11bbc  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x11bc1  bne.un.s loc_11BEA
0x11bc3  ldc.i4.2
0x11bc4  ldarg.0
0x11bc5  ldstr    aExistingrsvali_0// "ExistingRSValidator.Failure.Not2012OrLa"...
0x11bca  ldc.i4.1
0x11bcb  newarr   [mscorlib]System.Object
0x11bd0  dup
0x11bd1  ldc.i4.0
0x11bd2  ldloc.0
0x11bd3  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11bd8  stelem.ref
0x11bd9  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11bde  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x11be3  stloc.s  5
0x11be5  leave    loc_11CF2
0x11bea  ldc.i4   0x80048302
0x11bef  ldloc.s  6
0x11bf1  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x11bf6  bne.un.s loc_11C1F
0x11bf8  ldc.i4.2
0x11bf9  ldarg.0
0x11bfa  ldstr    aExistingrsvali_1// "ExistingRSValidator.Failure.NoPrivilege"
0x11bff  ldc.i4.1
0x11c00  newarr   [mscorlib]System.Object
0x11c05  dup
0x11c06  ldc.i4.0
0x11c07  ldloc.0
0x11c08  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11c0d  stelem.ref
0x11c0e  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11c13  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x11c18  stloc.s  5
0x11c1a  leave    loc_11CF2
0x11c1f  ldc.i4   0x80048301
0x11c24  ldloc.s  6
0x11c26  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x11c2b  bne.un.s loc_11C54
0x11c2d  ldc.i4.2
0x11c2e  ldarg.0
0x11c2f  ldstr    aExistingrsvali_2// "ExistingRSValidator.Failure.InvalidUrl"
0x11c34  ldc.i4.1
0x11c35  newarr   [mscorlib]System.Object
0x11c3a  dup
0x11c3b  ldc.i4.0
0x11c3c  ldloc.0
0x11c3d  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11c42  stelem.ref
0x11c43  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11c48  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x11c4d  stloc.s  5
0x11c4f  leave    loc_11CF2
0x11c54  ldc.i4   0x80048309
0x11c59  ldloc.s  6
0x11c5b  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x11c60  bne.un.s loc_11C8B
0x11c62  ldc.i4.2
0x11c63  ldarg.0
0x11c64  ldstr    aExistingrsvali_3// "ExistingRSValidator.Failure.WorkgroupHo"...
0x11c69  ldc.i4.1
0x11c6a  newarr   [mscorlib]System.Object
0x11c6f  dup
0x11c70  ldc.i4.0
0x11c71  ldloc.0
0x11c72  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11c77  stelem.ref
0x11c78  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11c7d  ldsfld   string Microsoft.Crm.Tools.Admin.ExistingRSValidator::WorkgroupHotfixFailureLink
0x11c82  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string, string)
0x11c87  stloc.s  5
0x11c89  leave.s  loc_11CF2
0x11c8b  ldc.i4.2
0x11c8c  ldarg.0
0x11c8d  ldstr    aExistingrsvali_4// "ExistingRSValidator.Failure.UnknownWith"...
0x11c92  ldc.i4.2
0x11c93  newarr   [mscorlib]System.Object
0x11c98  dup
0x11c99  ldc.i4.0
0x11c9a  ldloc.0
0x11c9b  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11ca0  stelem.ref
0x11ca1  dup
0x11ca2  ldc.i4.1
0x11ca3  ldarg.0
0x11ca4  ldloc.s  6
0x11ca6  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x11cab  stelem.ref
0x11cac  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11cb1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x11cb6  stloc.s  5
0x11cb8  leave.s  loc_11CF2
0x11cba  stloc.s  7
0x11cbc  ldc.i4.2
0x11cbd  ldarg.0
0x11cbe  ldstr    aExistingrsvali_4// "ExistingRSValidator.Failure.UnknownWith"...
0x11cc3  ldc.i4.2
0x11cc4  newarr   [mscorlib]System.Object
0x11cc9  dup
0x11cca  ldc.i4.0
0x11ccb  ldloc.0
0x11ccc  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11cd1  stelem.ref
0x11cd2  dup
0x11cd3  ldc.i4.1
0x11cd4  ldarg.0
0x11cd5  ldloc.s  7
0x11cd7  call     instance string [Microsoft.Crm.Tools.EDW.Framework]Microsoft.Crm.Tools.EDW.Framework.ConditionBase::BuildExceptionMessage(class [mscorlib]System.Exception)
0x11cdc  stelem.ref
0x11cdd  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11ce2  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x11ce7  stloc.s  5
0x11ce9  leave.s  loc_11CF2
0x11ceb  ldc.i4.0
0x11cec  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x11cf1  ret
0x11cf2  ldloc.s  5
0x11cf4  ret
```
