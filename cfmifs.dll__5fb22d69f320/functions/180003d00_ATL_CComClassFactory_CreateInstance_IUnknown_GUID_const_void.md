# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003d00`
- end: `0x180003d62`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003d00`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // r8d

  v5 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2
      && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180003d00  sub     rsp, 28h
0x180003d04  mov     r11, rcx
0x180003d07  mov     rax, r8
0x180003d0a  xor     ecx, ecx
0x180003d0c  mov     r10, rdx
0x180003d0f  mov     r8d, 80004003h
0x180003d15  test    r9, r9
0x180003d18  jz      short loc_180003D5A
0x180003d1a  mov     [r9], rcx
0x180003d1d  test    rdx, rdx
0x180003d20  jz      short loc_180003D45
0x180003d22  cmp     [rax], ecx
0x180003d24  jnz     short loc_180003D3D
0x180003d26  cmp     [rax+4], ecx
0x180003d29  jnz     short loc_180003D3D
0x180003d2b  cmp     dword ptr [rax+8], 0C0h
0x180003d32  jnz     short loc_180003D3D
0x180003d34  cmp     dword ptr [rax+0Ch], 46000000h
0x180003d3b  jz      short loc_180003D45
0x180003d3d  mov     r8d, 80040110h
0x180003d43  jmp     short loc_180003D5A
0x180003d45  mov     rdx, rax
0x180003d48  mov     r8, r9
0x180003d4b  mov     rax, [r11+40h]
0x180003d4f  mov     rcx, r10
0x180003d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d57  mov     r8d, eax
0x180003d5a  mov     eax, r8d
0x180003d5d  add     rsp, 28h
0x180003d61  retn
```
