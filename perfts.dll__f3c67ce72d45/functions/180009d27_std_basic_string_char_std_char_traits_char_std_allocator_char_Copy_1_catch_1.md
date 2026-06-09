# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180009d27`
- end: `0x180009d6b`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001da8`
- `0x180001f88`
- `0x1800020e8`
- `0x180009d27`

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
  return &loc_180002011;
}

```

## disassembly

```asm
0x180009d27  mov     [rsp+arg_8], rdx
0x180009d2c  push    rbp
0x180009d2d  sub     rsp, 20h
0x180009d31  mov     rbp, rdx
0x180009d34  mov     rcx, [rbp+68h]
0x180009d38  mov     [rbp+68h], rcx
0x180009d3c  xor     eax, eax
0x180009d3e  add     rcx, 1; Size
0x180009d42  jz      short loc_180009D59
0x180009d44  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180009d48  ja      short loc_180009D54
0x180009d4a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d4f  test    rax, rax
0x180009d52  jnz     short loc_180009D59
0x180009d54  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180009d59  mov     [rbp+78h], rax
0x180009d5d  lea     rax, loc_180002011
0x180009d64  add     rsp, 20h
0x180009d68  pop     rbp
0x180009d69  retn
```
