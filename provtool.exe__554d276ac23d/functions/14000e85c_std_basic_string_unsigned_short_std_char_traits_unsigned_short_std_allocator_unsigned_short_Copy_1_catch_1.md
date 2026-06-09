# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x14000e85c`
- end: `0x14000e8b0`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001674`
- `0x14000e85c`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000e895`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000e895`

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
0x14000e85c  mov     [rsp+arg_8], rdx
0x14000e861  push    rbp
0x14000e862  sub     rsp, 20h
0x14000e866  mov     rbp, rdx
0x14000e869  mov     rcx, [rbp+58h]
0x14000e86d  mov     [rbp+58h], rcx
0x14000e871  xor     eax, eax
0x14000e873  add     rcx, 1
0x14000e877  jz      short loc_14000E89B
0x14000e879  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000e883  cmp     rcx, rax
0x14000e886  ja      short loc_14000E895
0x14000e888  add     rcx, rcx; Size
0x14000e88b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e890  test    rax, rax
0x14000e893  jnz     short loc_14000E89B
0x14000e895  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000e89b  mov     [rbp+68h], rax
0x14000e89f  mov     rax, 0
0x14000e8a9  add     rsp, 20h
0x14000e8ad  pop     rbp
0x14000e8ae  retn
```
