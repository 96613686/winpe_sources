# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x18000d077`
- end: `0x18000d09c`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007844`
- `0x18000c4b0`

## pseudocode

```c
void __fastcall __noreturn std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbp

  v2 = a2;
  LOBYTE(a2) = 1;
  std::wstring::_Tidy(*(_QWORD *)(v2 + 80), a2, 0);
  throw;
}

```

## disassembly

```asm
0x18000d077  mov     [rsp+arg_8], rdx
0x18000d07c  push    rbp
0x18000d07d  sub     rsp, 20h
0x18000d081  mov     rbp, rdx
0x18000d084  xor     r8d, r8d
0x18000d087  mov     dl, 1
0x18000d089  mov     rcx, [rbp+50h]
0x18000d08d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000d092  xor     edx, edx; pThrowInfo
0x18000d094  xor     ecx, ecx; pExceptionObject
0x18000d096  call    _CxxThrowException_0
```
