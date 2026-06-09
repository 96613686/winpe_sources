# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a090`
- end: `0x18000a0e4`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `int(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003488`
- `0x18000a090`
- `0x18000d010`

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
0x18000a090  push    rbx
0x18000a092  sub     rsp, 20h
0x18000a096  mov     r11, r8
0x18000a099  mov     r10, rdx
0x18000a09c  mov     rbx, rcx
0x18000a09f  mov     eax, 80004003h
0x18000a0a4  test    r9, r9
0x18000a0a7  jz      short loc_18000A0DE
0x18000a0a9  mov     qword ptr [r9], 0
0x18000a0b0  test    rdx, rdx
0x18000a0b3  jz      short loc_18000A0CC
0x18000a0b5  mov     rcx, r8; struct _GUID *
0x18000a0b8  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000a0bd  test    eax, eax
0x18000a0bf  jnz     short loc_18000A0CC
0x18000a0c1  mov     eax, 80040110h
0x18000a0c6  add     rsp, 20h
0x18000a0ca  pop     rbx
0x18000a0cb  retn
0x18000a0cc  mov     rax, [rbx+40h]
0x18000a0d0  mov     r8, r9
0x18000a0d3  mov     rdx, r11
0x18000a0d6  mov     rcx, r10
0x18000a0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0de  add     rsp, 20h
0x18000a0e2  pop     rbx
0x18000a0e3  retn
```
