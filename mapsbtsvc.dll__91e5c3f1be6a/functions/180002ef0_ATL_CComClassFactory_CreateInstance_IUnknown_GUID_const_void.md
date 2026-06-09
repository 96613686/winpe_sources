# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002ef0`
- end: `0x180002f44`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002ef0`
- `0x180003064`
- `0x180015010`

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
0x180002ef0  push    rbx
0x180002ef2  sub     rsp, 20h
0x180002ef6  mov     r11, r8
0x180002ef9  mov     r10, rdx
0x180002efc  mov     rbx, rcx
0x180002eff  mov     eax, 80004003h
0x180002f04  test    r9, r9
0x180002f07  jz      short loc_180002F3E
0x180002f09  mov     qword ptr [r9], 0
0x180002f10  test    rdx, rdx
0x180002f13  jz      short loc_180002F2C
0x180002f15  mov     rcx, r8; struct _GUID *
0x180002f18  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x180002f1d  test    eax, eax
0x180002f1f  jnz     short loc_180002F2C
0x180002f21  mov     eax, 80040110h
0x180002f26  add     rsp, 20h
0x180002f2a  pop     rbx
0x180002f2b  retn
0x180002f2c  mov     rax, [rbx+40h]
0x180002f30  mov     r8, r9
0x180002f33  mov     rdx, r11
0x180002f36  mov     rcx, r10
0x180002f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f3e  add     rsp, 20h
0x180002f42  pop     rbx
0x180002f43  retn
```
