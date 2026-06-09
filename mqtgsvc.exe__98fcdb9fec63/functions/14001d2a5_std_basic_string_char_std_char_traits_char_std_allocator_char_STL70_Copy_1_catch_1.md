# _std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$1

- ea: `0x14001d2a5`
- end: `0x14001d2d9`
- name: `_std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch$1`
- size: `52`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003958`

## pseudocode

```c
__int64 __fastcall std::basic_string_char_std::char_traits_char__std::allocator_char___STL70_::_Copy_::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a2 + 88);
  *(_QWORD *)(a2 + 88) = v2;
  *(_QWORD *)(a2 + 104) = std::_Allocate<char>(v2 + 1, 0);
  return 0;
}

```

## disassembly

```asm
0x14001d2a5  mov     [rsp+arg_8], rdx
0x14001d2aa  push    rbp
0x14001d2ab  sub     rsp, 20h
0x14001d2af  mov     rbp, rdx
0x14001d2b2  mov     rcx, [rbp+58h]
0x14001d2b6  mov     [rbp+58h], rcx
0x14001d2ba  inc     rcx
0x14001d2bd  xor     edx, edx
0x14001d2bf  call    ??$_Allocate@D@std@@YAPEAD_KPEAD@Z; std::_Allocate<char>(unsigned __int64,char *)
0x14001d2c4  mov     [rbp+68h], rax
0x14001d2c8  mov     rax, 0
0x14001d2d2  add     rsp, 20h
0x14001d2d6  pop     rbp
0x14001d2d7  retn
```
