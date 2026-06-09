# CIISComputerCF::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006ff0`
- end: `0x180007018`
- name: `?CreateInstance@CIISComputerCF@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `40`
- prototype: `__int64 __fastcall(CIISComputerCF *this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000683c`
- `0x180006ff0`

## pseudocode

```c
__int64 __fastcall CIISComputerCF::CreateInstance(
        CIISComputerCF *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  if ( !a4 )
    return 2147500035LL;
  *a4 = 0;
  if ( a2 )
    return CIISComputer::CreateComputer(a2, (const struct _GUID *)a2, a4);
  else
    return 2147500037LL;
}

```

## disassembly

```asm
0x180006ff0  test    r9, r9
0x180006ff3  jnz     short loc_180006FFB
0x180006ff5  mov     eax, 80004003h
0x180006ffa  retn
0x180006ffb  mov     qword ptr [r9], 0
0x180007002  test    rdx, rdx
0x180007005  jnz     short loc_18000700D
0x180007007  mov     eax, 80004005h
0x18000700c  retn
0x18000700d  mov     r8, r9; void **
0x180007010  mov     rcx, rdx; struct IUnknown *
0x180007013  jmp     ?CreateComputer@CIISComputer@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CIISComputer::CreateComputer(IUnknown *,_GUID const &,void * *)
```
