# Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::ExecuteWithRetry

- ea: `0x16d70`
- end: `0x16e31`
- name: `Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::ExecuteWithRetry`
- size: `193`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x6c10`
- `0x6c30`
- `0x6c50`
- `0x6c90`
- `0x8630`
- `0x16d30`
- `0x16d70`

## string_xrefs

- `0x16da5`: `Failed to execute action {0} on attempt {1}. Retrying in {2} seconds. `

## pseudocode

```c

```

## disassembly

```asm
0x16d70  ldarg.2
0x16d71  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x16d76  pop
0x16d77  ldc.i4.1
0x16d78  stloc.0
0x16d79  br       loc_16E1D
0x16d7e  ldarga.s 3
0x16d80  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x16d85  ldarg.0
0x16d86  callvirt instance var<u1> class [mscorlib]System.Func`1<mvar<u1>>::Invoke()
0x16d8b  stloc.1
0x16d8c  leave    loc_16E2F
0x16d91  stloc.2
0x16d92  ldloc.0
0x16d93  ldc.i4.3
0x16d94  bge.s    loc_16DF9
0x16d96  ldloc.2
0x16d97  call     class Microsoft.Crm.Tools.Admin.PackageRetryInfo Microsoft.Crm.Tools.Admin.PackageRetryInfo::GetPackageRetryInfo(class [mscorlib]System.Exception ex)
0x16d9c  stloc.3
0x16d9d  ldloc.3
0x16d9e  callvirt instance bool Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_ShouldRetry()
0x16da3  brfalse.s loc_16DF9
0x16da5  ldstr    aFailedToExecut// "Failed to execute action {0} on attempt"...
0x16daa  ldarg.1
0x16dab  ldloc.0
0x16dac  box      [mscorlib]System.Int32
0x16db1  ldloc.3
0x16db2  callvirt instance int32 Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_RetryInterval()
0x16db7  ldc.i4   0x3E8
0x16dbc  div
0x16dbd  box      [mscorlib]System.Int32
0x16dc2  call     string [mscorlib]System.String::Format(string, object, object, object)
0x16dc7  ldstr    aReasonForRetry// "Reason for retry: {0}."
0x16dcc  ldloc.3
0x16dcd  callvirt instance valuetype Microsoft.Crm.Tools.Admin.PackageRetryReason Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_RetryReason()
0x16dd2  box      Microsoft.Crm.Tools.Admin.PackageRetryReason
0x16dd7  call     string [mscorlib]System.String::Format(string, object)
0x16ddc  call     string [mscorlib]System.String::Concat(string, string)
0x16de1  stloc.s  4
0x16de3  ldarg.2
0x16de4  ldloc.s  4
0x16de6  ldloc.2
0x16de7  call     void Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::LogInfoAsError(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, string message, class [mscorlib]System.Exception ex)
0x16dec  ldloc.3
0x16ded  callvirt instance int32 Microsoft.Crm.Tools.Admin.PackageRetryInfo::get_RetryInterval()
0x16df2  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x16df7  leave.s  loc_16E19
0x16df9  ldloc.2
0x16dfa  ldarg.2
0x16dfb  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x16e00  ldc.i4.3
0x16e01  ldstr    aExceptionOccur_3// "Exception occurred while executing acti"...
0x16e06  ldarg.1
0x16e07  call     string [mscorlib]System.String::Format(string, object)
0x16e0c  ldc.i4.0
0x16e0d  newarr   [mscorlib]System.Object
0x16e12  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x16e17  rethrow
0x16e19  ldloc.0
0x16e1a  ldc.i4.1
0x16e1b  add
0x16e1c  stloc.0
0x16e1d  ldloc.0
0x16e1e  ldc.i4.3
0x16e1f  ble      loc_16D7E
0x16e24  ldloca.s 5
0x16e26  initobj  mvar<u1>
0x16e2c  ldloc.s  5
0x16e2e  ret
0x16e2f  ldloc.1
0x16e30  ret
```
