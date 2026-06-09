# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800042c0`
- end: `0x180004322`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800042c0`
- `0x180009010`

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
      return this[7](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800042c0  sub     rsp, 28h
0x1800042c4  mov     r11, rcx
0x1800042c7  mov     rax, r8
0x1800042ca  xor     ecx, ecx
0x1800042cc  mov     r10, rdx
0x1800042cf  mov     r8d, 80004003h
0x1800042d5  test    r9, r9
0x1800042d8  jz      short loc_18000431A
0x1800042da  mov     [r9], rcx
0x1800042dd  test    rdx, rdx
0x1800042e0  jz      short loc_180004305
0x1800042e2  cmp     [rax], ecx
0x1800042e4  jnz     short loc_1800042FD
0x1800042e6  cmp     [rax+4], ecx
0x1800042e9  jnz     short loc_1800042FD
0x1800042eb  cmp     dword ptr [rax+8], 0C0h
0x1800042f2  jnz     short loc_1800042FD
0x1800042f4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800042fb  jz      short loc_180004305
0x1800042fd  mov     r8d, 80040110h
0x180004303  jmp     short loc_18000431A
0x180004305  mov     rdx, rax
0x180004308  mov     r8, r9
0x18000430b  mov     rax, [r11+38h]
0x18000430f  mov     rcx, r10
0x180004312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004317  mov     r8d, eax
0x18000431a  mov     eax, r8d
0x18000431d  add     rsp, 28h
0x180004321  retn
```
