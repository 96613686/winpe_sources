# Microsoft.Crm.Application.WebServices.WorkflowWebService::AppendAttributeTypeInfo

- ea: `0x89f0`
- end: `0x8a21`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AppendAttributeTypeInfo`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7bb0`
- `0x7e70`
- `0x7fe0`

## callees

- `0x89f0`

## pseudocode

```c

```

## disassembly

```asm
0x89f0  ldarg.2
0x89f1  ldstr    asc_AB88// ";"
0x89f6  ldarg.3
0x89f7  call     string [mscorlib]System.String::Concat(string, string, string)
0x89fc  stloc.0
0x89fd  ldarg.1
0x89fe  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x8a03  brtrue.s loc_8A0E
0x8a05  ldarg.1
0x8a06  ldloc.0
0x8a07  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8a0c  pop
0x8a0d  ret
0x8a0e  ldarg.1
0x8a0f  ldstr    asc_BFA8// "&"
0x8a14  ldloc.0
0x8a15  call     string [mscorlib]System.String::Concat(string, string)
0x8a1a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8a1f  pop
0x8a20  ret
```
