# CIISApplicationPoolCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180007fa0`
- end: `0x180007fc8`
- name: `?CreateInstance@CIISApplicationPoolCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISApplicationPoolCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000745c`
- `0x180007fa0`

## pseudocode

```c
__int64 __fastcall CIISApplicationPoolCF::CreateInstance(
        CIISApplicationPoolCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return CIISApplicationPool::CreateApplicationPool(a2, (const WCHAR *)a2, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180007fa0  test    r9, r9
0x180007fa3  jnz     short loc_180007FAB
0x180007fa5  mov     eax, 80004003h
0x180007faa  retn
0x180007fab  mov     qword ptr [r9], 0
0x180007fb2  test    rdx, rdx
0x180007fb5  jnz     short loc_180007FBD
0x180007fb7  mov     eax, 80004005h
0x180007fbc  retn
0x180007fbd  mov     r8, r9; void **
0x180007fc0  mov     rcx, rdx; struct IUnknown *
0x180007fc3  jmp     ?CreateApplicationPool@CIISApplicationPool@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CIISApplicationPool::CreateApplicationPool(IUnknown *,_GUID const &,void * *)
```
