# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1

- ea: `0x18000d0a2`
- end: `0x18000d0f6`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$1`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800016a4`
- `0x18000d0a2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d0db`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000d0db`

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
0x18000d0a2  mov     [rsp+arg_8], rdx
0x18000d0a7  push    rbp
0x18000d0a8  sub     rsp, 20h
0x18000d0ac  mov     rbp, rdx
0x18000d0af  mov     rcx, [rbp+58h]
0x18000d0b3  mov     [rbp+58h], rcx
0x18000d0b7  xor     eax, eax
0x18000d0b9  add     rcx, 1
0x18000d0bd  jz      short loc_18000D0E1
0x18000d0bf  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000d0c9  cmp     rcx, rax
0x18000d0cc  ja      short loc_18000D0DB
0x18000d0ce  add     rcx, rcx; Size
0x18000d0d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d0d6  test    rax, rax
0x18000d0d9  jnz     short loc_18000D0E1
0x18000d0db  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000d0e1  mov     [rbp+68h], rax
0x18000d0e5  mov     rax, 0
0x18000d0ef  add     rsp, 20h
0x18000d0f3  pop     rbp
0x18000d0f4  retn
```
