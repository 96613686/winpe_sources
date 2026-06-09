# Microsoft.Crm.Sandbox.SandboxRestrictedTraceListener::GetTraceLevel

- ea: `0x1d70`
- end: `0x1d8e`
- name: `Microsoft.Crm.Sandbox.SandboxRestrictedTraceListener::GetTraceLevel`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1c60`
- `0x1cb0`
- `0x1d10`

## callees

- `0x1d70`

## pseudocode

```c

```

## disassembly

```asm
0x1d70  ldarg.0
0x1d71  ldc.i4.2
0x1d72  beq.s    loc_1D7E
0x1d74  ldarg.0
0x1d75  ldc.i4.4
0x1d76  beq.s    loc_1D86
0x1d78  ldarg.0
0x1d79  ldc.i4.8
0x1d7a  beq.s    loc_1D82
0x1d7c  br.s     loc_1D8A
0x1d7e  ldc.i4.1
0x1d7f  stloc.0
0x1d80  br.s     loc_1D8C
0x1d82  ldc.i4.3
0x1d83  stloc.0
0x1d84  br.s     loc_1D8C
0x1d86  ldc.i4.2
0x1d87  stloc.0
0x1d88  br.s     loc_1D8C
0x1d8a  ldc.i4.4
0x1d8b  stloc.0
0x1d8c  ldloc.0
0x1d8d  ret
```
