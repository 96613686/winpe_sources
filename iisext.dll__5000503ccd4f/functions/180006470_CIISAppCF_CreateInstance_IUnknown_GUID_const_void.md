# CIISAppCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006470`
- end: `0x180006498`
- name: `?CreateInstance@CIISAppCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `int(CIISAppCF *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180005a58`
- `0x180006470`

## pseudocode

```c
__int64 __fastcall CIISAppCF::CreateInstance(CIISAppCF *this, struct IUnknown *a2, const struct _GUID *a3, void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return CIISApp::CreateApp(a2, (const WCHAR *)a2, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180006470  test    r9, r9
0x180006473  jnz     short loc_18000647B
0x180006475  mov     eax, 80004003h
0x18000647a  retn
0x18000647b  mov     qword ptr [r9], 0
0x180006482  test    rdx, rdx
0x180006485  jnz     short loc_18000648D
0x180006487  mov     eax, 80004005h
0x18000648c  retn
0x18000648d  mov     r8, r9; void **
0x180006490  mov     rcx, rdx; struct IUnknown *
0x180006493  jmp     ?CreateApp@CIISApp@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CIISApp::CreateApp(IUnknown *,_GUID const &,void * *)
```
