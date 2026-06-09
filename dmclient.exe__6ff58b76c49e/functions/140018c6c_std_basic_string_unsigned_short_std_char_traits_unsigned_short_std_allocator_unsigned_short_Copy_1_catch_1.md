# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x140018c6c`
- end: `0x140018cbf`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002060`
- `0x140002208`
- `0x140018c6c`

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
0x140018c6c  mov     [rsp+arg_8], rdx
0x140018c71  push    rbp
0x140018c72  sub     rsp, 20h
0x140018c76  mov     rbp, rdx
0x140018c79  mov     rcx, [rbp+58h]
0x140018c7d  mov     [rbp+58h], rcx
0x140018c81  xor     eax, eax
0x140018c83  add     rcx, 1
0x140018c87  jz      short loc_140018CAA
0x140018c89  mov     rax, 7FFFFFFFFFFFFFFFh
0x140018c93  cmp     rcx, rax
0x140018c96  ja      short loc_140018CA5
0x140018c98  add     rcx, rcx; Size
0x140018c9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018ca0  test    rax, rax
0x140018ca3  jnz     short loc_140018CAA
0x140018ca5  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140018caa  mov     [rbp+68h], rax
0x140018cae  mov     rax, 0
0x140018cb8  add     rsp, 20h
0x140018cbc  pop     rbp
0x140018cbd  retn
```
