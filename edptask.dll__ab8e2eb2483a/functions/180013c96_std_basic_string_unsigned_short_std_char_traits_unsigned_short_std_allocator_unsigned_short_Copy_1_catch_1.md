# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x180013c96`
- end: `0x180013ce9`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180013c96`

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
0x180013c96  mov     [rsp+arg_8], rdx
0x180013c9b  push    rbp
0x180013c9c  sub     rsp, 20h
0x180013ca0  mov     rbp, rdx
0x180013ca3  mov     rcx, [rbp+58h]
0x180013ca7  mov     [rbp+58h], rcx
0x180013cab  xor     eax, eax
0x180013cad  add     rcx, 1
0x180013cb1  jz      short loc_180013CD4
0x180013cb3  mov     rax, 7FFFFFFFFFFFFFFFh
0x180013cbd  cmp     rcx, rax
0x180013cc0  ja      short loc_180013CCF
0x180013cc2  add     rcx, rcx; Size
0x180013cc5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013cca  test    rax, rax
0x180013ccd  jnz     short loc_180013CD4
0x180013ccf  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180013cd4  mov     [rbp+68h], rax
0x180013cd8  mov     rax, 0
0x180013ce2  add     rsp, 20h
0x180013ce6  pop     rbp
0x180013ce7  retn
```
