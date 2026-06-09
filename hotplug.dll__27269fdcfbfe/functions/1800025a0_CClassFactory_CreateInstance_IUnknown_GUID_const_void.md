# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x1800025a0`
- end: `0x1800025cc`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `44`
- prototype: `__int64 __fastcall(__int64 (__fastcall **this)(const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800025a0`
- `0x180009010`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        __int64 (__fastcall **this)(const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 result; // rax

  *a4 = 0;
  result = 2147746064LL;
  if ( !a2 )
    return this[2](a3, a4);
  return result;
}

```

## disassembly

```asm
0x1800025a0  sub     rsp, 28h
0x1800025a4  mov     qword ptr [r9], 0
0x1800025ab  mov     r10, rcx
0x1800025ae  mov     eax, 80040110h
0x1800025b3  test    rdx, rdx
0x1800025b6  jnz     short loc_1800025C7
0x1800025b8  mov     rax, [r10+10h]
0x1800025bc  mov     rdx, r9
0x1800025bf  mov     rcx, r8
0x1800025c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c7  add     rsp, 28h
0x1800025cb  retn
```
