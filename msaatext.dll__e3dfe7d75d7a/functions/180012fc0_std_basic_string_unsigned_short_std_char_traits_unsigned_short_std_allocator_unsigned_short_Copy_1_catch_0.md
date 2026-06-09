# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x180012fc0`
- end: `0x180012fe5`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f3c`
- `0x180002ee4`

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
0x180012fc0  mov     [rsp+arg_8], rdx
0x180012fc5  push    rbp
0x180012fc6  sub     rsp, 20h
0x180012fca  mov     rbp, rdx
0x180012fcd  xor     r8d, r8d
0x180012fd0  mov     dl, 1
0x180012fd2  mov     rcx, [rbp+50h]
0x180012fd6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180012fdb  xor     edx, edx; pThrowInfo
0x180012fdd  xor     ecx, ecx; pExceptionObject
0x180012fdf  call    _CxxThrowException_0
```
