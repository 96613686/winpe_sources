# Microsoft.Crm.Tools.Admin.PackageRetryInfo::GetPackageRetryInfo_0

- ea: `0x6cc0`
- end: `0x6dc6`
- name: `Microsoft.Crm.Tools.Admin.PackageRetryInfo::GetPackageRetryInfo_0`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6260`
- `0x6c90`

## callees

- `0x6c20`
- `0x6c40`
- `0x6c60`
- `0x6cc0`
- `0x6dd0`

## string_xrefs

- `0x6cfb`: `The complex data import failed because the compressed`
- `0x6d28`: `Invalid access token would be returned`
- `0x6d50`: `The solution installation or removal failed due to the installation or removal of another solution at the same time`

## pseudocode

```c

```

## disassembly

```asm
0x6cc0  newobj   instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::.ctor()
0x6cc5  stloc.0
0x6cc6  ldloc.0
0x6cc7  ldc.i4.0
0x6cc8  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_ShouldRetry(bool value)
0x6ccd  ldloc.0
0x6cce  ldc.i4   0xEA60
0x6cd3  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryInterval(int32 value)
0x6cd8  ldloc.0
0x6cd9  ldc.i4.0
0x6cda  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryReason(valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason value)
0x6cdf  ldarg.0
0x6ce0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6ce5  brfalse.s loc_6CFA
0x6ce7  ldloc.0
0x6ce8  ldc.i4.1
0x6ce9  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_ShouldRetry(bool value)
0x6cee  ldloc.0
0x6cef  ldc.i4.1
0x6cf0  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryReason(valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason value)
0x6cf5  br       loc_6DC4
0x6cfa  ldarg.0
0x6cfb  ldstr    aTheComplexData// "The complex data import failed because "...
0x6d00  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6d05  brfalse.s loc_6D1A
0x6d07  ldloc.0
0x6d08  ldc.i4.1
0x6d09  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_ShouldRetry(bool value)
0x6d0e  ldloc.0
0x6d0f  ldc.i4.3
0x6d10  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryReason(valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason value)
0x6d15  br       loc_6DC4
0x6d1a  ldarg.0
0x6d1b  ldstr    aOutofmemoryexc// "OutOfMemoryException"
0x6d20  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6d25  brtrue.s loc_6D34
0x6d27  ldarg.0
0x6d28  ldstr    aInvalidAccessT// "Invalid access token would be returned"
0x6d2d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6d32  brfalse.s loc_6D4F
0x6d34  ldloc.0
0x6d35  ldc.i4.1
0x6d36  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_ShouldRetry(bool value)
0x6d3b  ldloc.0
0x6d3c  ldc.i4.4
0x6d3d  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryReason(valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason value)
0x6d42  ldloc.0
0x6d43  ldc.i4   0x493E0
0x6d48  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryInterval(int32 value)
0x6d4d  br.s     loc_6DC4
0x6d4f  ldarg.0
0x6d50  ldstr    aTheSolutionIns// "The solution installation or removal fa"...
0x6d55  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6d5a  brfalse.s loc_6D77
0x6d5c  ldloc.0
0x6d5d  ldc.i4.1
0x6d5e  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_ShouldRetry(bool value)
0x6d63  ldloc.0
0x6d64  ldc.i4.5
0x6d65  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryReason(valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason value)
0x6d6a  ldloc.0
0x6d6b  ldc.i4   0x493E0
0x6d70  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryInterval(int32 value)
0x6d75  br.s     loc_6DC4
0x6d77  ldarg.0
0x6d78  call     bool [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.Retry.Policy.SqlExceptionRetryMapping::IsSqlErrorMessageMatch(string)
0x6d7d  brtrue.s loc_6D99
0x6d7f  ldarg.0
0x6d80  ldstr    aTheRpcServerIs// "The RPC server is unavailable"
0x6d85  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6d8a  brtrue.s loc_6D99
0x6d8c  ldarg.0
0x6d8d  ldstr    aNoSuchHostIsKn// "No such host is known"
0x6d92  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6d97  brfalse.s loc_6DA9
0x6d99  ldloc.0
0x6d9a  ldc.i4.1
0x6d9b  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_ShouldRetry(bool value)
0x6da0  ldloc.0
0x6da1  ldc.i4.6
0x6da2  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryReason(valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason value)
0x6da7  br.s     loc_6DC4
0x6da9  ldarg.0
0x6daa  ldstr    aPdError// "PD Error:"
0x6daf  callvirt instance bool [mscorlib]System.String::Contains(string)
0x6db4  brtrue.s loc_6DC4
0x6db6  ldloc.0
0x6db7  ldc.i4.1
0x6db8  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_ShouldRetry(bool value)
0x6dbd  ldloc.0
0x6dbe  ldc.i4.2
0x6dbf  callvirt instance void Microsoft.Crm.Tools.Admin.PackageRetryInfo::set_RetryReason(valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason value)
0x6dc4  ldloc.0
0x6dc5  ret
```
