# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceFailureCountResetTime

- ea: `0x1ca0`
- end: `0x1cba`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceFailureCountResetTime`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1a80`

## callees

- `0x1e60`

## pseudocode

```c

```

## disassembly

```asm
0x1ca0  ldarg.0
0x1ca1  ldstr    aFailcountreset// "failcountreset"
0x1ca6  ldc.r8   5.0
0x1caf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1cb4  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.AsyncServiceInstaller::ReadTimeSpanParameter(string parameterName, valuetype [mscorlib]System.TimeSpan defaultValue)
0x1cb9  ret
```
