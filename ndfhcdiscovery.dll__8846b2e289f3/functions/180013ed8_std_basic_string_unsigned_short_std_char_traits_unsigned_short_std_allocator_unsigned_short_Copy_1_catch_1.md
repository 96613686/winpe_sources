# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180013ed8`
- end: `0x180013f2b`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800012e0`
- `0x180001488`
- `0x180013ed8`

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
0x180013ed8  mov     [rsp+arg_8], rdx
0x180013edd  push    rbp
0x180013ede  sub     rsp, 20h
0x180013ee2  mov     rbp, rdx
0x180013ee5  mov     rcx, [rbp+58h]
0x180013ee9  mov     [rbp+58h], rcx
0x180013eed  xor     eax, eax
0x180013eef  add     rcx, 1
0x180013ef3  jz      short loc_180013F16
0x180013ef5  mov     rax, 7FFFFFFFFFFFFFFFh
0x180013eff  cmp     rcx, rax
0x180013f02  ja      short loc_180013F11
0x180013f04  add     rcx, rcx; Size
0x180013f07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013f0c  test    rax, rax
0x180013f0f  jnz     short loc_180013F16
0x180013f11  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180013f16  mov     [rbp+68h], rax
0x180013f1a  mov     rax, 0
0x180013f24  add     rsp, 20h
0x180013f28  pop     rbp
0x180013f29  retn
```
