# CWMDeColorConvDMO::QueryInterface(_GUID const &,void * *)

- ea: `0x18000df00`
- end: `0x18000df12`
- name: `?QueryInterface@CWMDeColorConvDMO@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `18`
- prototype: `__int64 __fastcall(CWMDeColorConvDMO *__hidden this, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000df20`
- `0x18000df40`
- `0x18000df60`
- `0x18000df80`
- `0x18000dfa0`

## callees

- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::QueryInterface(CWMDeColorConvDMO *this, const struct _GUID *a2, void **a3)
{
  return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *, void **))this + 54))(
           *((_QWORD *)this + 54),
           a2,
           a3);
}

```

## disassembly

```asm
0x18000df00  mov     rcx, [rcx+1B0h]
0x18000df07  mov     rax, [rcx]
0x18000df0a  mov     rax, [rax]
0x18000df0d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
