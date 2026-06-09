# _std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_static_wchar_t___STL70_::_Copy_::_1_::catch$3

- ea: `0x18002fc24`
- end: `0x18002fcab`
- name: `_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_static_wchar_t___STL70_::_Copy_::_1_::catch$3`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003426`
- `0x18001722c`
- `0x18002fc24`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002fc6a`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18002fc6a`

## pseudocode

```c
__int64 __fastcall std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_static_wchar_t___STL70_::_Copy_::_1_::catch_3(
        __int64 a1,
        unsigned __int64 a2,
        int a3)
{
  unsigned __int64 v3; // rbp
  __int64 v4; // rcx
  unsigned __int64 v5; // rcx

  v3 = a2;
  v4 = *(_QWORD *)(a2 + 152);
  *(_QWORD *)(a2 + 152) = v4;
  v5 = v4 + 1;
  if ( v5 )
  {
    a2 = 0xFFFFFFFFFFFFFFFFuLL % v5;
    if ( 0xFFFFFFFFFFFFFFFFuLL / v5 < 2 )
    {
      *(_QWORD *)(v3 + 152) = 0;
      exception::exception((exception *)(v3 + 56), (const char *const *)(v3 + 152));
      *(_QWORD *)(v3 + 56) = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)(v3 + 56);
    }
  }
  *(_QWORD *)(v3 + 168) = MmAllocate(2 * v5, (const char *)a2, a3);
  return 0;
}

```

## disassembly

```asm
0x18002fc24  mov     [rsp+arg_8], rdx
0x18002fc29  push    rbp
0x18002fc2a  sub     rsp, 20h
0x18002fc2e  mov     rbp, rdx
0x18002fc31  mov     rcx, [rbp+98h]
0x18002fc38  mov     [rbp+98h], rcx
0x18002fc3f  add     rcx, 1
0x18002fc43  jz      short loc_18002FC8B
0x18002fc45  xor     edx, edx
0x18002fc47  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fc4b  div     rcx
0x18002fc4e  cmp     rax, 2
0x18002fc52  jnb     short loc_18002FC8B
0x18002fc54  mov     qword ptr [rbp+98h], 0
0x18002fc5f  lea     rdx, [rbp+98h]
0x18002fc66  lea     rcx, [rbp+38h]
0x18002fc6a  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18002fc70  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18002fc77  mov     [rbp+38h], rax
0x18002fc7b  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18002fc82  lea     rcx, [rbp+38h]; pExceptionObject
0x18002fc86  call    _CxxThrowException_0
0x18002fc8b  add     rcx, rcx; unsigned __int64
0x18002fc8e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002fc93  mov     [rbp+0A8h], rax
0x18002fc9a  mov     rax, 0
0x18002fca4  add     rsp, 20h
0x18002fca8  pop     rbp
0x18002fca9  retn
```
