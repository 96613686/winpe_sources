# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000ae6c`
- end: `0x18000aebf`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001140`
- `0x180001348`
- `0x18000ae6c`

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
0x18000ae6c  mov     [rsp+arg_8], rdx
0x18000ae71  push    rbp
0x18000ae72  sub     rsp, 20h
0x18000ae76  mov     rbp, rdx
0x18000ae79  mov     rcx, [rbp+58h]
0x18000ae7d  mov     [rbp+58h], rcx
0x18000ae81  xor     eax, eax
0x18000ae83  add     rcx, 1
0x18000ae87  jz      short loc_18000AEAA
0x18000ae89  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000ae93  cmp     rcx, rax
0x18000ae96  ja      short loc_18000AEA5
0x18000ae98  add     rcx, rcx; Size
0x18000ae9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aea0  test    rax, rax
0x18000aea3  jnz     short loc_18000AEAA
0x18000aea5  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000aeaa  mov     [rbp+68h], rax
0x18000aeae  mov     rax, 0
0x18000aeb8  add     rsp, 20h
0x18000aebc  pop     rbp
0x18000aebd  retn
```
