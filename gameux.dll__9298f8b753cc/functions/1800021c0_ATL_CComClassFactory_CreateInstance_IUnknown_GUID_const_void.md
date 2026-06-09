# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800021c0`
- end: `0x180002214`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `84`
- prototype: `int(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800021c0`
- `0x18000221c`
- `0x180004010`

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
0x1800021c0  push    rbx
0x1800021c2  sub     rsp, 20h
0x1800021c6  mov     r11, r8
0x1800021c9  mov     r10, rdx
0x1800021cc  mov     rbx, rcx
0x1800021cf  mov     eax, 80004003h
0x1800021d4  test    r9, r9
0x1800021d7  jz      short loc_18000220E
0x1800021d9  mov     qword ptr [r9], 0
0x1800021e0  test    rdx, rdx
0x1800021e3  jz      short loc_1800021FC
0x1800021e5  mov     rcx, r8; struct _GUID *
0x1800021e8  call    ?InlineIsEqualUnknown@ATL@@YAHAEBU_GUID@@@Z; ATL::InlineIsEqualUnknown(_GUID const &)
0x1800021ed  test    eax, eax
0x1800021ef  jnz     short loc_1800021FC
0x1800021f1  mov     eax, 80040110h
0x1800021f6  add     rsp, 20h
0x1800021fa  pop     rbx
0x1800021fb  retn
0x1800021fc  mov     rax, [rbx+40h]
0x180002200  mov     r8, r9
0x180002203  mov     rdx, r11
0x180002206  mov     rcx, r10
0x180002209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000220e  add     rsp, 20h
0x180002212  pop     rbx
0x180002213  retn
```
