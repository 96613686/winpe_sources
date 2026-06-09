# Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_MaximumThreadsPerCPU

- ea: `0xeea0`
- end: `0xeeb9`
- name: `Microsoft.Crm.Asynchronous.ServerAsyncOperationQueueConfiguration::get_MaximumThreadsPerCPU`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe6f0`
- `0xeea0`

## string_xrefs

- `0xeea1`: `AsyncMaximumThreadsPerCPU`

## pseudocode

```c

```

## disassembly

```asm
0xeea0  ldarg.0
0xeea1  ldstr    aAsyncmaximumth_0// "AsyncMaximumThreadsPerCPU"
0xeea6  call     instance object Microsoft.Crm.Asynchronous.ServerQueueConfigurationBase::GetDeploymentSetting(string settingName)
0xeeab  stloc.0
0xeeac  ldloc.0
0xeead  brfalse.s loc_EEB6
0xeeaf  ldloc.0
0xeeb0  unbox.any [mscorlib]System.Int32
0xeeb5  ret
0xeeb6  ldc.i4.s 0x64
0xeeb8  ret
```
