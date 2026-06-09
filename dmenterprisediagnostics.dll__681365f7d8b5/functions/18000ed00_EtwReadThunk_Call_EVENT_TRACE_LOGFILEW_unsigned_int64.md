# EtwReadThunk_Call(_EVENT_TRACE_LOGFILEW *,unsigned __int64)

- ea: `0x18000ed00`
- end: `0x18000ed19`
- name: `?EtwReadThunk_Call@@YA_KPEAU_EVENT_TRACE_LOGFILEW@@_K@Z`
- size: `25`
- prototype: `unsigned __int64 __fastcall(struct _EVENT_TRACE_LOGFILEW *, unsigned __int64)`
- caller_count: `256`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dd00`
- `0x18000dd10`
- `0x18000dd20`
- `0x18000dd30`
- `0x18000dd40`
- `0x18000dd50`
- `0x18000dd60`
- `0x18000dd70`
- `0x18000dd80`
- `0x18000dd90`
- `0x18000dda0`
- `0x18000ddb0`
- `0x18000ddc0`
- `0x18000ddd0`
- `0x18000dde0`
- `0x18000ddf0`
- `0x18000de00`
- `0x18000de10`
- `0x18000de20`
- `0x18000de30`
- `0x18000de40`
- `0x18000de50`
- `0x18000de60`
- `0x18000de70`
- `0x18000de80`
- `0x18000de90`
- `0x18000dea0`
- `0x18000deb0`
- `0x18000dec0`
- `0x18000ded0`
- `0x18000dee0`
- `0x18000def0`
- `0x18000df00`
- `0x18000df10`
- `0x18000df20`
- `0x18000df30`
- `0x18000df40`
- `0x18000df50`
- `0x18000df60`
- `0x18000df70`
- `0x18000df80`
- `0x18000df90`
- `0x18000dfa0`
- `0x18000dfb0`
- `0x18000dfc0`
- `0x18000dfd0`
- `0x18000dfe0`
- `0x18000dff0`
- `0x18000e000`
- `0x18000e010`

## callees

- `0x180027010`

## pseudocode

```c
__int64 __fastcall EtwReadThunk_Call(struct _EVENT_TRACE_LOGFILEW *a1, __int64 a2)
{
  return ((__int64 (__fastcall *)(struct _EVENT_TRACE_LOGFILEW *, _UNKNOWN *****************))(&off_180033008)[3 * a2 + 1])(
           a1,
           (&off_180033008)[3 * a2]);
}

```

## disassembly

```asm
0x18000ed00  lea     rax, [rdx+rdx*2]
0x18000ed04  lea     r8, off_180033008
0x18000ed0b  mov     rdx, [r8+rax*8]
0x18000ed0f  mov     rax, [r8+rax*8+8]
0x18000ed14  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
