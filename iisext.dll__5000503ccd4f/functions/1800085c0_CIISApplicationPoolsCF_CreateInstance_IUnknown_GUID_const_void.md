# CIISApplicationPoolsCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800085c0`
- end: `0x1800085e8`
- name: `?CreateInstance@CIISApplicationPoolsCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISApplicationPoolsCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000828c`
- `0x1800085c0`

## pseudocode

```c
__int64 __fastcall CIISApplicationPoolsCF::CreateInstance(
        CIISApplicationPoolsCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return CIISApplicationPools::CreateApplicationPools(a2, (const WCHAR *)a2, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x1800085c0  test    r9, r9
0x1800085c3  jnz     short loc_1800085CB
0x1800085c5  mov     eax, 80004003h
0x1800085ca  retn
0x1800085cb  mov     qword ptr [r9], 0
0x1800085d2  test    rdx, rdx
0x1800085d5  jnz     short loc_1800085DD
0x1800085d7  mov     eax, 80004005h
0x1800085dc  retn
0x1800085dd  mov     r8, r9; void **
0x1800085e0  mov     rcx, rdx; struct IUnknown *
0x1800085e3  jmp     ?CreateApplicationPools@CIISApplicationPools@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CIISApplicationPools::CreateApplicationPools(IUnknown *,_GUID const &,void * *)
```
