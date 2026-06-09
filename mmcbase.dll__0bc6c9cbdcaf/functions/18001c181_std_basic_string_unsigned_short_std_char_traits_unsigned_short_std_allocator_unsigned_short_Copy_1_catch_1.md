# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18001c181`
- end: `0x18001c1d5`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009928`
- `0x18001c181`

## import_xrefs

- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x18001c1b0`
- `MFC42u!__imp_??2@YAPEAX_K@Z` at `0x18001c1b0`

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
0x18001c181  mov     [rsp+arg_8], rdx
0x18001c186  push    rbp
0x18001c187  sub     rsp, 20h
0x18001c18b  mov     rbp, rdx
0x18001c18e  mov     rcx, [rbp+58h]
0x18001c192  mov     [rbp+58h], rcx
0x18001c196  xor     eax, eax
0x18001c198  add     rcx, 1
0x18001c19c  jz      short loc_18001C1C0
0x18001c19e  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001c1a8  cmp     rcx, rax
0x18001c1ab  ja      short loc_18001C1BB
0x18001c1ad  add     rcx, rcx
0x18001c1b0  call    cs:__imp_??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c1b6  test    rax, rax
0x18001c1b9  jnz     short loc_18001C1C0
0x18001c1bb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001c1c0  mov     [rbp+68h], rax
0x18001c1c4  mov     rax, 0
0x18001c1ce  add     rsp, 20h
0x18001c1d2  pop     rbp
0x18001c1d3  retn
```
