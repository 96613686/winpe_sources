# Microsoft.Crm.Sdk.ServiceDescription::GetTypeParsers

- ea: `0x8ad0`
- end: `0x8adc`
- name: `Microsoft.Crm.Sdk.ServiceDescription::GetTypeParsers`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a60`

## callees

- `0x8b60`

## pseudocode

```c

```

## disassembly

```asm
0x8ad0  ldarg.0
0x8ad1  ldstr    aIfieldparser// "IFieldParser"
0x8ad6  call     instance class [mscorlib]System.Collections.IEnumerable Microsoft.Crm.Sdk.ServiceDescription::GetTypes(string interfaceName)
0x8adb  ret
```
