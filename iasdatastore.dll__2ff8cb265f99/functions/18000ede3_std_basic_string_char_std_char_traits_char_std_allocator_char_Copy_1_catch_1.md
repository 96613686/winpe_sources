# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000ede3`
- end: `0x18000ee2a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180002028`
- `0x180002310`
- `0x18000ede3`

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
0x18000ede3  mov     [rsp+arg_8], rdx
0x18000ede8  push    rbp
0x18000ede9  sub     rsp, 20h
0x18000eded  mov     rbp, rdx
0x18000edf0  mov     rcx, [rbp+58h]
0x18000edf4  mov     [rbp+58h], rcx
0x18000edf8  xor     eax, eax
0x18000edfa  add     rcx, 1; Size
0x18000edfe  jz      short loc_18000EE15
0x18000ee00  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ee04  ja      short loc_18000EE10
0x18000ee06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ee0b  test    rax, rax
0x18000ee0e  jnz     short loc_18000EE15
0x18000ee10  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000ee15  mov     [rbp+68h], rax
0x18000ee19  mov     rax, 0
0x18000ee23  add     rsp, 20h
0x18000ee27  pop     rbp
0x18000ee28  retn
```
