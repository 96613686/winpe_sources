# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x1400199ac`
- end: `0x1400199f3`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002084`
- `0x140002228`
- `0x1400199ac`

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
0x1400199ac  mov     [rsp+arg_8], rdx
0x1400199b1  push    rbp
0x1400199b2  sub     rsp, 20h
0x1400199b6  mov     rbp, rdx
0x1400199b9  mov     rcx, [rbp+58h]
0x1400199bd  mov     [rbp+58h], rcx
0x1400199c1  xor     eax, eax
0x1400199c3  add     rcx, 1; Size
0x1400199c7  jz      short loc_1400199DE
0x1400199c9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400199cd  ja      short loc_1400199D9
0x1400199cf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400199d4  test    rax, rax
0x1400199d7  jnz     short loc_1400199DE
0x1400199d9  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1400199de  mov     [rbp+68h], rax
0x1400199e2  mov     rax, 0
0x1400199ec  add     rsp, 20h
0x1400199f0  pop     rbp
0x1400199f1  retn
```
