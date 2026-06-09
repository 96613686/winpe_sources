# LsapFreeLsaHeap

- ea: `0x1400016c0`
- end: `0x1400016d9`
- name: `LsapFreeLsaHeap`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001720`
- `0x140002c24`
- `0x140003584`
- `0x1400037b8`
- `0x140003a6c`
- `0x140003ce8`
- `0x140003e9c`
- `0x140004d80`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1400016d2`

## pseudocode

```c
BOOLEAN __fastcall LsapFreeLsaHeap(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x1400016c0  mov     rax, gs:60h
0x1400016c9  mov     r8, rcx
0x1400016cc  xor     edx, edx
0x1400016ce  mov     rcx, [rax+30h]
0x1400016d2  jmp     cs:__imp_RtlFreeHeap
```
