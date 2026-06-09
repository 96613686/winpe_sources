# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18001387e`
- end: `0x1800138c5`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001404`
- `0x1800015a8`
- `0x18001387e`

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
0x18001387e  mov     [rsp+arg_8], rdx
0x180013883  push    rbp
0x180013884  sub     rsp, 20h
0x180013888  mov     rbp, rdx
0x18001388b  mov     rcx, [rbp+58h]
0x18001388f  mov     [rbp+58h], rcx
0x180013893  xor     eax, eax
0x180013895  add     rcx, 1; Size
0x180013899  jz      short loc_1800138B0
0x18001389b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001389f  ja      short loc_1800138AB
0x1800138a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800138a6  test    rax, rax
0x1800138a9  jnz     short loc_1800138B0
0x1800138ab  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800138b0  mov     [rbp+68h], rax
0x1800138b4  mov     rax, 0
0x1800138be  add     rsp, 20h
0x1800138c2  pop     rbp
0x1800138c3  retn
```
