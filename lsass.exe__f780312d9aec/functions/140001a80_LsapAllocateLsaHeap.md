# LsapAllocateLsaHeap

- ea: `0x140001a80`
- end: `0x140001a9c`
- name: `LsapAllocateLsaHeap`
- size: `28`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140001720`
- `0x140003584`
- `0x1400037b8`
- `0x140003a6c`
- `0x140003c04`
- `0x140003ce8`
- `0x140003e9c`
- `0x140004cb0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140001a95`

## pseudocode

```c
PVOID __fastcall LsapAllocateLsaHeap(unsigned int a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, a1);
}

```

## disassembly

```asm
0x140001a80  mov     r8d, ecx
0x140001a83  mov     edx, 8
0x140001a88  mov     rcx, gs:60h
0x140001a91  mov     rcx, [rcx+30h]
0x140001a95  jmp     cs:__imp_RtlAllocateHeap
```
