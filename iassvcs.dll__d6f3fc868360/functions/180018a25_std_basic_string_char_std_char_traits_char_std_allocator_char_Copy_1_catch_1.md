# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180018a25`
- end: `0x180018a6c`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001238`
- `0x18000d98c`
- `0x180018a25`

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
0x180018a25  mov     [rsp+arg_8], rdx
0x180018a2a  push    rbp
0x180018a2b  sub     rsp, 20h
0x180018a2f  mov     rbp, rdx
0x180018a32  mov     rcx, [rbp+58h]
0x180018a36  mov     [rbp+58h], rcx
0x180018a3a  xor     eax, eax
0x180018a3c  add     rcx, 1; Size
0x180018a40  jz      short loc_180018A57
0x180018a42  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180018a46  ja      short loc_180018A52
0x180018a48  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018a4d  test    rax, rax
0x180018a50  jnz     short loc_180018A57
0x180018a52  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180018a57  mov     [rbp+68h], rax
0x180018a5b  mov     rax, 0
0x180018a65  add     rsp, 20h
0x180018a69  pop     rbp
0x180018a6a  retn
```
