# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::WaitForCompletion

- ea: `0xdf0`
- end: `0xe5c`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::WaitForCompletion`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x720`

## callees

- `0x2b0`
- `0x7f0`
- `0xdf0`

## string_xrefs

- `0xdf7`: `Waiting for PackageDeployer completion...`
- `0xe4c`: `PackageDeployer operation completed.`

## pseudocode

```c

```

## disassembly

```asm
0xdf0  ldarg.0
0xdf1  ldarg.0
0xdf2  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xdf7  ldstr    aWaitingForPack// "Waiting for PackageDeployer completion."...
0xdfc  call     string [mscorlib]System.String::Concat(string, string)
0xe01  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xe06  ldarg.0
0xe07  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_completionEvent
0xe0c  ldarg.0
0xe0d  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobTimeout
0xe12  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(valuetype [mscorlib]System.TimeSpan)
0xe17  brtrue.s loc_E45
0xe19  ldarg.0
0xe1a  ldarg.0
0xe1b  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xe20  ldstr    aPackagedeploye_6// "PackageDeployer operation timed out."
0xe25  call     string [mscorlib]System.String::Concat(string, string)
0xe2a  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xe2f  ldarg.0
0xe30  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xe35  ldstr    aImportOperatio// "Import operation timed out."
0xe3a  call     string [mscorlib]System.String::Concat(string, string)
0xe3f  newobj   instance void Microsoft.Crm.PackageDeployment.PackageDeployerException::.ctor(string message)
0xe44  throw
0xe45  ldarg.0
0xe46  ldarg.0
0xe47  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xe4c  ldstr    aPackagedeploye_7// "PackageDeployer operation completed."
0xe51  call     string [mscorlib]System.String::Concat(string, string)
0xe56  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xe5b  ret
```
