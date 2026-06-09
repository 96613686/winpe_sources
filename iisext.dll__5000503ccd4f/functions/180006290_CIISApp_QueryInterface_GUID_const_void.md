# CIISApp::QueryInterface(_GUID const &,void * *)

- ea: `0x180006290`
- end: `0x1800062aa`
- name: `?QueryInterface@CIISApp@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `26`
- prototype: `__int64 __fastcall(CIISApp *__hidden this, const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800062b0`
- `0x1800062c0`
- `0x1800062d0`

## callees

- `0x180006290`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISApp::QueryInterface(CIISApp *this, const struct _GUID *a2, void **a3)
{
  if ( a3 )
    return (***((__int64 (__fastcall ****)(_QWORD, const struct _GUID *))this + 6))(*((_QWORD *)this + 6), a2);
  else
    return 2147500035LL;
}

```

## disassembly

```asm
0x180006290  test    r8, r8
0x180006293  jnz     short loc_18000629B
0x180006295  mov     eax, 80004003h
0x18000629a  retn
0x18000629b  mov     rcx, [rcx+30h]
0x18000629f  mov     rax, [rcx]
0x1800062a2  mov     rax, [rax]
0x1800062a5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
