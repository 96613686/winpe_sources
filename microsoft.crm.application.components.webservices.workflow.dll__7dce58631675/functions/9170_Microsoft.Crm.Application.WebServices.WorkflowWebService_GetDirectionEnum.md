# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum

- ea: `0x9170`
- end: `0x9182`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum`
- size: `18`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x22e0`
- `0x2820`
- `0x3480`
- `0x3e00`
- `0x3ea0`
- `0x4560`
- `0x45d0`
- `0x4740`
- `0x47b0`
- `0x4ab0`
- `0x4d60`
- `0x5040`
- `0x5300`
- `0x5700`
- `0x5ac0`
- `0x5dd0`
- `0x6b20`
- `0x6b90`
- `0x6cf0`

## callees

- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x9170  ldarg.1
0x9171  ldstr    aBefore// "before"
0x9176  ldc.i4.4
0x9177  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x917c  brtrue.s loc_9180
0x917e  ldc.i4.0
0x917f  ret
0x9180  ldc.i4.1
0x9181  ret
```
