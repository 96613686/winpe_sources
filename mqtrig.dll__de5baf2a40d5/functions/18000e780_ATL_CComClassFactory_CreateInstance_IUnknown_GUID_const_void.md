# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000e780`
- end: `0x18000e7d4`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e780`
- `0x18000ed70`
- `0x180022010`

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
0x18000e780  push    rbx
0x18000e782  sub     rsp, 20h
0x18000e786  mov     r11, r8
0x18000e789  mov     r10, rdx
0x18000e78c  mov     rbx, rcx
0x18000e78f  mov     eax, 80004003h
0x18000e794  test    r9, r9
0x18000e797  jz      short loc_18000E7CE
0x18000e799  mov     qword ptr [r9], 0
0x18000e7a0  test    rdx, rdx
0x18000e7a3  jz      short loc_18000E7BC
0x18000e7a5  mov     rcx, r8; struct _GUID *
0x18000e7a8  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000e7ad  test    eax, eax
0x18000e7af  jnz     short loc_18000E7BC
0x18000e7b1  mov     eax, 80040110h
0x18000e7b6  add     rsp, 20h
0x18000e7ba  pop     rbx
0x18000e7bb  retn
0x18000e7bc  mov     rax, [rbx+40h]
0x18000e7c0  mov     r8, r9
0x18000e7c3  mov     rdx, r11
0x18000e7c6  mov     rcx, r10
0x18000e7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7ce  add     rsp, 20h
0x18000e7d2  pop     rbx
0x18000e7d3  retn
```
