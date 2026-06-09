# _std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0

- ea: `0x140015f7b`
- end: `0x140015fa0`
- name: `_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___::_Copy_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400023b8`
- `0x1400143f4`

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
0x140015f7b  mov     [rsp+arg_8], rdx
0x140015f80  push    rbp
0x140015f81  sub     rsp, 20h
0x140015f85  mov     rbp, rdx
0x140015f88  xor     r8d, r8d
0x140015f8b  mov     dl, 1
0x140015f8d  mov     rcx, [rbp+50h]
0x140015f91  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140015f96  xor     edx, edx; pThrowInfo
0x140015f98  xor     ecx, ecx; pExceptionObject
0x140015f9a  call    _CxxThrowException_0
```
