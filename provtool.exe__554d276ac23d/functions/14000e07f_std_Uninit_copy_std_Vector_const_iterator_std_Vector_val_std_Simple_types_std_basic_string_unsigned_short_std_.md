# _std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________::_1_::catch$0

- ea: `0x14000e07f`
- end: `0x14000e0af`
- name: `_std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140003288`
- `0x14000dd7c`
- `0x14000e07f`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_copy_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short__________std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 i; // rbx

  for ( i = *(_QWORD *)(a2 + 72); i != *(_QWORD *)(a2 + 64); i += 32 )
    std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(a1, i);
  throw;
}

```

## disassembly

```asm
0x14000e07f  mov     [rsp+arg_8], rdx
0x14000e084  push    rbx
0x14000e085  push    rbp
0x14000e086  sub     rsp, 28h
0x14000e08a  mov     rbp, rdx
0x14000e08d  mov     rbx, [rbp+48h]
0x14000e091  jmp     short loc_14000E09F
0x14000e093  mov     rdx, rbx
0x14000e096  call    ??$destroy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(std::wstring *)
0x14000e09b  add     rbx, 20h ; ' '
0x14000e09f  cmp     rbx, [rbp+40h]
0x14000e0a3  jnz     short loc_14000E093
0x14000e0a5  xor     edx, edx; pThrowInfo
0x14000e0a7  xor     ecx, ecx; pExceptionObject
0x14000e0a9  call    _CxxThrowException_0
```
