# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180009df3`
- end: `0x180009e3a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001098`
- `0x180001238`
- `0x180009df3`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 104) = v4;
  return 0;
}

```

## disassembly

```asm
0x180009df3  mov     [rsp+arg_8], rdx
0x180009df8  push    rbp
0x180009df9  sub     rsp, 20h
0x180009dfd  mov     rbp, rdx
0x180009e00  mov     rcx, [rbp+58h]
0x180009e04  mov     [rbp+58h], rcx
0x180009e08  xor     eax, eax
0x180009e0a  add     rcx, 1; Size
0x180009e0e  jz      short loc_180009E25
0x180009e10  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009e14  ja      short loc_180009E20
0x180009e16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e1b  test    rax, rax
0x180009e1e  jnz     short loc_180009E25
0x180009e20  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180009e25  mov     [rbp+68h], rax
0x180009e29  mov     rax, 0
0x180009e33  add     rsp, 20h
0x180009e37  pop     rbp
0x180009e38  retn
```
