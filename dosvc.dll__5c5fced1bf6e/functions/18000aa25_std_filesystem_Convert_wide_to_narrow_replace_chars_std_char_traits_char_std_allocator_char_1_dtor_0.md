# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x18000aa25`
- end: `0x18000aa4e`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `41`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009a30`
- `0x18000aa25`

## pseudocode

```c
void __fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    std::string::~string(*(_QWORD *)(a2 + 176));
  }
}

```

## disassembly

```asm
0x18000aa25  push    rbp
0x18000aa27  sub     rsp, 20h
0x18000aa2b  mov     rbp, rdx
0x18000aa2e  mov     eax, [rbp+30h]
0x18000aa31  and     eax, 1
0x18000aa34  test    eax, eax
0x18000aa36  jz      short loc_18000AA48
0x18000aa38  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000aa3c  mov     rcx, [rbp+0B0h]
0x18000aa43  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000aa48  add     rsp, 20h
0x18000aa4c  pop     rbp
0x18000aa4d  retn
```
