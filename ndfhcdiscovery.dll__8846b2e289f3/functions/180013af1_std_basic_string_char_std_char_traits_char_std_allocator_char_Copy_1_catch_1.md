# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x180013af1`
- end: `0x180013b38`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800012e0`
- `0x180001488`
- `0x180013af1`

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
0x180013af1  mov     [rsp+arg_8], rdx
0x180013af6  push    rbp
0x180013af7  sub     rsp, 20h
0x180013afb  mov     rbp, rdx
0x180013afe  mov     rcx, [rbp+58h]
0x180013b02  mov     [rbp+58h], rcx
0x180013b06  xor     eax, eax
0x180013b08  add     rcx, 1; Size
0x180013b0c  jz      short loc_180013B23
0x180013b0e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013b12  ja      short loc_180013B1E
0x180013b14  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013b19  test    rax, rax
0x180013b1c  jnz     short loc_180013B23
0x180013b1e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180013b23  mov     [rbp+68h], rax
0x180013b27  mov     rax, 0
0x180013b31  add     rsp, 20h
0x180013b35  pop     rbp
0x180013b36  retn
```
