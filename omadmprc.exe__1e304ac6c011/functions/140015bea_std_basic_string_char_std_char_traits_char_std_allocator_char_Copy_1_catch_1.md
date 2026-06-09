# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x140015bea`
- end: `0x140015c31`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001c34`
- `0x140001e38`
- `0x140015bea`

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
0x140015bea  mov     [rsp+arg_8], rdx
0x140015bef  push    rbp
0x140015bf0  sub     rsp, 20h
0x140015bf4  mov     rbp, rdx
0x140015bf7  mov     rcx, [rbp+58h]
0x140015bfb  mov     [rbp+58h], rcx
0x140015bff  xor     eax, eax
0x140015c01  add     rcx, 1; Size
0x140015c05  jz      short loc_140015C1C
0x140015c07  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140015c0b  ja      short loc_140015C17
0x140015c0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015c12  test    rax, rax
0x140015c15  jnz     short loc_140015C1C
0x140015c17  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140015c1c  mov     [rbp+68h], rax
0x140015c20  mov     rax, 0
0x140015c2a  add     rsp, 20h
0x140015c2e  pop     rbp
0x140015c2f  retn
```
