# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180012f73`
- end: `0x180012fba`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001370`
- `0x180001518`
- `0x180012f73`

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
0x180012f73  mov     [rsp+arg_8], rdx
0x180012f78  push    rbp
0x180012f79  sub     rsp, 20h
0x180012f7d  mov     rbp, rdx
0x180012f80  mov     rcx, [rbp+58h]
0x180012f84  mov     [rbp+58h], rcx
0x180012f88  xor     eax, eax
0x180012f8a  add     rcx, 1; Size
0x180012f8e  jz      short loc_180012FA5
0x180012f90  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180012f94  ja      short loc_180012FA0
0x180012f96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012f9b  test    rax, rax
0x180012f9e  jnz     short loc_180012FA5
0x180012fa0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180012fa5  mov     [rbp+68h], rax
0x180012fa9  mov     rax, 0
0x180012fb3  add     rsp, 20h
0x180012fb7  pop     rbp
0x180012fb8  retn
```
