# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000a320`
- end: `0x18000a374`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000a320`
- `0x18000a9c4`
- `0x18001c010`

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
0x18000a320  push    rbx
0x18000a322  sub     rsp, 20h
0x18000a326  mov     r11, r8
0x18000a329  mov     r10, rdx
0x18000a32c  mov     rbx, rcx
0x18000a32f  mov     eax, 80004003h
0x18000a334  test    r9, r9
0x18000a337  jz      short loc_18000A36E
0x18000a339  mov     qword ptr [r9], 0
0x18000a340  test    rdx, rdx
0x18000a343  jz      short loc_18000A35C
0x18000a345  mov     rcx, r8; struct _GUID *
0x18000a348  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x18000a34d  test    eax, eax
0x18000a34f  jnz     short loc_18000A35C
0x18000a351  mov     eax, 80040110h
0x18000a356  add     rsp, 20h
0x18000a35a  pop     rbx
0x18000a35b  retn
0x18000a35c  mov     rax, [rbx+40h]
0x18000a360  mov     r8, r9
0x18000a363  mov     rdx, r11
0x18000a366  mov     rcx, r10
0x18000a369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a36e  add     rsp, 20h
0x18000a372  pop     rbx
0x18000a373  retn
```
