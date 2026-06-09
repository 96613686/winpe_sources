# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180009f4f`
- end: `0x180009fa2`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001098`
- `0x180001238`
- `0x180009f4f`

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
0x180009f4f  mov     [rsp+arg_8], rdx
0x180009f54  push    rbp
0x180009f55  sub     rsp, 20h
0x180009f59  mov     rbp, rdx
0x180009f5c  mov     rcx, [rbp+58h]
0x180009f60  mov     [rbp+58h], rcx
0x180009f64  xor     eax, eax
0x180009f66  add     rcx, 1
0x180009f6a  jz      short loc_180009F8D
0x180009f6c  mov     rax, 7FFFFFFFFFFFFFFFh
0x180009f76  cmp     rcx, rax
0x180009f79  ja      short loc_180009F88
0x180009f7b  add     rcx, rcx; Size
0x180009f7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009f83  test    rax, rax
0x180009f86  jnz     short loc_180009F8D
0x180009f88  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180009f8d  mov     [rbp+68h], rax
0x180009f91  mov     rax, 0
0x180009f9b  add     rsp, 20h
0x180009f9f  pop     rbp
0x180009fa0  retn
```
