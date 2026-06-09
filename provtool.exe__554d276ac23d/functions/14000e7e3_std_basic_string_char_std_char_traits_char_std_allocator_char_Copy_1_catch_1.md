# _std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1

- ea: `0x14000e7e3`
- end: `0x14000e82b`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___::_Copy_::_1_::catch$1`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140001674`
- `0x14000e7e3`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000e810`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x14000e810`

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
0x14000e7e3  mov     [rsp+arg_8], rdx
0x14000e7e8  push    rbp
0x14000e7e9  sub     rsp, 20h
0x14000e7ed  mov     rbp, rdx
0x14000e7f0  mov     rcx, [rbp+58h]
0x14000e7f4  mov     [rbp+58h], rcx
0x14000e7f8  xor     eax, eax
0x14000e7fa  add     rcx, 1; Size
0x14000e7fe  jz      short loc_14000E816
0x14000e800  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e804  ja      short loc_14000E810
0x14000e806  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e80b  test    rax, rax
0x14000e80e  jnz     short loc_14000E816
0x14000e810  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000e816  mov     [rbp+68h], rax
0x14000e81a  mov     rax, 0
0x14000e824  add     rsp, 20h
0x14000e828  pop     rbp
0x14000e829  retn
```
