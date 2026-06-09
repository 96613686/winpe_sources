# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000d4d2`
- end: `0x18000d520`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800016b4`
- `0x18000d4d2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d4ff`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d4ff`

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
0x18000d4d2  mov     [rsp+arg_8], rdx
0x18000d4d7  push    rbp
0x18000d4d8  sub     rsp, 20h
0x18000d4dc  mov     rbp, rdx
0x18000d4df  mov     rcx, [rbp+58h]
0x18000d4e3  mov     [rbp+58h], rcx
0x18000d4e7  xor     eax, eax
0x18000d4e9  add     rcx, 1; Size
0x18000d4ed  jz      short loc_18000D50B
0x18000d4ef  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000d4f3  ja      short loc_18000D4FF
0x18000d4f5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d4fa  test    rax, rax
0x18000d4fd  jnz     short loc_18000D50B
0x18000d4ff  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000d506  nop     dword ptr [rax+rax+00h]
0x18000d50b  mov     [rbp+68h], rax
0x18000d50f  mov     rax, 0
0x18000d519  add     rsp, 20h
0x18000d51d  pop     rbp
0x18000d51e  retn
```
