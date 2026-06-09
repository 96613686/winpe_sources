# CIISServerCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a580`
- end: `0x18000a5a8`
- name: `?CreateInstance@CIISServerCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISServerCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009df0`
- `0x18000a580`

## pseudocode

```c
__int64 __fastcall CIISServerCF::CreateInstance(
        CIISServerCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return CIISServer::CreateServer(a2, (const WCHAR *)a2, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x18000a580  test    r9, r9
0x18000a583  jnz     short loc_18000A58B
0x18000a585  mov     eax, 80004003h
0x18000a58a  retn
0x18000a58b  mov     qword ptr [r9], 0
0x18000a592  test    rdx, rdx
0x18000a595  jnz     short loc_18000A59D
0x18000a597  mov     eax, 80004005h
0x18000a59c  retn
0x18000a59d  mov     r8, r9; void **
0x18000a5a0  mov     rcx, rdx; struct IUnknown *
0x18000a5a3  jmp     ?CreateServer@CIISServer@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CIISServer::CreateServer(IUnknown *,_GUID const &,void * *)
```
