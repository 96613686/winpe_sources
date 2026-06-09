# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion_0

- ea: `0x1670`
- end: `0x16c0`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SignalCompletion_0`
- size: `80`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1660`
- `0x1700`
- `0x1890`
- `0x19c0`

## callees

- `0xf60`
- `0xfe0`
- `0x1670`

## string_xrefs

- `0x167a`: `Signaling PackageDeployer operation completion.`

## pseudocode

```c

```

## disassembly

```asm
0x1670  ldarg.1
0x1671  brtrue.s loc_168B
0x1673  ldarg.0
0x1674  ldarg.0
0x1675  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x167a  ldstr    aSignalingPacka// "Signaling PackageDeployer operation com"...
0x167f  call     string [mscorlib]System.String::Concat(string, string)
0x1684  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x1689  br.s     loc_16A7
0x168b  ldarg.0
0x168c  ldarg.0
0x168d  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x1692  ldstr    aSignalingPacka_0// "Signaling PackageDeployer operation err"...
0x1697  ldarg.1
0x1698  callvirt instance string [mscorlib]System.Object::ToString()
0x169d  call     string [mscorlib]System.String::Concat(string, string, string)
0x16a2  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0x16a7  ldarg.0
0x16a8  ldarg.1
0x16a9  stfld    class [mscorlib]System.Exception Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobException
0x16ae  ldarg.0
0x16af  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_completionEvent
0x16b4  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x16b9  pop
0x16ba  leave.s  loc_16BF
0x16bc  pop
0x16bd  leave.s  loc_16BF
0x16bf  ret
```
