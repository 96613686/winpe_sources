# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x140015fa6`
- end: `0x140015ff9`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001c34`
- `0x140001e38`
- `0x140015fa6`

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
0x140015fa6  mov     [rsp+arg_8], rdx
0x140015fab  push    rbp
0x140015fac  sub     rsp, 20h
0x140015fb0  mov     rbp, rdx
0x140015fb3  mov     rcx, [rbp+58h]
0x140015fb7  mov     [rbp+58h], rcx
0x140015fbb  xor     eax, eax
0x140015fbd  add     rcx, 1
0x140015fc1  jz      short loc_140015FE4
0x140015fc3  mov     rax, 7FFFFFFFFFFFFFFFh
0x140015fcd  cmp     rcx, rax
0x140015fd0  ja      short loc_140015FDF
0x140015fd2  add     rcx, rcx; Size
0x140015fd5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140015fda  test    rax, rax
0x140015fdd  jnz     short loc_140015FE4
0x140015fdf  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140015fe4  mov     [rbp+68h], rax
0x140015fe8  mov     rax, 0
0x140015ff2  add     rsp, 20h
0x140015ff6  pop     rbp
0x140015ff7  retn
```
