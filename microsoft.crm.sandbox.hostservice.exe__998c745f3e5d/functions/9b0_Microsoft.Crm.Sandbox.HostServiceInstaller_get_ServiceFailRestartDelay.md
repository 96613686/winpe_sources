# Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceFailRestartDelay

- ea: `0x9b0`
- end: `0x9ca`
- name: `Microsoft.Crm.Sandbox.HostServiceInstaller::get_ServiceFailRestartDelay`
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
0x9b0  ldarg.0
0x9b1  ldstr    aResetdelay// "resetdelay"
0x9b6  ldc.r8   60.0
0x9bf  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x9c4  call     instance valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Sandbox.HostServiceInstaller::ReadTimeSpanParameter(string parameterName, valuetype [mscorlib]System.TimeSpan defaultValue)
0x9c9  ret
```
