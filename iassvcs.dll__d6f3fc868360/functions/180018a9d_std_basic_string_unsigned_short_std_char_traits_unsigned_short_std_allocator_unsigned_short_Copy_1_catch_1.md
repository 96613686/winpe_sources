# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180018a9d`
- end: `0x180018af0`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001238`
- `0x18000d98c`
- `0x180018a9d`

## pseudocode

```c
__int64 __fastcall std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  unsigned __int64 v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    if ( v5 > 0x7FFFFFFFFFFFFFFFLL || (v4 = operator new(2 * v5)) == 0 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x180018a9d  mov     [rsp+arg_8], rdx
0x180018aa2  push    rbp
0x180018aa3  sub     rsp, 20h
0x180018aa7  mov     rbp, rdx
0x180018aaa  mov     rcx, [rbp+58h]
0x180018aae  mov     [rbp+58h], rcx
0x180018ab2  xor     eax, eax
0x180018ab4  add     rcx, 1
0x180018ab8  jz      short loc_180018ADB
0x180018aba  mov     rax, 7FFFFFFFFFFFFFFFh
0x180018ac4  cmp     rcx, rax
0x180018ac7  ja      short loc_180018AD6
0x180018ac9  add     rcx, rcx; Size
0x180018acc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018ad1  test    rax, rax
0x180018ad4  jnz     short loc_180018ADB
0x180018ad6  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018adb  mov     [rbp+68h], rax
0x180018adf  mov     rax, 0
0x180018ae9  add     rsp, 20h
0x180018aed  pop     rbp
0x180018aee  retn
```
