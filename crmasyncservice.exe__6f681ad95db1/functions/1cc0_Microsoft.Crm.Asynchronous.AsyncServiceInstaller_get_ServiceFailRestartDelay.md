# Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceFailRestartDelay

- ea: `0x1cc0`
- end: `0x1cda`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceInstaller::get_ServiceFailRestartDelay`
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
0x1cc0  ldarg.0
0x1cc1  ldstr    aResetdelay// "resetdelay"
0x1cc6  ldc.r8   60.0
0x1ccf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x1cd4  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Asynchronous.AsyncServiceInstaller::ReadTimeSpanParameter(string parameterName, valuetype [mscorlib]System.TimeSpan defaultValue)
0x1cd9  ret
```
