# SafeAllocaAllocateFromHeap

- ea: `0x180007940`
- end: `0x180007959`
- name: `SafeAllocaAllocateFromHeap`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `35`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001010`
- `0x180001930`
- `0x1800058e0`
- `0x180006070`
- `0x180006904`
- `0x180006b60`
- `0x180007990`
- `0x18000d2b0`
- `0x18000dea0`
- `0x1800105e0`
- `0x1800113a0`
- `0x180011f10`
- `0x1800126f0`
- `0x180012fa4`
- `0x180013740`
- `0x180013b80`
- `0x180014024`
- `0x18001d8e8`
- `0x18001de24`
- `0x18001e014`
- `0x18001e0dc`
- `0x18001e8c0`
- `0x180020718`
- `0x180020a70`
- `0x180021a74`
- `0x180021efc`
- `0x1800222f0`
- `0x180022608`
- `0x180022ca4`
- `0x180022fa8`
- `0x180023ac4`
- `0x180023e34`
- `0x180024190`
- `0x180024650`
- `0x180024a3c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180007952`

## pseudocode

```c
PVOID __fastcall SafeAllocaAllocateFromHeap(SIZE_T a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180007940  mov     rax, gs:60h
0x180007949  mov     r8, rcx
0x18000794c  xor     edx, edx
0x18000794e  mov     rcx, [rax+30h]
0x180007952  jmp     cs:__imp_RtlAllocateHeap
```
