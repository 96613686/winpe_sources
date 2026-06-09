# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch$3

- ea: `0x14001d30d`
- end: `0x14001d394`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch$3`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001cc6`
- `0x14000ed18`
- `0x14001d30d`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x14001d353`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x14001d353`

## pseudocode

```c
__int64 __fastcall std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  unsigned __int64 v4; // rcx

  v3 = *(_QWORD *)(a2 + 152);
  *(_QWORD *)(a2 + 152) = v3;
  v4 = v3 + 1;
  if ( v4 && 0xFFFFFFFFFFFFFFFFuLL / v4 < 2 )
  {
    *(_QWORD *)(a2 + 152) = 0;
    exception::exception((exception *)(a2 + 56), (const char *const *)(a2 + 152));
    *(_QWORD *)(a2 + 56) = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)(a2 + 56);
  }
  *(_QWORD *)(a2 + 168) = MmAllocate(2 * v4);
  return 0;
}

```

## disassembly

```asm
0x14001d30d  mov     [rsp+arg_8], rdx
0x14001d312  push    rbp
0x14001d313  sub     rsp, 20h
0x14001d317  mov     rbp, rdx
0x14001d31a  mov     rcx, [rbp+98h]
0x14001d321  mov     [rbp+98h], rcx
0x14001d328  add     rcx, 1
0x14001d32c  jz      short loc_14001D374
0x14001d32e  xor     edx, edx
0x14001d330  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001d334  div     rcx
0x14001d337  cmp     rax, 2
0x14001d33b  jnb     short loc_14001D374
0x14001d33d  mov     qword ptr [rbp+98h], 0
0x14001d348  lea     rdx, [rbp+98h]
0x14001d34f  lea     rcx, [rbp+38h]
0x14001d353  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x14001d359  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x14001d360  mov     [rbp+38h], rax
0x14001d364  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14001d36b  lea     rcx, [rbp+38h]; pExceptionObject
0x14001d36f  call    _CxxThrowException_0
0x14001d374  add     rcx, rcx; unsigned __int64
0x14001d377  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x14001d37c  mov     [rbp+0A8h], rax
0x14001d383  mov     rax, 0
0x14001d38d  add     rsp, 20h
0x14001d391  pop     rbp
0x14001d392  retn
```
