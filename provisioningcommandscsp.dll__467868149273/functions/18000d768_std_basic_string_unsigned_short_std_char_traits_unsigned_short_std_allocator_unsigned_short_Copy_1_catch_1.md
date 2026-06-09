# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000d768`
- end: `0x18000d7c2`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800016b4`
- `0x18000d768`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d7a1`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d7a1`

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
0x18000d768  mov     [rsp+arg_8], rdx
0x18000d76d  push    rbp
0x18000d76e  sub     rsp, 20h
0x18000d772  mov     rbp, rdx
0x18000d775  mov     rcx, [rbp+58h]
0x18000d779  mov     [rbp+58h], rcx
0x18000d77d  xor     eax, eax
0x18000d77f  add     rcx, 1
0x18000d783  jz      short loc_18000D7AD
0x18000d785  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000d78f  cmp     rcx, rax
0x18000d792  ja      short loc_18000D7A1
0x18000d794  add     rcx, rcx; Size
0x18000d797  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d79c  test    rax, rax
0x18000d79f  jnz     short loc_18000D7AD
0x18000d7a1  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000d7a8  nop     dword ptr [rax+rax+00h]
0x18000d7ad  mov     [rbp+68h], rax
0x18000d7b1  mov     rax, 0
0x18000d7bb  add     rsp, 20h
0x18000d7bf  pop     rbp
0x18000d7c0  retn
```
