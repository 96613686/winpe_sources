# CIISDsCrMapCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000de70`
- end: `0x18000de98`
- name: `?CreateInstance@CIISDsCrMapCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISDsCrMapCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a94c`
- `0x18000de70`

## pseudocode

```c
__int64 __fastcall CIISDsCrMapCF::CreateInstance(
        CIISDsCrMapCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return CIISDsCrMap::Create(a2, (const WCHAR *)a2, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000de70  test    r9, r9
0x18000de73  jnz     short loc_18000DE7B
0x18000de75  mov     eax, 80004003h
0x18000de7a  retn
0x18000de7b  mov     qword ptr [r9], 0
0x18000de82  test    rdx, rdx
0x18000de85  jnz     short loc_18000DE8D
0x18000de87  mov     eax, 80004005h
0x18000de8c  retn
0x18000de8d  mov     r8, r9; void **
0x18000de90  mov     rcx, rdx; struct IUnknown *
0x18000de93  jmp     ?Create@CIISDsCrMap@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CIISDsCrMap::Create(IUnknown *,_GUID const &,void * *)
```
