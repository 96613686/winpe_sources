# CIISWebServiceCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180009af0`
- end: `0x180009b18`
- name: `?CreateInstance@CIISWebServiceCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISWebServiceCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180008fc0`
- `0x180009af0`

## pseudocode

```c
__int64 __fastcall CIISWebServiceCF::CreateInstance(
        CIISWebServiceCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return CIISWebService::CreateWebService(a2, (const WCHAR *)a2, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180009af0  test    r9, r9
0x180009af3  jnz     short loc_180009AFB
0x180009af5  mov     eax, 80004003h
0x180009afa  retn
0x180009afb  mov     qword ptr [r9], 0
0x180009b02  test    rdx, rdx
0x180009b05  jnz     short loc_180009B0D
0x180009b07  mov     eax, 80004005h
0x180009b0c  retn
0x180009b0d  mov     r8, r9; void **
0x180009b10  mov     rcx, rdx; struct IUnknown *
0x180009b13  jmp     ?CreateWebService@CIISWebService@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CIISWebService::CreateWebService(IUnknown *,_GUID const &,void * *)
```
