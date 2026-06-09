# CdvmftMFT::QueryInterface(_GUID const &,void * *)

- ea: `0x180005bd0`
- end: `0x180005bdf`
- name: `?QueryInterface@CdvmftMFT@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `15`
- prototype: `__int64 __fastcall(CdvmftMFT *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005bf0`
- `0x180005c00`
- `0x180005c10`
- `0x180005c20`
- `0x180005c30`

## callees

- `0x18001e010`

## pseudocode

```c
__int64 __fastcall CdvmftMFT::QueryInterface(CdvmftMFT *this, const struct _GUID *a2, void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this - 2))(
           *((_QWORD *)this - 2),
           a2,
           a3);
}

```

## disassembly

```asm
0x180005bd0  mov     rcx, [rcx-10h]
0x180005bd4  mov     rax, [rcx]
0x180005bd7  mov     rax, [rax]
0x180005bda  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
