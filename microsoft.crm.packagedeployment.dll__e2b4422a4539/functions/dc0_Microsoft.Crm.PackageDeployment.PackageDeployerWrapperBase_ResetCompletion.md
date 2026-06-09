# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ResetCompletion

- ea: `0xdc0`
- end: `0xdea`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::ResetCompletion`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x720`

## callees

- `0x7f0`

## string_xrefs

- `0xdc7`: `Resetting PackageDeployer operation completion state.`

## pseudocode

```c

```

## disassembly

```asm
0xdc0  ldarg.0
0xdc1  ldarg.0
0xdc2  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xdc7  ldstr    aResettingPacka// "Resetting PackageDeployer operation com"...
0xdcc  call     string [mscorlib]System.String::Concat(string, string)
0xdd1  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xdd6  ldarg.0
0xdd7  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_completionEvent
0xddc  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Reset()
0xde1  pop
0xde2  ldarg.0
0xde3  ldnull
0xde4  stfld    class [mscorlib]System.Exception Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobException
0xde9  ret
```
