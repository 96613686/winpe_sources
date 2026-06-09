# Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepId

- ea: `0x14840`
- end: `0x1485a`
- name: `Microsoft.Crm.Workflow.Services.ActivityServiceBase::FindStepId`
- size: `26`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x14930`
- `0x16b30`
- `0x188b0`
- `0x18c00`
- `0x18d50`
- `0x19570`
- `0x1a460`

## callees

- `0x14840`

## pseudocode

```c

```

## disassembly

```asm
0x14840  ldarg.1
0x14841  stloc.0
0x14842  ldarg.1
0x14843  ldc.i4.s 0x3A
0x14845  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x1484a  stloc.1
0x1484b  ldloc.1
0x1484c  ldc.i4.m1
0x1484d  beq.s    loc_14858
0x1484f  ldarg.1
0x14850  ldc.i4.0
0x14851  ldloc.1
0x14852  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x14857  stloc.0
0x14858  ldloc.0
0x14859  ret
```
