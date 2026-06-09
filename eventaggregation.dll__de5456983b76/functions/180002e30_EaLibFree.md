# EaLibFree

- ea: `0x180002e30`
- end: `0x180002e49`
- name: `EaLibFree`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `26`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002000`
- `0x1800022b0`
- `0x180002e50`
- `0x180003070`
- `0x180003250`
- `0x180003660`
- `0x180003e20`
- `0x1800085c4`
- `0x1800086d0`
- `0x180008940`
- `0x1800089a0`
- `0x180008d98`
- `0x180008ed0`
- `0x180008fb0`
- `0x180008fc0`
- `0x180009250`
- `0x180009300`
- `0x180009b20`
- `0x180009b58`
- `0x180009d38`
- `0x180009ff0`
- `0x18000a414`
- `0x18000a5f8`
- `0x18000aae8`
- `0x18000ab7c`
- `0x18000ad20`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180002e42`

## pseudocode

```c
BOOLEAN __fastcall EaLibFree(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180002e30  mov     rax, gs:60h
0x180002e39  mov     r8, rcx
0x180002e3c  xor     edx, edx
0x180002e3e  mov     rcx, [rax+30h]
0x180002e42  jmp     cs:__imp_RtlFreeHeap
```
