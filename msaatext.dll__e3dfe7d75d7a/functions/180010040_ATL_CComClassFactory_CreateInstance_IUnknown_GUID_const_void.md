# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180010040`
- end: `0x1800100a2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180010040`
- `0x180014010`

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
0x180010040  sub     rsp, 28h
0x180010044  mov     r11, rcx
0x180010047  mov     rax, r8
0x18001004a  xor     ecx, ecx
0x18001004c  mov     r10, rdx
0x18001004f  mov     r8d, 80004003h
0x180010055  test    r9, r9
0x180010058  jz      short loc_18001009A
0x18001005a  mov     [r9], rcx
0x18001005d  test    rdx, rdx
0x180010060  jz      short loc_180010085
0x180010062  cmp     [rax], ecx
0x180010064  jnz     short loc_18001007D
0x180010066  cmp     [rax+4], ecx
0x180010069  jnz     short loc_18001007D
0x18001006b  cmp     dword ptr [rax+8], 0C0h
0x180010072  jnz     short loc_18001007D
0x180010074  cmp     dword ptr [rax+0Ch], 46000000h
0x18001007b  jz      short loc_180010085
0x18001007d  mov     r8d, 80040110h
0x180010083  jmp     short loc_18001009A
0x180010085  mov     rdx, rax
0x180010088  mov     r8, r9
0x18001008b  mov     rax, [r11+40h]
0x18001008f  mov     rcx, r10
0x180010092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010097  mov     r8d, eax
0x18001009a  mov     eax, r8d
0x18001009d  add     rsp, 28h
0x1800100a1  retn
```
