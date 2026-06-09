# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ResetCompletion

- ea: `0x15a0`
- end: `0x15ca`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::ResetCompletion`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xe90`

## callees

- `0xf60`

## string_xrefs

- `0x15a7`: `Resetting PackageDeployer operation completion state.`

## pseudocode

```c

```

## disassembly

```asm
0x15a0  ldarg.0
0x15a1  ldarg.0
0x15a2  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x15a7  ldstr    aResettingPacka// "Resetting PackageDeployer operation com"...
0x15ac  call     string [mscorlib]System.String::Concat(string, string)
0x15b1  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0x15b6  ldarg.0
0x15b7  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_completionEvent
0x15bc  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Reset()
0x15c1  pop
0x15c2  ldarg.0
0x15c3  ldnull
0x15c4  stfld    class [mscorlib]System.Exception Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_jobException
0x15c9  ret
```
