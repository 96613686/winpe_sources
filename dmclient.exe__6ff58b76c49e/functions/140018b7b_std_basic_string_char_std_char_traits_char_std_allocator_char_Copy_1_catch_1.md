# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x140018b7b`
- end: `0x140018bc2`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002060`
- `0x140002208`
- `0x140018b7b`

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
0x140018b7b  mov     [rsp+arg_8], rdx
0x140018b80  push    rbp
0x140018b81  sub     rsp, 20h
0x140018b85  mov     rbp, rdx
0x140018b88  mov     rcx, [rbp+58h]
0x140018b8c  mov     [rbp+58h], rcx
0x140018b90  xor     eax, eax
0x140018b92  add     rcx, 1; Size
0x140018b96  jz      short loc_140018BAD
0x140018b98  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140018b9c  ja      short loc_140018BA8
0x140018b9e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140018ba3  test    rax, rax
0x140018ba6  jnz     short loc_140018BAD
0x140018ba8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140018bad  mov     [rbp+68h], rax
0x140018bb1  mov     rax, 0
0x140018bbb  add     rsp, 20h
0x140018bbf  pop     rbp
0x140018bc0  retn
```
