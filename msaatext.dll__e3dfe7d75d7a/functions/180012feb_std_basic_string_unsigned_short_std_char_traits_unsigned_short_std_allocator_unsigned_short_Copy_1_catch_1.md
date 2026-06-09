# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180012feb`
- end: `0x18001303e`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001370`
- `0x180001518`
- `0x180012feb`

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
0x180012feb  mov     [rsp+arg_8], rdx
0x180012ff0  push    rbp
0x180012ff1  sub     rsp, 20h
0x180012ff5  mov     rbp, rdx
0x180012ff8  mov     rcx, [rbp+58h]
0x180012ffc  mov     [rbp+58h], rcx
0x180013000  xor     eax, eax
0x180013002  add     rcx, 1
0x180013006  jz      short loc_180013029
0x180013008  mov     rax, 7FFFFFFFFFFFFFFFh
0x180013012  cmp     rcx, rax
0x180013015  ja      short loc_180013024
0x180013017  add     rcx, rcx; Size
0x18001301a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001301f  test    rax, rax
0x180013022  jnz     short loc_180013029
0x180013024  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180013029  mov     [rbp+68h], rax
0x18001302d  mov     rax, 0
0x180013037  add     rsp, 20h
0x18001303b  pop     rbp
0x18001303c  retn
```
