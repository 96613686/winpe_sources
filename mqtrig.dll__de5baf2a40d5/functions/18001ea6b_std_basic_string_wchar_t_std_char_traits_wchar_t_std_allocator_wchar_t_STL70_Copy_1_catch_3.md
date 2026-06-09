# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch$3

- ea: `0x18001ea6b`
- end: `0x18001eaf2`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___STL70_::_Copy_::_1_::catch$3`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001ce6`
- `0x180014ae8`
- `0x18001ea6b`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001eab1`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18001eab1`

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
0x18001ea6b  mov     [rsp+arg_8], rdx
0x18001ea70  push    rbp
0x18001ea71  sub     rsp, 20h
0x18001ea75  mov     rbp, rdx
0x18001ea78  mov     rcx, [rbp+98h]
0x18001ea7f  mov     [rbp+98h], rcx
0x18001ea86  add     rcx, 1
0x18001ea8a  jz      short loc_18001EAD2
0x18001ea8c  xor     edx, edx
0x18001ea8e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ea92  div     rcx
0x18001ea95  cmp     rax, 2
0x18001ea99  jnb     short loc_18001EAD2
0x18001ea9b  mov     qword ptr [rbp+98h], 0
0x18001eaa6  lea     rdx, [rbp+98h]
0x18001eaad  lea     rcx, [rbp+38h]
0x18001eab1  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18001eab7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001eabe  mov     [rbp+38h], rax
0x18001eac2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001eac9  lea     rcx, [rbp+38h]; pExceptionObject
0x18001eacd  call    _CxxThrowException_0
0x18001ead2  add     rcx, rcx; unsigned __int64
0x18001ead5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18001eada  mov     [rbp+0A8h], rax
0x18001eae1  mov     rax, 0
0x18001eaeb  add     rsp, 20h
0x18001eaef  pop     rbp
0x18001eaf0  retn
```
