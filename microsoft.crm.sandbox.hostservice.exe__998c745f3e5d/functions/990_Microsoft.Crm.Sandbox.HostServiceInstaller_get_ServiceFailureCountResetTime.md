# Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceFailureCountResetTime

- ea: `0x990`
- end: `0x9aa`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceFailureCountResetTime`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7b0`

## callees

- `0xa60`

## pseudocode

```c

```

## disassembly

```asm
0x990  ldarg.0
0x991  ldstr    aFailcountreset// "failcountreset"
0x996  ldc.r8   5.0
0x99f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x9a4  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.HostServiceInstaller::ReadTimeSpanParameter(string parameterName, valuetype [mscorlib]System.TimeSpan defaultValue)
0x9a9  ret
```
