# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140001d90`
- end: `0x140001df2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001d90`
- `0x140006010`

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
0x140001d90  sub     rsp, 28h
0x140001d94  mov     r11, rcx
0x140001d97  mov     rax, r8
0x140001d9a  xor     ecx, ecx
0x140001d9c  mov     r10, rdx
0x140001d9f  mov     r8d, 80004003h
0x140001da5  test    r9, r9
0x140001da8  jz      short loc_140001DEA
0x140001daa  mov     [r9], rcx
0x140001dad  test    rdx, rdx
0x140001db0  jz      short loc_140001DD5
0x140001db2  cmp     [rax], ecx
0x140001db4  jnz     short loc_140001DCD
0x140001db6  cmp     [rax+4], ecx
0x140001db9  jnz     short loc_140001DCD
0x140001dbb  cmp     dword ptr [rax+8], 0C0h
0x140001dc2  jnz     short loc_140001DCD
0x140001dc4  cmp     dword ptr [rax+0Ch], 46000000h
0x140001dcb  jz      short loc_140001DD5
0x140001dcd  mov     r8d, 80040110h
0x140001dd3  jmp     short loc_140001DEA
0x140001dd5  mov     rdx, rax
0x140001dd8  mov     r8, r9
0x140001ddb  mov     rax, [r11+40h]
0x140001ddf  mov     rcx, r10
0x140001de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001de7  mov     r8d, eax
0x140001dea  mov     eax, r8d
0x140001ded  add     rsp, 28h
0x140001df1  retn
```
