# Microsoft.Crm.Application.WebServices.WorkflowWebService::InjectNewStepId

- ea: `0x8350`
- end: `0x836d`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InjectNewStepId`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x8260`

## pseudocode

```c

```

## disassembly

```asm
0x8350  ldarg.1
0x8351  ldc.i4.0
0x8352  ldarg.1
0x8353  ldarg.2
0x8354  ldc.i4.5
0x8355  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x835a  ldarg.2
0x835b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8360  add
0x8361  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x8366  ldarg.3
0x8367  call     string [mscorlib]System.String::Concat(string, string)
0x836c  ret
```
