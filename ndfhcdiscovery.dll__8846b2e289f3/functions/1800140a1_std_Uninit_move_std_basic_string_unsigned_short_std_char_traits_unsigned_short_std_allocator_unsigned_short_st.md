# _std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0

- ea: `0x1800140a1`
- end: `0x1800140d1`
- name: `_std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch$0`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001f9c`
- `0x18000c558`
- `0x1800140a1`

## pseudocode

```c
void __fastcall __noreturn std::_Uninit_move_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::allocator_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______::_1_::catch_0(
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
0x1800140a1  mov     [rsp+arg_8], rdx
0x1800140a6  push    rbx
0x1800140a7  push    rbp
0x1800140a8  sub     rsp, 28h
0x1800140ac  mov     rbp, rdx
0x1800140af  mov     rbx, [rbp+48h]
0x1800140b3  jmp     short loc_1800140C1
0x1800140b5  mov     rdx, rbx
0x1800140b8  call    ??$destroy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(std::wstring *)
0x1800140bd  add     rbx, 20h ; ' '
0x1800140c1  cmp     rbx, [rbp+40h]
0x1800140c5  jnz     short loc_1800140B5
0x1800140c7  xor     edx, edx; pThrowInfo
0x1800140c9  xor     ecx, ecx; pExceptionObject
0x1800140cb  call    _CxxThrowException_0
```
