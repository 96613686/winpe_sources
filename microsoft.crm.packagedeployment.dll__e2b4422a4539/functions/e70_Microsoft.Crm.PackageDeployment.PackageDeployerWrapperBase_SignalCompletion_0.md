# Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion_0

- ea: `0xe70`
- end: `0xebb`
- name: `Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::SignalCompletion_0`
- size: `75`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xe60`
- `0xf00`
- `0x1080`
- `0x11b0`

## callees

- `0x7f0`
- `0x870`
- `0xe70`

## string_xrefs

- `0xe7a`: `Signaling PackageDeployer operation completion.`

## pseudocode

```c

```

## disassembly

```asm
0xe70  ldarg.1
0xe71  brtrue.s loc_E8B
0xe73  ldarg.0
0xe74  ldarg.0
0xe75  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xe7a  ldstr    aSignalingPacka// "Signaling PackageDeployer operation com"...
0xe7f  call     string [mscorlib]System.String::Concat(string, string)
0xe84  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogInfo(string data)
0xe89  br.s     loc_EA7
0xe8b  ldarg.0
0xe8c  ldarg.0
0xe8d  ldfld    string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0xe92  ldstr    aSignalingPacka_0// "Signaling PackageDeployer operation err"...
0xe97  ldarg.1
0xe98  callvirt instance string [mscorlib]System.Object::ToString()
0xe9d  call     string [mscorlib]System.String::Concat(string, string, string)
0xea2  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogError(string data)
0xea7  ldarg.0
0xea8  ldarg.1
0xea9  stfld    class [mscorlib]System.Exception Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_jobException
0xeae  ldarg.0
0xeaf  ldfld    class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::_completionEvent
0xeb4  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xeb9  pop
0xeba  ret
```
