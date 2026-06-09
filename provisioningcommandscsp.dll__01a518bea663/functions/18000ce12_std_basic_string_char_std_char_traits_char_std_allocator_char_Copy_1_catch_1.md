# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x18000ce12`
- end: `0x18000ce5a`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `72`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800016a4`
- `0x18000ce12`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000ce3f`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000ce3f`

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
0x18000ce12  mov     [rsp+arg_8], rdx
0x18000ce17  push    rbp
0x18000ce18  sub     rsp, 20h
0x18000ce1c  mov     rbp, rdx
0x18000ce1f  mov     rcx, [rbp+58h]
0x18000ce23  mov     [rbp+58h], rcx
0x18000ce27  xor     eax, eax
0x18000ce29  add     rcx, 1; Size
0x18000ce2d  jz      short loc_18000CE45
0x18000ce2f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000ce33  ja      short loc_18000CE3F
0x18000ce35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ce3a  test    rax, rax
0x18000ce3d  jnz     short loc_18000CE45
0x18000ce3f  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000ce45  mov     [rbp+68h], rax
0x18000ce49  mov     rax, 0
0x18000ce53  add     rsp, 20h
0x18000ce57  pop     rbp
0x18000ce58  retn
```
