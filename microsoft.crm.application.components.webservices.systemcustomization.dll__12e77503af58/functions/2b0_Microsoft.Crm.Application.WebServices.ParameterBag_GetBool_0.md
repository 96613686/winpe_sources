# Microsoft.Crm.Application.WebServices.ParameterBag::GetBool_0

- ea: `0x2b0`
- end: `0x2bd`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetBool_0`
- size: `13`
- prototype: ``
- caller_count: `37`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`
- `0x26f0`
- `0x2ad0`
- `0x2b10`
- `0x2b90`
- `0x2bd0`
- `0x2bf0`
- `0x2c10`
- `0x2c30`
- `0x2c60`
- `0x2cb0`
- `0x2cf0`
- `0x2e60`
- `0x2e80`
- `0x2ef0`
- `0x2f10`
- `0x2f30`
- `0x2f50`
- `0x2fc0`
- `0x2fe0`
- `0x3450`
- `0x3880`
- `0x39c0`
- `0x3a00`
- `0x3a40`
- `0x3a60`
- `0x3a80`
- `0x3ac0`
- `0x3c10`
- `0x3cb0`
- `0x3e00`
- `0x3e20`
- `0x3e40`
- `0x3eb0`
- `0x3f80`
- `0x3ff0`
- `0x4100`

## callees

- `0x220`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.0
0x2b1  ldarg.1
0x2b2  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x2b7  call     bool [mscorlib]System.Boolean::Parse(string)
0x2bc  ret
```
