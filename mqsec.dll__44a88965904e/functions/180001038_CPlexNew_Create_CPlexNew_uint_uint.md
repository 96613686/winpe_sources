# CPlexNew::Create(CPlexNew * &,uint,uint)

- ea: `0x180001038`
- end: `0x1800010ad`
- name: `?Create@CPlexNew@@SAPEAU1@AEAPEAU1@II@Z`
- size: `117`
- prototype: `struct CPlexNew *__fastcall(struct CPlexNew **, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e008`
- `0x180015780`

## callees

- `0x180001038`
- `0x180003426`
- `0x18001722c`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180001089`
- `msvcrt!??0exception@@QEAA@AEBQEBDH@Z` at `0x180001089`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct CPlexNew *__fastcall CPlexNew::Create(struct CPlexNew **a1, unsigned int a2)
{
  unsigned __int64 v3; // rax
  struct CPlexNew *result; // rax
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  v3 = 32LL * a2;
  if ( !is_mul_ok(a2, 0x20u) || v3 >= 0xFFFFFFFFFFFFFFF0uLL )
  {
    exception::exception((exception *)pExceptionObject, &std::_bad_alloc_Message, 1);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  result = (struct CPlexNew *)MmAllocate(v3 + 16);
  *(_QWORD *)result = *a1;
  *a1 = result;
  return result;
}

```

## disassembly

```asm
0x180001038  push    rbx
0x18000103a  sub     rsp, 40h
0x18000103e  mov     rbx, rcx
0x180001041  mov     [rsp+48h+arg_18], 0
0x18000104a  mov     edx, edx
0x18000104c  mov     eax, 20h ; ' '
0x180001051  mul     rdx
0x180001054  test    rdx, rdx
0x180001057  jnz     short loc_180001077
0x180001059  lea     rcx, [rax+10h]; unsigned __int64
0x18000105d  cmp     rcx, 10h
0x180001061  jb      short loc_180001077
0x180001063  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180001068  mov     rcx, [rbx]
0x18000106b  mov     [rax], rcx
0x18000106e  mov     [rbx], rax
0x180001071  add     rsp, 40h
0x180001075  pop     rbx
0x180001076  retn
0x180001077  mov     r8d, 1
0x18000107d  lea     rdx, ?_bad_alloc_Message@std@@3PEBDEB; char const * const std::_bad_alloc_Message
0x180001084  lea     rcx, [rsp+48h+pExceptionObject]
0x180001089  call    cs:__imp_??0exception@@QEAA@AEBQEBDH@Z; exception::exception(char const * const &,int)
0x18000108f  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001096  mov     [rsp+48h+pExceptionObject], rax
0x18000109b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800010a2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800010a7  call    _CxxThrowException_0
```
