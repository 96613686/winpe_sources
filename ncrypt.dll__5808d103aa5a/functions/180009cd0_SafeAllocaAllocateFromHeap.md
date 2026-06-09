# SafeAllocaAllocateFromHeap

- ea: `0x180009cd0`
- end: `0x180009ce9`
- name: `SafeAllocaAllocateFromHeap`
- size: `25`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `33`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001e78`
- `0x18000382c`
- `0x180006730`
- `0x180008c1c`
- `0x180008da0`
- `0x1800090e0`
- `0x18000962c`
- `0x180009830`
- `0x180009aa0`
- `0x180009ecc`
- `0x18000d100`
- `0x18000f290`
- `0x1800102c0`
- `0x180010c90`
- `0x180011470`
- `0x1800116b0`
- `0x180011950`
- `0x180012120`
- `0x180015030`
- `0x180015770`
- `0x180015cd0`
- `0x180016350`
- `0x1800175f0`
- `0x180017990`
- `0x180019be0`
- `0x18001a06c`
- `0x18001a8e0`
- `0x18001ab20`
- `0x18001ac70`
- `0x18001aef0`
- `0x18001b140`
- `0x18001b2c0`
- `0x18001bbe8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180009ce2`

## pseudocode

```c
PVOID __fastcall SafeAllocaAllocateFromHeap(SIZE_T a1)
{
  return RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180009cd0  mov     rax, gs:60h
0x180009cd9  mov     r8, rcx
0x180009cdc  xor     edx, edx
0x180009cde  mov     rcx, [rax+30h]
0x180009ce2  jmp     cs:__imp_RtlAllocateHeap
```
