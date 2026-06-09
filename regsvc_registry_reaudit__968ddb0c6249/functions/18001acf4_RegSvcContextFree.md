# RegSvcContextFree

- ea: `0x18001acf4`
- end: `0x18001ad0d`
- name: `RegSvcContextFree`
- size: `25`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180019200`
- `0x18001a2d0`
- `0x18001a5b0`
- `0x18001a8d0`
- `0x18001a9f0`
- `0x18001aa60`
- `0x18001acc8`
- `0x18001b970`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18001ad06`

## pseudocode

```c
BOOLEAN __fastcall RegSvcContextFree(void *a1)
{
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18001acf4  mov     rax, gs:60h
0x18001acfd  mov     r8, rcx
0x18001ad00  xor     edx, edx
0x18001ad02  mov     rcx, [rax+30h]
0x18001ad06  jmp     cs:__imp_RtlFreeHeap
```
