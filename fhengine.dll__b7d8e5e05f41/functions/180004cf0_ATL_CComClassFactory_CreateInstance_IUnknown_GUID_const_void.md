# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004cf0`
- end: `0x180004d44`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004cf0`
- `0x180004f88`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        __int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  const struct _GUID *v4; // r11
  struct IUnknown *v5; // r10
  __int64 result; // rax

  v4 = a3;
  v5 = a2;
  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( !a2 || (unsigned int)ATL::InlineIsEqualUnknown(a3) )
      return this[8](v5, v4, a4);
    else
      return 2147746064LL;
  }
  return result;
}

```

## disassembly

```asm
0x180004cf0  push    rbx
0x180004cf2  sub     rsp, 20h
0x180004cf6  mov     r11, r8
0x180004cf9  mov     r10, rdx
0x180004cfc  mov     rbx, rcx
0x180004cff  mov     eax, 80004003h
0x180004d04  test    r9, r9
0x180004d07  jz      short loc_180004D3E
0x180004d09  mov     qword ptr [r9], 0
0x180004d10  test    rdx, rdx
0x180004d13  jz      short loc_180004D2C
0x180004d15  mov     rcx, r8; struct _GUID *
0x180004d18  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180004d1d  test    eax, eax
0x180004d1f  jnz     short loc_180004D2C
0x180004d21  mov     eax, 80040110h
0x180004d26  add     rsp, 20h
0x180004d2a  pop     rbx
0x180004d2b  retn
0x180004d2c  mov     rax, [rbx+40h]
0x180004d30  mov     r8, r9
0x180004d33  mov     rdx, r11
0x180004d36  mov     rcx, r10
0x180004d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3e  add     rsp, 20h
0x180004d42  pop     rbx
0x180004d43  retn
```
