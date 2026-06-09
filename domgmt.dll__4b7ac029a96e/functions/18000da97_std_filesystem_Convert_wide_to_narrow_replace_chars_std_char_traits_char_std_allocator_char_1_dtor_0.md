# _std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0

- ea: `0x18000da97`
- end: `0x18000dabd`
- name: `_std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008d20`
- `0x18000da97`

## pseudocode

```c
void __fastcall std::filesystem::_Convert_wide_to_narrow_replace_chars_std::char_traits_char__std::allocator_char____::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 48) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 48) &= ~1u;
    std::string::~string(*(char ***)(a2 + 112));
  }
}

```

## disassembly

```asm
0x18000da97  push    rbp
0x18000da99  sub     rsp, 20h
0x18000da9d  mov     rbp, rdx
0x18000daa0  mov     eax, [rbp+30h]
0x18000daa3  and     eax, 1
0x18000daa6  test    eax, eax
0x18000daa8  jz      short loc_18000DAB7
0x18000daaa  and     dword ptr [rbp+30h], 0FFFFFFFEh
0x18000daae  mov     rcx, [rbp+70h]
0x18000dab2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000dab7  add     rsp, 20h
0x18000dabb  pop     rbp
0x18000dabc  retn
```
