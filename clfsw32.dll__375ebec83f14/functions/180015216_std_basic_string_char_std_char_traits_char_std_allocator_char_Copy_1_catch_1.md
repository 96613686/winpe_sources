# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180015216`
- end: `0x18001525a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001cec`
- `0x180001ec8`
- `0x180002028`
- `0x180015216`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void *__fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx
  void *v4; // rax
  size_t v5; // rcx

  v3 = *(_QWORD *)(a2 + 104);
  *(_QWORD *)(a2 + 104) = v3;
  v4 = 0;
  v5 = v3 + 1;
  if ( v5 )
  {
    v4 = operator new(v5);
    if ( !v4 )
      std::_Xbad_alloc();
  }
  *(_QWORD *)(a2 + 120) = v4;
  return &loc_180001F51;
}

```

## disassembly

```asm
0x180015216  mov     [rsp+arg_8], rdx
0x18001521b  push    rbp
0x18001521c  sub     rsp, 20h
0x180015220  mov     rbp, rdx
0x180015223  mov     rcx, [rbp+68h]
0x180015227  mov     [rbp+68h], rcx
0x18001522b  xor     eax, eax
0x18001522d  add     rcx, 1; Size
0x180015231  jz      short loc_180015248
0x180015233  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180015237  ja      short loc_180015243
0x180015239  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001523e  test    rax, rax
0x180015241  jnz     short loc_180015248
0x180015243  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180015248  mov     [rbp+78h], rax
0x18001524c  lea     rax, loc_180001F51
0x180015253  add     rsp, 20h
0x180015257  pop     rbp
0x180015258  retn
```
