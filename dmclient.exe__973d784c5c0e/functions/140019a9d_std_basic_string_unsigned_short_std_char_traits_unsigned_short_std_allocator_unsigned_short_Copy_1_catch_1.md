# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x140019a9d`
- end: `0x140019af0`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140002084`
- `0x140002228`
- `0x140019a9d`

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
0x140019a9d  mov     [rsp+arg_8], rdx
0x140019aa2  push    rbp
0x140019aa3  sub     rsp, 20h
0x140019aa7  mov     rbp, rdx
0x140019aaa  mov     rcx, [rbp+58h]
0x140019aae  mov     [rbp+58h], rcx
0x140019ab2  xor     eax, eax
0x140019ab4  add     rcx, 1
0x140019ab8  jz      short loc_140019ADB
0x140019aba  mov     rax, 7FFFFFFFFFFFFFFFh
0x140019ac4  cmp     rcx, rax
0x140019ac7  ja      short loc_140019AD6
0x140019ac9  add     rcx, rcx; Size
0x140019acc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140019ad1  test    rax, rax
0x140019ad4  jnz     short loc_140019ADB
0x140019ad6  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140019adb  mov     [rbp+68h], rax
0x140019adf  mov     rax, 0
0x140019ae9  add     rsp, 20h
0x140019aed  pop     rbp
0x140019aee  retn
```
